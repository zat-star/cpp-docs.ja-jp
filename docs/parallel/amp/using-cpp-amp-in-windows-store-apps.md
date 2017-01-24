---
title: "Windows ストア アプリでの C++ AMP の使用 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
caps.latest.revision: 14
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows ストア アプリでの C++ AMP の使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\) を使用すると、GPU \(グラフィックス処理装置\) またはその他の計算アクセラレータで計算を実行できます。  ただし C\+\+ AMP では、Windows ランタイムの型を直接操作するための API が提供されておらず、Windows ランタイムでは C\+\+ AMP のラッパーが提供されません。  Windows ランタイムの型を \(独自に作成したコードも含めて\) コード内で使用するときは、C\+\+ AMP と互換性のある型に変換する必要があります。  
  
## パフォーマンスに関する考慮事項  
 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリの作成に [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)]\([!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)]\) を使用する場合、C\+\+ AMP で使用するデータには、POD \(plain old data\) 型と共に連続した記憶域 \(`std::vector` や C スタイルの配列など\) を使用することをお勧めします。  マーシャリングの必要がないため、非 POD 型または Windows RT コンテナーを使用する場合より高いパフォーマンスの実現に役立ちます。.  
  
 C \+\+ AMP カーネルで、この方法で格納されているデータにアクセスするには、`std::vector` または配列記憶域を `concurrency::array_view` でラップし、この配列ビューを `concurrency::parallel_for_each` ループで使用します。  
  
```cpp  
// simple vector addition example  
std::vector<int> data0(1024, 1);  
std::vector<int> data1(1024, 2);  
std::vector<int> data_out(data0.size(), 0);  
  
concurrency::array_view<int, 1> av0(data0.size(), data0);  
concurrency::array_view<int, 1> av1(data1.size(), data1);  
concurrency::array_view<int, 1> av2(data_out.size(), data2);   
  
av2.discard_data();  
  
concurrency::parallel_for_each(av0.extent, [=](concurrency::index<1> idx) restrict(amp)  
{  
  av2[idx] = av0[idx] + av1[idx];  
});  
  
```  
  
## Windows ランタイム型をマーシャリングする  
 Windows ランタイム API を使用する場合、`Platform::Array<T>^` などの Windows ランタイム コンテナーに格納されているデータや、`ref` キーワードまたは `value` キーワードを使用して宣言されたクラスや構造体などの複合データ型に格納されているデータに対して C\+\+ AMP を使用することが考えられます。  この場合、C\+\+ AMP でデータを使用できるように特別な作業を行う必要があります。  
  
### Platform::Array\<T\>^ \(T は POD 型\)  
 `Platform::Array<T>^` を検出した場合に T が POD 型であれば、基となる記憶域に `get` メンバー関数を使用してアクセスすることができます。  
  
```cpp  
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API  
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));  
  
```  
  
 T が POD 型でない場合に C\+\+ AMP でデータを使用するには、次のセクションで説明する手法を使用します。  
  
### Windows ランタイム型: ref クラスと value クラス  
 C\+\+ AMP では、複合データ型がサポートされません。  これには、非 POD 型や、`ref` キーワードまたは `value` キーワードを使用して宣言される型が含まれます。  サポートされていない型が `restrict(amp)` のコンテキストで使用されている場合、コンパイル時エラーが生成されます。  
  
 サポートされない型を検出した場合は、そのデータの必要な部分を `concurrency::array` オブジェクトにコピーできます。  データを C\+\+ AMP で使用できるようにする作業に加え、この手動コピーを行うことも、データの局所性を最大限に高め、使用しないデータがアクセラレータにコピーされないようにする点で、パフォーマンスの向上に役立ちます。  さらにパフォーマンスを高めるには、*ステージング配列*を使用します。これは、`concurrency::array` の特殊な形であり、指定されたアクセラレータでこの配列と他の配列との間で頻繁な転送を行う場合に配列を最適化するためのヒントを AMP ランタイムに提供します。  
  
```cpp  
// pixel_color.h  
ref class pixel_color sealed  
{  
 public:   
  pixel_color(Platform::String^ color_name, int red, int green, int blue)   
  {  
    name = color_name;  
    r = red;  
    g = green;  
    b = blue;  
  }  
  
  property Platform::String^ name;   
  property int r;  
  property int g;  
..property int b;  
};  
  
// Some other file  
std::vector<pixel_color^> pixels (256);   
  
for(pixel_color ^pixel : pixels)   
{  
  pixels.push_back(ref new pixel_color("blue", 0, 0, 255));  
}  
// Create the accelerators  
auto cpuAccelerator = concurrency::accelerator(concurrency::accelerator::cpu_accelerator);  
auto devAccelerator = concurrency::accelerator(concurrency::accelerator::default_accelerator);  
  
// Create the staging arrays  
concurrency::array<float, 1> red_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);  
concurrency::array<float, 1>  blue_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);   
  
// Extract data from the complex array of structs into staging arrays.  
concurrency::parallel_for(0, 256, [&](int i)  
{   
  red_vec[i] = pixels[i]->r; blue_vec[i] = pixels[i]->b;  
});  
  
// Array views are still used to copy data to the accelerator  
concurrency::array_view<float, 1> av_red(red_vec);  
concurrency::array_view<float, 1> av_blue(blue_vec);  
  
// Change all pixels from blue to red.  
concurrency::parallel_for_each(av_red.extent, [=](index<1> idx) restrict(amp)  
{  
  av_red[idx] = 255;  
  av_blue[idx] = 0;  
});  
  
```  
  
## 参照  
 [C\+\+ を使った初めての Windows ストア アプリの作成](http://go.microsoft.com/fwlink/p/?LinkId=249073)   
 [C\+\+ での Windows ランタイム コンポーネントの作成](http://go.microsoft.com/fwlink/p/?LinkId=249076)