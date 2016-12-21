---
title: "例外の仕様 (スロー) (C++) | Microsoft Docs"
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
  - "C++ 例外処理, スロー (例外を)"
  - "例外, 例外の指定"
  - "throw キーワード [C++], 例外の指定"
  - "throw キーワード [C++], throw() および throw(...)"
  - "スロー (例外を), throw キーワード"
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
caps.latest.revision: 20
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 例外の仕様 (スロー) (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

例外の指定は、C\+\+11 で使用が推奨されていない C\+\+ 言語の機能です。  これらは、関数からスローできる例外に関する概要情報を提供するように設計されていましたが、実際には、問題があることがわかりました。  ある程度役に立つことがわかっている例外の指定は throw\(\) の指定です。  例:  
  
```  
void MyFunction(int i) throw();  
```  
  
 このコードでは、コンパイル時に関数が例外をスローしません。  これは、[\_\_declspec\(nothrow\)](../Topic/nothrow%20\(C++\).md) の使用と同じです。  その使用は省略可能であると見なされます。  
  
 **\(C\+\+ 11\)** ISO C\+\+11 標準で [noexcept](../Topic/noexcept%20\(C++\).md) 演算子が導入され、Visual Studio 2015 以降でサポートされています。  可能な場合は常に、`noexcept` を使用して関数が例外をスローするかどうかを指定してください。  
  
 Visual C\+\+ は、例外の指定の実装について ISO C\+\+ 標準から逸脱しています。  次の表は、Visual C\+\+ での例外の指定の実装をまとめたものです。  
  
|例外の指定|説明|  
|-----------|--------|  
|throw\(\)|関数は例外をスローしません。  ただし、throw\(\) でマークされた関数から例外がスローされると、Visual C\+\+ コンパイラは unexpected を呼び出しません \(詳細については「[unexpected](../Topic/unexpected%20\(CRT\).md)」と「[unexpected](../Topic/unexpected%20\(%3Cexception%3E\).md)」を参照\)。  関数が throw\(\) でマークされている場合、Visual C\+\+ コンパイラは、関数が C\+\+ 例外をスローしないと想定して、それに応じたコードを生成します。  C\+\+ コンパイラによってコードの最適化が実行される可能性があるため \(関数が C\+\+ 例外をスローしないという想定に基づいて\)、関数が例外をスローした場合にプログラムが正しく実行されないことがあります。|  
|throw\(...\)|関数は例外をスローできます。|  
|throw\(`type`\)|関数は型 `type` の例外をスローできます。  ただし、Visual C\+\+ .NET では、これは throw\(...\) として解釈されます。  「[関数の例外指定子](../misc/15-4-function-exception-specifiers.md)」を参照してください。|  
  
 例外処理がアプリケーションで使用されている場合、スローされた例外を処理する 1 つ以上の関数が必要です。  例外をスローする関数と、例外を処理する関数の間に呼び出される関数は、例外をスローできる必要があります。  
  
 関数のスロー動作は、次の要因によって決まります。  
  
-   C または C\+\+ で関数をコンパイルするかどうか。  
  
-   どの [\/EH](../build/reference/eh-exception-handling-model.md) コンパイラ オプションを使用するか。  
  
-   例外の指定を明示的に使用するかどうか。  
  
 明示的な例外の指定は C 関数では使用できません。  
  
 次の表に、関数のスロー動作をまとめます。  
  
|関数|\/EHsc|\/EHs|\/EHa|\/EHac|  
|--------|------------|-----------|-----------|------------|  
|C 関数|throw\(\)|throw\(...\)|throw\(...\)|throw\(...\)|  
|例外を指定していない C\+\+ 関数|throw\(...\)|throw\(...\)|throw\(...\)|throw\(...\)|  
|throw\(\) 例外を指定した C\+\+ 関数|throw\(\)|throw\(\)|throw\(...\)|throw\(...\)|  
|throw\(...\) 例外を指定した C\+\+ 関数|throw\(...\)|throw\(...\)|throw\(...\)|throw\(...\)|  
|throw\(`type`\) 例外を指定した C\+\+ 関数|throw\(...\)|throw\(...\)|throw\(...\)|throw\(...\)|  
  
## 使用例  
  
```cpp  
// exception_specification.cpp  
// compile with: /EHs  
#include <stdio.h>  
  
void handler() {  
   printf_s("in handler\n");  
}  
  
void f1(void) throw(int) {  
   printf_s("About to throw 1\n");  
   if (1)  
      throw 1;  
}  
  
void f5(void) throw() {  
   try {  
      f1();  
   }  
   catch(...) {  
      handler();  
    }  
}  
  
// invalid, doesn't handle the int exception thrown from f1()  
// void f3(void) throw() {  
//   f1();  
// }  
  
void __declspec(nothrow) f2(void) {  
   try {  
      f1();  
   }  
   catch(int) {  
      handler();  
    }  
}  
  
// only valid if compiled without /EHc   
// /EHc means assume extern "C" functions don't throw exceptions  
extern "C" void f4(void);  
void f4(void) {  
   f1();  
}  
  
int main() {  
   f2();  
  
   try {  
      f4();  
   }  
   catch(...) {  
      printf_s("Caught exception from f4\n");  
   }  
   f5();  
}  
```  
  
  **About to throw 1**  
**in handler**  
**About to throw 1**  
**Caught exception from f4**  
**About to throw 1**  
**in handler**   
## 参照  
 [try、throw、および catch ステートメント \(C\+\+\)](../cpp/try-throw-and-catch-statements-cpp.md)   
 [C\+\+ 例外処理](../cpp/cpp-exception-handling.md)