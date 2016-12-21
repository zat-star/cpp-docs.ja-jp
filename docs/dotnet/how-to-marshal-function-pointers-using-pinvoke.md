---
title: "方法: PInvoke を使用して関数ポインターをマーシャリングする | Microsoft Docs"
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
  - "データ マーシャリング [C++], コールバックとデリゲート"
  - "相互運用 [C++], コールバックとデリゲート"
  - "マーシャリング [C++], コールバックとデリゲート"
  - "プラットフォーム呼び出し [C++], コールバックとデリゲート"
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: PInvoke を使用して関数ポインターをマーシャリングする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、.NET Framework の P\/Invoke 機能を使用してアンマネージ関数と相互運用するときに、関数ポインターの代わりにマネージ デリゲートを使用する方法について説明します。  ただし、P\/Invoke は、ほとんどコンパイル時のエラーを報告せず、タイプセーフでもなく、また実装に時間がかかるため、可能な場合、Visual C\+\+ プログラマは P\/Invoke の代わりに C\+\+ Interop を使用することが推奨されています。  アンマネージ API が DLL としてパッケージ化されていて、そのソース コードが利用できない場合、P\/Invoke を使用する以外方法はありません。  それ以外の場合、次のトピックを参照してください。  
  
-   [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [方法: C\+\+ Interop を使用してコールバックおよびデリゲートをマーシャリングする](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
 関数ポインターを引数として受け取るアンマネージ API は、ネイティブ関数ポインターの代わりにマネージ デリゲートを使用してマネージ コードから呼び出すことができます。  コンパイラは、デリゲートを関数ポインターとしてアンマネージ関数に自動的にマーシャリングし、必要なマネージまたはアンマネージ遷移コードを挿入します。  
  
## 使用例  
 次のコードは、アンマネージ モジュールとマネージ モジュールで構成されます。  アンマネージ モジュールは、関数ポインターを受け取る TakesCallback と呼ばれる関数を定義する DLL です。  このアドレスは、関数を実行するために使用されます。  
  
 マネージ モジュールは、関数ポインターとしてネイティブ コードにマーシャリングされるデリゲートを定義し、<xref:System.Runtime.InteropServices.DllImportAttribute> 属性を使用して、ネイティブ TakesCallback 関数をマネージ コードに公開します。  main 関数では、デリゲートのインスタンスが作成され、TakesCallback 関数に渡されます。  プログラムの出力には、この関数がネイティブ TakesCallback 関数によって実行されたことが示されます。  
  
 マネージ関数は、ネイティブ関数の実行中に .NET Framework のガベージ コレクションがデリゲートを再配置することがないように、マネージ デリゲートに対するガベージ コレクションを抑制します。  
  
 \/clr を指定してマネージ モジュールをコンパイルします。\/clr:pure を使用してもかまいません。  
  
```  
// TraditionalDll5.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   /* Declare an unmanaged function type that takes two int arguments  
      Note the use of __stdcall for compatibility with managed code */  
   typedef int (__stdcall *CALLBACK)(int);  
   TRADITIONALDLL_API int TakesCallback(CALLBACK fp, int);  
}  
  
int TakesCallback(CALLBACK fp, int n) {  
   printf_s("[unmanaged] got callback address, calling it...\n");  
   return fp(n);  
}  
```  
  
```  
// MarshalDelegate.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
public delegate int GetTheAnswerDelegate(int);  
public value struct TraditionalDLL {  
   [DllImport("TraditionalDLL5.dll")]  
   static public int TakesCallback(GetTheAnswerDelegate^ pfn, int n);  
};  
  
int GetNumber(int n) {  
   Console::WriteLine("[managed] callback!");  
   static int x = 0;  
   ++x;  
   return x + n;  
}  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
   pin_ptr<GetTheAnswerDelegate^> pp = &fp;  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
   int answer = TraditionalDLL::TakesCallback(fp, 42);  
}  
```  
  
 ただし、DLL のどの部分も、従来の \#include ディレクティブを使用してのマネージ コードへの公開はしていません。  実際には、DLL には実行時にしかアクセスしないため、<xref:System.Runtime.InteropServices.DllImportAttribute> を使ってインポートされた関数についての問題は、コンパイル時には検出されません。  
  
## 参照  
 [C\+\+ での明示的な PInvoke \(DllImport 属性\) の使用方法 ](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)