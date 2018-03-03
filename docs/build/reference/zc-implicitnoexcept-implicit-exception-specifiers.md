---
title: "-Zc: implicitNoexcept (暗黙的な例外指定子) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Zc:implicitNoexcept
dev_langs:
- C++
helpviewer_keywords:
- /Zc:implicitNoexcept
- Zc:implicitNoexcept
- -Zc:implicitNoexcept
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9af0a7a3a175699a4f4b738271fe0d4c5bbac4b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="zcimplicitnoexcept-implicit-exception-specifiers"></a>/Zc:implicitNoexcept (暗黙の例外指定子)
ときに、 **/Zc:implicitNoexcept**オプションを指定すると、コンパイラは暗黙的な付加[noexcept](../../cpp/noexcept-cpp.md)コンパイラ定義の特別なメンバー関数をユーザー定義のデストラクターを例外指定子とデアロケーターです。 既定では、 **/Zc:implicitNoexcept** ISO C 11 標準に準拠するように有効にします。 このオプションをオフにすると、ユーザー定義のデストラクターとデアロケーターおよびコンパイラ定義の特別なメンバー関数に対して暗黙的な `noexcept` が無効になります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
/Zc:implicitNoexcept[-]  
```  
  
#### <a name="parameters"></a>パラメーター  
  
## <a name="remarks"></a>コメント  
 既定では、場合**/Zc:implicitNoexcept**指定すると、コンパイラは ISO C 11 標準のセクション 15.4 に続くし、暗黙的に追加、`noexcept`例外指定子をそれぞれが暗黙的に宣言または明示的に既定されました。特殊なメンバー関数 — 既定のコンス トラクター、コピー コンス トラクター、移動コンス トラクター、デストラクター、コピー代入演算子、または移動代入演算子、および各ユーザー定義のデストラクターまたはデアロケーター関数。 ユーザー定義のデアロケーターには、暗黙的な `noexcept(true)` 例外指定子があります。 ユーザー定義のデストラクターでは、含まれているメンバー クラスまたは基底クラスに `noexcept(true)` ではないデストラクターがなければ、暗黙的な例外指定子は `noexcept(true)` です。 コンパイラにより生成された特別なメンバー関数では、この関数によって直接呼び出された任意の関数が実質的に `noexcept(false)` である場合、暗黙的な例外指定子は `noexcept(false)` です。 それ以外の場合、暗黙的な例外指定子は `noexcept(true)` です。  
  
 コンパイラは、明示的な `noexcept` や `throw` 指定子または `__declspec(nothrow)` 属性を使用して宣言された関数に対して暗黙的な例外指定子を生成しません。  
  
 指定して、オプションが無効になっている場合**/zc: implicitnoexcept-**、コンパイラによって暗黙的な例外指定子は生成されません。 この動作は Visual Studio 2013 の場合と同じであり、例外指定子がないデストラクターとデアロケーターでは `throw` ステートメントを使用することができません。 既定とタイミング**/Zc:implicitNoexcept**を指定した場合、`throw`で暗黙的な関数の実行時にステートメントが検出された`noexcept(true)`指定子の直接の呼び出しになります`std::terminate`と例外ハンドラーに対する通常のアンワインド動作は保証されません。 このような状況を識別するには、コンパイラが生成されます[コンパイラの警告 (レベル 1) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md)です。 場合、`throw`は、意図的なことをお勧めする明示的な関数の宣言を変更する`noexcept(false)`指定子を使用せずに**/zc: implicitnoexcept-**です。  
  
 この例では、明示的な例外指定子を持たないユーザー定義のデストラクターの動作時に、 **/Zc:implicitNoexcept**オプションを設定するか、または無効になっています。 動作を示すを設定するを使用してコンパイル`cl /EHsc /W4 implicitNoexcept.cpp`です。 表示するには無効にしたときの動作を使用してコンパイル`cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp`です。  
  
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
  
 既定の設定を使用して、コンパイル時に**/Zc:implicitNoexcept**サンプルには、次の出力が生成されます。  
  
```Output  
~B Exception caught  
Unexpected throw caused std::terminate  
Exit returning EXIT_FAILURE  
```  
  
 設定を使用して、コンパイル時に**/zc: implicitnoexcept-**サンプルには、次の出力が生成されます。  
  
```Output  
~B Exception caught  
~D Exception caught  
Exit returning EXIT_SUCCESS  
```  
  
 Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、 **C/C++**フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  変更、**追加オプション**含めるプロパティを**/Zc:implicitNoexcept**または**/zc: implicitnoexcept-**を選択し**OK**です。  
  
## <a name="see-also"></a>参照  
 [/Zc (準拠)](../../build/reference/zc-conformance.md)   
 [noexcept](../../cpp/noexcept-cpp.md)   
 [例外の仕様 (スロー)](../../cpp/exception-specifications-throw-cpp.md)   
 [terminate](../../standard-library/exception-functions.md#terminate)