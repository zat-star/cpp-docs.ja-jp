---
title: "コンパイラ エラー C2065 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2065
dev_langs:
- C++
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 5a3a0d4389a958f421f23a4dc96a395eaf3e22ab
ms.contentlocale: ja-jp
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-error-c2065"></a>コンパイラ エラー C2065
'identifier' : 定義されていない識別子です。  
  
コンパイラは、識別子の宣言を見つけることができません。 識別子が変数の場合を使用する前に、宣言で変数の種類を指定する必要があります。 識別子が関数名である場合は、関数を使用する前に、宣言内で関数を使用するパラメーターを指定する必要があります。 識別子が、ユーザー定義型のタグなどに設定されている場合、`class`または`struct`を使用する前に、タグの型を宣言する必要があります。 使用して型を宣言する必要があります、識別子が、型の別名の場合、`using`宣言または`typedef`型を使用する前にします。  
  
このエラーの多くの原因があります。 次にいくつかの最も一般的な問題を示します。
  
## <a name="example-misspelled-identifier"></a>例: スペルの正しくない識別子  
  
このエラーは、識別子名のスペルが誤っていない、または識別子、間違った大文字と小文字を区別を使用するときによく発生します。 宣言内の名前を使用する名前と正確に一致する必要があります。  
  
```cpp  
// C2065_spell.cpp  
// compile with: cl /EHsc C2065_spell.cpp 
#include <iostream> 
using namespace std; 
int main() { 
    int someIdentifier = 42; 
    cout << "Some Identifier: " << SomeIdentifier << endl;   
    // C2065: 'SomeIdentifier': undeclared identifier 
    // To fix, correct the spelling:  
    // cout << "Some Identifier: " << someIdentifier << endl;   
}  
```
  
## <a name="example-missing-header-file"></a>例: ヘッダー ファイルがありません。  
  
識別子を宣言するヘッダー ファイルが含まれているいません。 それを使用するすべてのソース ファイルで、識別子の宣言を格納しているファイルが含まれていることを確認してください。  
  
```cpp  
// C2065_header.cpp  
// compile with: cl /EHsc C2065_spell.cpp 

//#include <stdio.h> 
int main() { 
    fpos_t file_position = 42; // C2065: 'fpos_t': undeclared identifier 
    // To fix, uncomment the #include <stdio.h> line
    // to include the header where fpos_t is defined  
} 
```  
  
定義した場合は、Windows デスクトップ アプリのソース ファイルにこのエラーを表示する可能性があります`VC_EXTRALEAN`、 `WIN32_LEAN_AND_MEAN`、または`WIN32_EXTRA_LEAN`です。 これらのプリプロセッサ マクロは、いくつかのヘッダー ファイルを windows.h および afxv から除外\_w32.h の高速にコンパイルします。 Windows.h および afxv_w32.h 除外された項目の最新の状態の詳細についてを参照してください。  
  
## <a name="eample-missing-closing-quote"></a>Eample: 閉じかっこがありません。  
  
このエラーは、文字列定数の後に、終わりの引用符がない場合に発生することができます。 これは、コンパイラと混同する簡単な方法です。 
  
```cpp  
// C2065_quote.cpp  
// compile with: cl /EHsc C2065_quote.cpp 
#include <iostream>  

int main() { 
    // Fix this issue by adding the closing quote to "Aaaa"
    char * first = "Aaaa, * last = "Zeee"; 
    std::cout << "Name: " << first 
        << " " << last << std::endl; // C2065: 'last': undeclared identifier 
} 
```  
  
## <a name="example-use-iterator-outside-for-loop-scope"></a>例: for ループ スコープの外側の反復子を使用します。  
  
このエラーは、反復子変数を宣言する場合に発生することができます、`for`ループし、使用しようとする反復子変数のスコープ外、`for`ループします。 コンパイラにより、 [/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)既定ではコンパイラ オプション。 参照してください[デバッグ反復子のサポート](../../standard-library/debug-iterator-support.md)詳細についてはします。  
  
```cpp  
// C2065_iter.cpp  
// compile with: cl /EHsc C2065_iter.cpp 
#include <iostream> 
#include <string> 

int main() {
    // char last = '!'; 
    std::string letters{ "ABCDEFGHIJKLMNOPQRSTUVWXYZ" }; 
    for (const char& c : letters) {
        if ('Q' == c) {
            std::cout << "Found Q!" << std::endl;
        }
        // last = c;
    }
    std::cout << "Last letter was " << c << std::endl; // C2065
    // Fix by using a variable declared in an outer scope.
    // Uncomment the lines that declare and use 'last' for an example.
    // std::cout << "Last letter was " << last << std::endl; // C2065
} 
```  
  
## <a name="example-preprocessor-removed-declaration"></a>プリプロセッサの削除宣言の例:  
  
このエラーは、関数または現在の構成がコンパイルされていない条件付きでコンパイルされたコード内にある変数を参照する場合に発生することができます。 ビルド環境で現在サポートされていないヘッダー ファイルで関数を呼び出す場合にも発生することができます。 特定の変数または関数は特定のプリプロセッサ マクロが定義されている場合にのみ使用できる場合、は、同じプリプロセッサ マクロが定義されている場合、これらの関数を呼び出すコードをコンパイルすることができますのみを確認します。 この問題がやすい IDE では、現在のビルド構成の必要なプリプロセッサ マクロが定義されていない場合、関数の宣言がグレーです。  
  
デバッグ ビルドは、市販のない場合に機能するコードの例を次に示します。  
  
```cpp  
// C2065_defined.cpp
// Compile with: cl /EHsc /W4 /MT C2065_defined.cpp
#include <iostream>
#include <crtdbg.h>
#ifdef _DEBUG
    _CrtMemState oldstate;
#endif
int main() {
    _CrtMemDumpStatistics(&oldstate); 
    std::cout << "Total count " << oldstate.lTotalCount; // C2065
    // Fix by guarding references the same way as the declaration:
    // #ifdef _DEBUG
    //    std::cout << "Total count " << oldstate.lTotalCount;
    // #endif
}
```
  
## <a name="example-use-an-unscoped-identifier"></a>例: 対象範囲外の識別子を使用します。  
  
このエラーは、ユーザーの識別子は正しくスコープでない場合に発生することができます。 たとえば、C++ 標準ライブラリ関数および演算子完全修飾されていない名前空間でまたは場合いないを移動、`std`名前空間を使用して、現在のスコープを`using`ディレクティブ、コンパイラが検出できないことです。 この問題を解決する必要がありますか、完全に識別子の名前を修飾または指定した、名前空間と、`using`ディレクティブです。  
  
この例は、ため、コンパイルが失敗した`cout`と`endl`で定義されて、`std`名前空間。  
  
```cpp  
// C2065_scope.cpp  
// compile with: cl /EHsc C2065_scope.cpp 
// using namespace std;   // Uncomment this line to fix  
#include <iostream>  
int main() {  
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier 
                               // C2065 'endl': undeclared identifier
    // Or try the following line instead  
    std::cout << "Hello" << std::endl;  
}
```  
  
内の宣言された識別子`class`、 `struct`、または`enum class`型は、外側のスコープの名前でも修飾する必要があります。
  
## <a name="example-ccli-type-deduction-failure"></a>例: C + + CLI 型推論が失敗  
  
このエラーは、目的の型引数を使用して、パラメーターから推測できない場合のジェネリック関数を呼び出すときに発生します。 詳細については、次を参照してください。[ジェネリック関数 (C + + CLI)](../../windows/generic-functions-cpp-cli.md)です。  
  
```cpp  
// C2065_b.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
int main() {  
   // global generic function call  
   G<T>(10);   // C2065  
   G<int>(10);   // OK - fix with a specific type argument  
}  
```  
  
## <a name="example-ccli-attribute-parameters"></a>例: C + + CLI 属性パラメーター  
  
このエラーは、Visual C++ 属性のパラメーター チェックを行う Visual C++ 2005 で行ったコンパイラ準拠作業の結果として生成されることもあります。  
  
```cpp  
// C2065_attributes.cpp  
// compile with: cl /c /clr C2065_attributes.cpp  
[module(DLL, name=MyLibrary)];   // C2065  
// try the following line instead  
// [module(dll, name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  

