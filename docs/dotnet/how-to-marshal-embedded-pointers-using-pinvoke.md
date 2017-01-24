---
title: "方法: PInvoke を使用して埋め込みポインターをマーシャリングする | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "データ マーシャリング [C++], 埋め込みポインター"
  - "埋め込みポインター [C++]"
  - "相互運用 [C++], 埋め込みポインター"
  - "マーシャリング [C++], 埋め込みポインター"
  - "プラットフォーム呼び出し [C++], 埋め込みポインター"
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: PInvoke を使用して埋め込みポインターをマーシャリングする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プラットフォーム呼び出し \(P\/Invoke\) 機能を使用して、マネージ コードからアンマネージ DLL で実装される関数を呼び出すことができます。  DLL のソース コードが利用できない場合、相互運用できるようにするには P\/Invoke を使用する以外方法はありません。  ただし、他の .NET 言語とは異なり、Visual C\+\+ には P\/Invoke 以外の方法が用意されています。  詳細については、「[C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)」および「[方法: C\+\+ Interop を使用して埋め込みポインターをマーシャリングする](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)」を参照してください。  
  
## 使用例  
 ネイティブ コードに構造体を渡す場合、データ レイアウトにおいてネイティブ構造体と等価なマネージ構造体を作成する必要があります。  ただし、ポインターを含む構造体の場合、特別な処理が必要です。  ネイティブ構造体に埋め込まれた各ポインターについて、その構造体のマネージ バージョンに <xref:System.IntPtr> 型のインスタンスを含める必要があります。  また、<xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A>、<xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A>、および <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> の各メソッドを使用して、これらのインスタンスのメモリを明示的に割り当て、初期化し、開放する必要があります。  
  
 次のコードは、アンマネージ モジュールとマネージ モジュールで構成されます。  アンマネージ モジュールは、ポインターを含む ListString と呼ばれる構造体を受け取る関数、および TakesListStruct と呼ばれる関数を定義する DLL です。  マネージ モジュールは、TakesListStruct 関数をインポートし、MListStruct と呼ばれる構造体を定義するコマンド ライン アプリケーションです。MListStruct は、<xref:System.IntPtr> インスタンスで表される double\* を除き、ネイティブな ListStruct と等価です。  main 関数は、TakesListStruct を呼び出す前に、このフィールドが参照するメモリを割り当てて初期化します。  
  
 \/clr を指定してマネージ モジュールをコンパイルします。\/clr:pure を使用してもかまいません。  
  
```  
// TraditionalDll6.cpp  
// compile with: /EHsc /LD  
#include <stdio.h>  
#include <iostream>  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
#pragma pack(push, 8)  
struct ListStruct {  
   int count;  
   double* item;  
};  
#pragma pack(pop)  
  
extern "C" {  
   TRADITIONALDLL_API void TakesListStruct(ListStruct);  
}  
  
void TakesListStruct(ListStruct list) {  
   printf_s("[unmanaged] count = %d\n", list.count);  
   for (int i=0; i<list.count; i++)  
      printf_s("array[%d] = %f\n", i, list.item[i]);  
}  
```  
  
```  
// EmbeddedPointerMarshalling.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Sequential, Pack=8)]  
value struct MListStruct {  
   int count;  
   IntPtr item;  
};  
  
value struct TraditionalDLL {  
    [DllImport("TraditionalDLL6.dll")]  
   static public void TakesListStruct(MListStruct);  
};  
  
int main() {  
   array<double>^ parray = gcnew array<double>(10);  
   Console::WriteLine("[managed] count = {0}", parray->Length);  
  
   Random^ r = gcnew Random();  
   for (int i=0; i<parray->Length; i++) {  
      parray[i] = r->NextDouble() * 100.0;  
      Console::WriteLine("array[{0}] = {1}", i, parray[i]);  
   }  
  
   int size = Marshal::SizeOf(double::typeid);  
   MListStruct list;  
   list.count = parray->Length;  
   list.item = Marshal::AllocCoTaskMem(size * parray->Length);  
  
   for (int i=0; i<parray->Length; i++) {  
      IntPtr t = IntPtr(list.item.ToInt32() + i * size);  
      Marshal::StructureToPtr(parray[i], t, false);  
   }  
  
   TraditionalDLL::TakesListStruct( list );  
   Marshal::FreeCoTaskMem(list.item);  
}  
```  
  
 ただし、DLL のどの部分も、従来の \#include ディレクティブを使用してのマネージ コードへの公開はしていません。  実際には、DLL には実行時にしかアクセスしないため、<xref:System.Runtime.InteropServices.DllImportAttribute> を使ってインポートされた関数についての問題は、コンパイル時には検出されません。  
  
## 参照  
 [C\+\+ での明示的な PInvoke \(DllImport 属性\) の使用方法 ](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)