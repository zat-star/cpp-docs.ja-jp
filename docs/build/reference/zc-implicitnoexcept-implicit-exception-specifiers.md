---
title: "/Zc:implicitNoexcept (暗黙の例外指定子) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc:implicitNoexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc:implicitNoexcept"
  - "Zc:implicitNoexcept"
  - "-Zc:implicitNoexcept"
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /Zc:implicitNoexcept (暗黙の例外指定子)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Zc:implicitNoexcept** オプションを指定すると、コンパイラは、コンパイラ定義の特別なメンバー関数およびユーザー定義のデストラクターとデアロケーターに暗黙的な [noexcept](../Topic/noexcept%20\(C++\).md) 例外指定子を追加します。  既定では、ISO C\+\+11 標準に準拠するように **\/Zc:implicitNoexcept** が有効になっています。  このオプションをオフにすると、ユーザー定義のデストラクターとデアロケーターおよびコンパイラ定義の特別なメンバー関数に対して暗黙的な `noexcept` が無効になります。  
  
## 構文  
  
```vb  
/Zc:implicitNoexcept[-]  
```  
  
#### パラメーター  
  
## 解説  
 既定では、**\/Zc:implicitNoexcept** を指定すると、コンパイラは ISO C\+\+11 標準のセクション 15.4 に従い、暗黙的に宣言または明示的に既定化されたそれぞれの特別なメンバー関数 \(既定のコントラクター、コピー コンストラクター、移動コンストラクター、デストラクター、コピー代入演算子、または移動代入演算子\)、およびユーザー定義のそれぞれのデストラクターまたはデアロケーター関数に `noexcept` 例外指定子を暗黙的に追加します。  ユーザー定義のデアロケーターには、暗黙的な `noexcept(true)` 例外指定子があります。  ユーザー定義のデストラクターでは、含まれているメンバー クラスまたは基底クラスに `noexcept(true)` ではないデストラクターがなければ、暗黙的な例外指定子は `noexcept(true)` です。  コンパイラにより生成された特別なメンバー関数では、この関数によって直接呼び出された任意の関数が実質的に `noexcept(false)` である場合、暗黙的な例外指定子は `noexcept(false)` です。  それ以外の場合、暗黙的な例外指定子は `noexcept(true)` です。  
  
 コンパイラは、明示的な `noexcept` や `throw` 指定子または `__declspec(nothrow)` 属性を使用して宣言された関数に対して暗黙的な例外指定子を生成しません。  
  
 **\/Zc:implicitNoexcept\-** を指定することでオプションが無効になっている場合、コンパイラによって暗黙的な例外指定子は生成されません。  この動作は Visual Studio 2013 の場合と同じであり、例外指定子がないデストラクターとデアロケーターでは `throw` ステートメントを使用することができません。  既定の場合や **\/Zc:implicitNoexcept** を指定した場合、暗黙的な `noexcept(true)` 指定子を使用する関数で実行時に `throw` ステートメントが見つかったときは、`std::terminate` が即座に呼び出され、例外ハンドラーに対する通常のアンワインド動作は保証されません。  このような状況を識別するため、コンパイラは[コンパイラの警告 \(レベル 1\) C4297](../Topic/Compiler%20Warning%20\(level%201\)%20C4297.md) を生成します。  `throw` が意図的なものである場合は、**\/Zc:implicitNoexcept\-** を使用する代わりに明示的な `noexcept(false)` 指定子を使用するように関数宣言を変更することをお勧めします。  
  
 このサンプルでは、**\/Zc:implicitNoexcept** オプションを設定したときまたは無効にしたときの、明示的な例外指定子を持たないユーザー定義のデストラクターの動作を示しています。  このオプションを設定したときの動作を示すには、`cl/EHsc/W4 implicitNoexcept.cpp` を使用してコンパイルします。  このオプションを無効にしたときの動作を示すには、`cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp` を使用してコンパイルします。  
  
```  
// implicitNoexcept.cpp  
// Compile by using: cl /EHsc /W4 implicitNoexcept.cpp  
// Compile by using: cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp  
  
#include <iostream>  
#include <cstdlib>      // for std::exit, EXIT_FAILURE, EXIT_SUCCESS  
#include <exception>    // for std::set_terminate  
  
void my_terminate()  
{  
    std::cout << "Unexpected throw caused std::terminate" << std::endl;  
    std::cout << "Exit returning EXIT_FAILURE" << std::endl;  
    std::exit(EXIT_FAILURE);  
}  
  
struct A {  
    // Explicit noexcept overrides implicit exception specification  
    ~A() noexcept(false) {  
        throw 1;  
    }  
};  
  
struct B : public A {  
    // Compiler-generated ~B() definition inherits noexcept(false)  
    ~B() = default;  
};  
  
struct C {  
    // By default, the compiler generates an implicit noexcept(true)  
    // specifier for this user-defined destructor. To enable it to  
    // throw an exception, use an explicit noexcept(false) specifier,  
    // or compile by using /Zc:implicitNoexcept-  
    ~C() {    
        throw 1; // C4297, calls std::terminate() at run time  
    }  
};  
  
struct D : public C {  
    // This destructor gets the implicit specifier of its base.  
    ~D() = default;  
};  
  
int main()  
{  
    std::set_terminate(my_terminate);  
  
    try  
    {  
        {  
            B b;   
        }  
    }  
    catch (...)  
    {  
        // exception should reach here in all cases  
        std::cout << "~B Exception caught" << std::endl;  
    }  
    try  
    {  
        {  
            D d;  
        }  
    }  
    catch (...)  
    {  
        // exception should not reach here if /Zc:implicitNoexcept  
        std::cout << "~D Exception caught" << std::endl;  
    }  
    std::cout << "Exit returning EXIT_SUCCESS" << std::endl;  
    return EXIT_SUCCESS;  
}  
  
```  
  
 既定の設定 **\/Zc:implicitNoexcept** を使用してコンパイルした場合、このサンプルでは次の出力が生成されます。  
  
  **~B Exception caught**  
**Unexpected throw caused std::terminate**  
**Exit returning EXIT\_FAILURE** 設定 **\/Zc:implicitNoexcept\-** を使用してコンパイルした場合、このサンプルでは次の出力が生成されます。  
  
  **~B Exception caught**  
**~D Exception caught**  
**Exit returning EXIT\_SUCCESS** Visual C\+\+ の準拠の問題の詳細については、「[非標準動作](../Topic/Nonstandard%20Behavior.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **\[追加オプション\]** プロパティを変更して **\/Zc:implicitNoexcept** または **\/Zc:implicitNoexcept\-** を含め、**\[OK\]** を選択します。  
  
## 参照  
 [\/Zc \(準拠\)](../../build/reference/zc-conformance.md)   
 [noexcept](../Topic/noexcept%20\(C++\).md)   
 [例外の仕様 \(スロー\)](../../cpp/exception-specifications-throw-cpp.md)   
 [terminate](../Topic/terminate%20\(%3Cexception%3E\).md)