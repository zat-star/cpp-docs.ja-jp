---
title: "未処理の C++ 例外 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 例外処理, 未処理の例外"
  - "catch キーワード [C++], ハンドラーが見つかりません"
  - "イベント ハンドラー, 未処理の例外"
  - "例外, 未処理"
  - "未処理の例外"
ms.assetid: 13f09c53-9254-4407-9db9-14e730e047cc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 未処理の C++ 例外
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

一致するハンドラー \(または省略記号 **catch** ハンドラー\) が現在の例外で見つからない場合は、定義済みの `terminate` ランタイム関数が呼び出されます  \(または明示的にハンドラーのいずれかで `terminate` を呼び出すことができます\)。 `terminate` の既定のアクションは、`abort` を呼び出すことです。  `terminate` でアプリケーションを終了する前に他の関数を呼び出すには、呼び出す関数の名前を唯一の引数として `set_terminate` 関数を呼び出します。  `set_terminate` はプログラムの任意の時点で呼び出すことができます。  `terminate` ルーチンは、`set_terminate` への引数として渡された最後の関数を常に呼び出します。  
  
## 使用例  
 次の例は、`char *` 例外をスローしますが、型 `char *` の例外をキャッチするハンドラーは含まれません。  `set_terminate` の呼び出しは、`terminate` に対して `term_func` を呼び出すように指示します。  
  
```  
// exceptions_Unhandled_Exceptions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
void term_func() {  
   cout << "term_func was called by terminate." << endl;  
   exit( -1 );  
}  
int main() {  
   try  
   {  
      set_terminate( term_func );  
      throw "Out of memory!"; // No catch handler for this exception  
   }  
   catch( int )  
   {  
      cout << "Integer exception raised." << endl;  
   }  
   return 0;  
}  
```  
  
## 出力  
  
```  
term_func was called by terminate.  
```  
  
 `term_func` 関数は、理想的には `exit` を呼び出して、プログラムまたは現在のスレッドを終了する必要があります。  そうしないで、呼び出し元に戻った場合は、`abort` が呼び出されます。  
  
## 参照  
 [C\+\+ 例外処理](../cpp/cpp-exception-handling.md)