---
title: "構造化例外処理 (C/C++) | Microsoft Docs"
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
  - "C++ 例外処理, 例外ハンドラー"
  - "C++ 例外処理, 終了ハンドラー"
  - "構造化例外処理"
  - "終了ハンドラー, 処理 (例外を C++ で)"
  - "try-catch キーワード [C++], 例外ハンドラー"
  - "try-catch キーワード [C++], 終了ハンドラー"
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 構造化例外処理 (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows および Visual C\+\+ は構造化例外処理 \(SEH\) をサポートしていますが、コードの移植性と柔軟性が高くなる ISO 標準の C\+\+ 例外処理を使用することをお勧めします。  ただし、既存のコードや特定の種類のプログラムでは、SEH を使用する必要がある場合もあります。  
  
## Microsoft 固有の仕様 →  
  
## 文章校正  
 *try\-except\-statement* :  
  
 `__try` *compound\-statement*  
  
 `__except` \( `expression` \) *compound\-statement*  
  
## 解説  
 SEH を使うと、実行が予期せずに終了した場合にメモリ ブロックやファイルなどのリソースが適切であることを確認できます。  また、メモリ不足などの特定の問題を、`goto` ステートメントやリターン コードの複雑なテストに依存しない簡潔な構造化されたコードを使用して処理することもできます。  
  
 ここで説明する try\-except および try\-finally ステートメントは C 言語に対する Microsoft の拡張機能です。  これらは、イベント後にプログラムの制御をアプリケーションが取得するようにし、そうでない場合は実行を終了させることによって SEH をサポートします。  SEH は C\+\+ ソース ファイルと連携しますが、C\+\+ 向けに設計されていません。  特定の修飾子と共に [\/EH](../build/reference/eh-exception-handling-model.md) オプションを使用してコンパイルした C \+\+ プログラムで SEH を使用する場合、ローカル オブジェクトのデストラクターは呼び出されますが、他の実行時の動作は予期したとおりにならない可能性があります   \(概要については、この記事で後述する例を参照してください\)。 ほとんどの場合、SEH の代わりに、Visual C\+\+ もサポートする ISO 標準の [C\+\+ 例外処理](../cpp/try-throw-and-catch-statements-cpp.md)を使用することをお勧めします。  C\+\+ 例外処理を使用すると、コードの移植性が高くなり、すべての種類の例外を処理できるようになります。  
  
 SEH を使用する C モジュールがある場合、C\+\+ 例外処理を使用する C\+\+ モジュールとそれらを混在させることができます。  詳細については、「[例外処理の相違点](../cpp/exception-handling-differences.md)」を参照してください。  
  
 SEH メカニズムには次の 2 つがあります。  
  
-   例外に対処または例外を拒絶できる[例外ハンドラー](../cpp/writing-an-exception-handler.md)。  
  
-   例外によってコード ブロック内で終了が発生すると呼び出される[終了ハンドラー](../cpp/writing-a-termination-handler.md)。  
  
 これら 2 種類のハンドラーは区別されますが、"スタックのアンワインド" というプロセスを通じて密接に関係しています。 例外が発生すると、Windows は現在アクティブである最も新しくインストールされた例外ハンドラーを検索します。  ハンドラーは、次の 3 つのうちの 1 つを行うことができます。  
  
-   例外の認識に失敗し、他のハンドラーに制御を渡す。  
  
-   例外を認識し、拒絶する。  
  
-   例外を認識し、処理する。  
  
 例外を認識する例外ハンドラーは、例外が発生したときに実行中だった関数内にない場合があります。  場合によっては、スタックのかなり上位の関数内にあります。  現在実行中の関数と、スタック フレーム上の他のすべての関数が終了します。  このプロセスでは、スタックが "アンワインド" されます。つまり、終了した関数のローカル変数は、`static` でない限りスタックから消去されます。  
  
 これがスタックをアンワインドするため、オペレーティング システムは、各関数に書き込んだ終了ハンドラーを呼び出します。  終了ハンドラーを使用して、異常終了のために開いたままになっているリソースをクリーンアップできます。  クリティカル セクションに入った場合、終了ハンドラーで終了できます。  プログラムがシャットダウンする場合、一時ファイルを閉じたり削除するなどの他のハウスキーピング タスクを実行できます。  
  
 詳細については次を参照してください:  
  
-   [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)  
  
-   [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)  
  
-   [C\+\+ での構造化例外処理の使用](../Topic/Using%20Structured%20Exception%20Handling%20with%20C++.md)  
  
## 使用例  
 前に説明したように、C\+\+ プログラムで SEH を使用し、特定の修飾子 \(たとえば **\/EH** や **\/EHsc**\) と共に **\/EHa** オプションを使用してコンパイルすると、ローカル オブジェクトのデストラクターが呼び出されます。  ただし、C\+\+ 例外も使用している場合は、実行時の動作は予期したとおりにならない可能性があります。  次の例は、これらの動作の違いを示しています。  
  
```cpp  
#include <stdio.h>  
#include <Windows.h>  
#include <exception>  
  
class TestClass  
{  
public:  
    ~TestClass()  
    {  
        printf("Destroying TestClass!\r\n");  
    }  
};  
  
__declspec(noinline) void TestCPPEX()  
{  
#ifdef CPPEX  
    printf("Throwing C++ exception\r\n");  
    throw std::exception("");  
#else  
    printf("Triggering SEH exception\r\n");  
    volatile int *pInt = 0x00000000;  
    *pInt = 20;  
#endif  
}  
  
__declspec(noinline) void TestExceptions()  
{  
    TestClass d;  
    TestCPPEX();  
}  
  
int main()  
{  
    __try  
    {  
        TestExceptions();  
    }  
    __except(EXCEPTION_EXECUTE_HANDLER)  
    {  
        printf("Executing SEH __except block\r\n");  
    }  
  
    return 0;  
}  
  
```  
  
 **\/EHsc** を使用してこのコードをコンパイルするがローカル テスト コントロール `CPPEX` が定義されていない場合、`TestClass` デストラクターの実行はされず、出力は次のようになります。  
  
  **SEH 例外のトリガー**  
**SEH \_\_except ブロックの実行** **\/EHsc** を使用してコードをコンパイルし、`CPPEX` を使用して `/DCPPEX` が定義されている場合 \(C\+\+ 例外がスローされる\)、`TestClass` デストラクターが実行され、出力は次のようになります。  
  
  **C\+\+ 例外のスロー**  
**TestClass\! の破棄  SEH \_\_except ブロックの実行**  **\/EHa** を使用してコードをコンパイルする場合、`TestClass` を使用して例外がスローされたか、または SEH を使用して例外をトリガーしたか \(`std::throw` が定義されたかどうか\) に関係なく、`CPPEX` デストラクターが実行されます。  出力は次のようになります。  
  
  **C\+\+ 例外のスロー**  
**TestClass\! の破棄  SEH \_\_except ブロックの実行**  詳細については、「[\/EH \(例外処理モデル\)](../build/reference/eh-exception-handling-model.md)」を参照してください。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [例外処理](../cpp/exception-handling-in-visual-cpp.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [\<exception\>](../standard-library/exception.md)   
 [エラーと例外の処理](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [構造化例外処理 \(Windows\)](http://msdn.microsoft.com/library/windows/desktop/ms680657.aspx)