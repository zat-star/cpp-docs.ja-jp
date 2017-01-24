---
title: "方法: PInvoke を使用して文字列をマーシャリングする | Microsoft Docs"
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
  - "データ マーシャリング [C++], 文字列"
  - "相互運用 [C++], 文字列"
  - "マーシャリング [C++], 文字列"
  - "プラットフォーム呼び出し [C++], 文字列"
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: PInvoke を使用して文字列をマーシャリングする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、.NET Framework のプラットフォーム呼び出しサポートを使用して、C スタイル文字列を受け取るネイティブ関数が CLR 文字列型 System::String を使ってどのように呼び出されるかについて説明します。  P\/Invoke は、ほとんどコンパイル時のエラーを報告せず、タイプセーフでもなく、また実装に時間がかかるため、可能な場合、Visual C\+\+ プログラマは P\/Invoke の代わりに C\+\+ Interop を使用することが推奨されています。  アンマネージ API が DLL としてパッケージされていて、そのソース コードが利用できない場合、P\/Invoke を使用する以外方法はありません。それ以外の場合は、「[C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください。  
  
 マネージ文字列とアンマネージ文字列はメモリ内で別々に配置されているため、マネージ関数からアンマネージ関数に文字列を渡すには、<xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を使用して、文字列データを正確かつ安全にマーシャリングするために必要な変換機構を挿入するようにコンパイラに指示する必要があります。  
  
 組み込みのデータ型でのみ使用する関数と同様、<xref:System.Runtime.InteropServices.DllImportAttribute> を使用して、マネージ エントリ ポイントをネイティブ関数に宣言します。ただし、文字列を渡す場合は、C スタイル文字列を受け取るこれらのエントリ ポイントを定義する代わりに、<xref:System.String> 型へのハンドルを使用できます。  これにより、コンパイラは、必要な変換を実行するコードを挿入するように指示されます。  文字列を受け取るアンマネージ関数の関数引数ごとに、<xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を使用して、String オブジェクトをネイティブ関数に C スタイル文字列としてマーシャリングすることを指示する必要があります。  
  
## 使用例  
 次のコードは、アンマネージ モジュールとマネージ モジュールで構成されます。  アンマネージ モジュールは、TakesAString と呼ばれる関数を定義する DLL で、TakesAString は C スタイル ANSI 文字列を char\* 形式で受け取ります。  マネージ モジュールは、TakesAString 関数をインポートするコマンド ライン アプリケーションですが、このモジュールは、char\* ではなくマネージされた System.String を受け取るように TakesAString 関数を定義します。  <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を使用すると、TakesAString を呼び出したときにマネージ文字列をマーシャリングする方法を指定できます。  
  
 \/clr を指定してマネージ モジュールをコンパイルします。\/clr:pure を使用してもかまいません。  
  
```  
// TraditionalDll2.cpp  
// compile with: /LD /EHsc  
#include <windows.h>  
#include <stdio.h>  
#include <iostream>  
  
using namespace std;  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAString(char*);  
}  
  
void TakesAString(char* p) {  
   printf_s("[unmanaged] %s\n", p);  
}  
```  
  
```  
// MarshalString.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL  
{  
   [DllImport("TraditionalDLL2.dll")]  
      static public void   
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);  
};  
  
int main() {  
   String^ s = gcnew String("sample string");  
    Console::WriteLine("[managed] passing managed string to unmanaged function...");  
   TraditionalDLL::TakesAString(s);  
   Console::WriteLine("[managed] {0}", s);  
}  
```  
  
 この手法を使用して文字列のコピーをアンマネージ ヒープ上に構築すると、ネイティブ関数によって文字列が変更されたとしても、文字列のマネージ コピーには影響しません。  
  
 ただし、DLL のどの部分も、従来の \#include ディレクティブを使用してのマネージ コードへの公開はしていません。  実際には、DLL には実行時しかアクセスしないため、`DllImport` を使ってインポートされた関数についての問題は、コンパイル時には検出されません。  
  
## 参照  
 [C\+\+ での明示的な PInvoke \(DllImport 属性\) の使用方法 ](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)