---
title: "方法: PInvoke を使用して配列をマーシャリングする | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "データ マーシャリング [C++], 配列"
  - "相互運用 [C++], 配列"
  - "マーシャリング [C++], 配列"
  - "プラットフォーム呼び出し [C++], 配列"
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# 方法: PInvoke を使用して配列をマーシャリングする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、.NET Framework のプラットフォーム呼び出しサポートを使用して、CLR 文字列型 <xref:System.String> を使って C スタイルの文字列を受け入れるネイティブ関数を呼び出す方法について説明します。  P\/Invoke は、ほとんどコンパイル時のエラーを報告せず、タイプセーフでもなく、また実装に時間がかかるため、可能な場合、Visual C\+\+ プログラマは P\/Invoke の代わりに C\+\+ Interop を使用することが推奨されています。  アンマネージ API が DLL としてパッケージ化されていて、そのソース コードが利用できない場合、P\/Invoke を使用する以外方法はありません \(それ以外の場合は、「[C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください\)。  
  
## 使用例  
 ネイティブ配列とマネージ配列はメモリ上で別々にレイアウトされているため、マネージ境界またはアンマネージ境界を超えてこれらの配列を正しく渡すには、変換、つまりマーシャリングが必要です。  このトピックでは、単純な \(blitable\) 項目の配列をマネージ コードからネイティブ関数に渡す方法について説明します。  
  
 一般的なマネージ データまたはアンマネージ データのマーシャリングと同様、<xref:System.Runtime.InteropServices.DllImportAttribute> 属性を使用して、使用するネイティブ関数ごとにマネージ エントリ ポイントを作成します。  配列を引数として使用する関数では、<xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性も使用して、データのマーシャリング方法をコンパイラに指定する必要があります。  次の例では、<xref:System.Runtime.InteropServices.UnmanagedType> 列挙型を使用して、マネージ配列を C スタイル配列としてマーシャリングしています。  
  
 次のコードは、アンマネージ モジュールとマネージ モジュールで構成されます。  アンマネージ モジュールは、整数の配列を受け取る関数を定義する DLL です。  2 つ目のモジュールは、この関数をインポートするマネージ コマンド ライン アプリケーションですが、このモジュールは、マネージ配列についてこの関数を定義します。さらに、<xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を使用して、呼び出されたときに配列をネイティブ配列に変換することを指定します。  
  
 \/clr を指定してマネージ モジュールをコンパイルします。\/clr:pure を使用してもかまいません。  
  
```  
// TraditionalDll4.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);  
}  
  
void TakesAnArray(int len, int a[]) {  
   printf_s("[unmanaged]\n");  
   for (int i=0; i<len; i++)  
      printf("%d = %d\n", i, a[i]);  
}  
```  
  
```  
// MarshalBlitArray.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL {  
   [DllImport("TraditionalDLL4.dll")]  
   static public void TakesAnArray(  
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);  
};  
  
int main() {  
   array<int>^ b = gcnew array<int>(3);  
   b[0] = 11;  
   b[1] = 33;  
   b[2] = 55;  
   TraditionalDLL::TakesAnArray(3, b);  
  
   Console::WriteLine("[managed]");  
   for (int i=0; i<3; i++)  
      Console::WriteLine("{0} = {1}", i, b[i]);  
}  
```  
  
 ただし、DLL のどの部分も、従来の \#include ディレクティブを使用してのマネージ コードへの公開は実行しません。  実際には、DLL には実行時にしかアクセスしないため、<xref:System.Runtime.InteropServices.DllImportAttribute> を使ってインポートされた関数についての問題は、コンパイル時には検出されません。  
  
## 参照  
 [C\+\+ での明示的な PInvoke \(DllImport 属性\) の使用方法 ](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)