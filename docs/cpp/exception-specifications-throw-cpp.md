---
title: "例外の仕様 (スロー) (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++], throw() vs. throw(...)
- throw keyword [C++], exception specifications
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7559bdf725727b79f99ed3bfcd4d6b7301528110
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exception-specifications-throw-noexcept-c"></a>例外の仕様 (スロー、noexcept) (C++)
例外の指定は、関数によって伝達されることができます、例外の種類に関するプログラマの意図を示す C++ 言語の機能です。 関数がいるかを使用して、例外によって終了可能性がありますを指定することができます、*例外指定*です。 コンパイラは、この情報を使用して、関数への呼び出しを最適化するために、関数をエスケープする場合、予期しない例外は、プログラムを終了する. 例外の指定の 2 種類があります。 *Noexcept 仕様*は c++ 11 で新しく追加します。 これは、関数をエスケープする可能性がある例外のセットが空かどうかを指定します。 *動的例外指定*、または`throw(optional_type_list)`仕様、c++ 11 では使用されなくなりましたおよび Visual Studio によって部分的にサポートされます。 この例外の指定された関数の場合からどのような例外をスローできる概要情報を提供するように設計されていますが、実際には、見つかった問題があること。 ある程度役に立つことが 1 つの動的な例外の仕様は、無条件`throw()`仕様です。 たとえば、関数宣言します。  
  
```cpp  
void MyFunction(int i) throw();  
```  
  
 このコードでは、コンパイル時に関数が例外をスローしません。 使用すると同じ[無視されます。](../cpp/nothrow-cpp.md)です。 その使用は省略可能であると見なされます。  
  
ISO c 11 標準で、 [noexcept](../cpp/noexcept-cpp.md)代わりに、演算子が導入されました。 これには、Visual Studio 2015 以降ではサポートされています。 可能な限り、使用、`noexcept`関数が例外をスローするかどうかを指定する式。 たとえば、上記の 1 つではなくこの関数の宣言を使用します。  
  
```cpp  
void MyFunction(int i) noexcept;  
```  
  
Visual C を完全にサポートしますが、`noexcept`式では、これとは異なる、ISO C 標準で動的な例外の仕様の実装です。  次の表は、Visual C++ での例外の指定の実装をまとめたものです。  
  
|例外の指定|説明|  
|-----------------------------|-------------|  
|`noexcept`<br/>`noexcept(true)`<br/>`throw()`|関数は例外をスローしません。 ただしかどうか、マークされた関数から例外がスローされます。 `throw()`、Visual c コンパイラ呼び出し`std::terminate`ではなく、`std::unexpected`です。 参照してください[std::unexpected](../c-runtime-library/reference/unexpected-crt.md)詳細についてはします。 関数がマークされている場合`noexcept`、 `noexcept(true)`、または`throw()`、Visual C コンパイラは関数が C++ 例外をスローしないし、それに応じてコードを生成します。 関数がスローしないこと、C++ の例外では、関数は例外をスローする場合を前提として、C コンパイラでは、コードの最適化を実行することが、ため、プログラムが正しく実行されません。|  
|`noexcept(false)`<br/>`throw(...)`<br/>ない仕様|関数は、任意の型の例外をスローできます。|  
|`throw(type)`|関数は型 `type` の例外をスローできます。 Visual c でこの構文は受け入れられますが、として解釈されます`noexcept(false)`です。|  
  
 場合は、アプリケーションでは、例外処理を使用する必要があります関数、関数の外側のスコープを終了する前に、スローされた例外のハンドルがマークされている呼び出し履歴で`noexcept`、 `noexcept(true)`、または`throw()`です。 例外をスローする 1 つと、例外を処理する 1 つとして指定の間ですべての関数が呼び出された場合`noexcept`、 `noexcept(true)`、または`throw()`、noexcept 関数が、例外が伝達されると、プログラムは終了します。  
  
 関数の例外の動作は、次の要因によって異なります。  
  
-   C または C++ で関数をコンパイルするかどうか。  
  
-   [/EH](../build/reference/eh-exception-handling-model.md)コンパイラ オプションを使用します。  
  
-   例外の指定を明示的に使用するかどうか。  
  
 明示的な例外の指定は C 関数では使用できません。 C の関数をスローしないはずの下の例外**/EHsc**、下にある構造化例外をスローする可能性がありますと**/EHs**、 **/EHa**、または**/EHac**です。  
  
 次の表では、C++ 関数はさまざまなコンパイラ例外の処理オプションでスローすることは可能性がある可能性があるかどうかをまとめたものです。  
  
|関数|/EHsc|/EHs|/EHa|/EHac|  
|--------------|------------|-----------|-----------|------------|  
|例外を指定していない C++ 関数|[はい]|はい|はい|[はい]|  
|C++ の関数を`noexcept`、 `noexcept(true)`、または`throw()`例外の指定|×|Ｘ|はい|[はい]|  
|C++ の関数を`noexcept(false)`、 `throw(...)`、または`throw(type)`例外の指定|[はい]|はい|はい|[はい]|  
  
## <a name="example"></a>例  
  
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
  
```Output  
About to throw 1  
in handler  
About to throw 1  
Caught exception from f4  
About to throw 1  
in handler  
```  
  
## <a name="see-also"></a>参照  
 [try、throw、catch ステートメント (C++)](../cpp/try-throw-and-catch-statements-cpp.md)   
 [C++ 例外処理](../cpp/cpp-exception-handling.md)