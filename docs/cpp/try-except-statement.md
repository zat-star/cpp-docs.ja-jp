---
title: "try-except ステートメント | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_abnormal_termination_cpp"
  - "_exception_code_cpp"
  - "EXCEPTION_CONTINUE_SEARCH"
  - "_exception_info"
  - "__except"
  - "EXCEPTION_CONTINUE_EXECUTION"
  - "_exception_code"
  - "__except_cpp"
  - "_exception_info_cpp"
  - "EXCEPTION_EXECUTE_HANDLER"
  - "_abnormal_termination"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__try キーワード [C++]"
  - "_abnormal_termination キーワード [C++]"
  - "_exception_code キーワード [C++]"
  - "_exception_info キーワード [C++]"
  - "EXCEPTION_CONTINUE_EXECUTION マクロ"
  - "EXCEPTION_CONTINUE_SEARCH マクロ"
  - "EXCEPTION_EXECUTE_HANDLER マクロ"
  - "GetExceptionCode 関数"
  - "try-catch キーワード [C++], try-except キーワード [C++]"
  - "try-except キーワード [C++]"
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# try-except ステートメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 次の構文は、try\-except ステートメントを示しています。  
  
## 構文  
  
```  
  
      __try   
{  
   // guarded code  
}  
__except ( expression )  
{  
   // exception handler code  
}  
```  
  
## 解説  
 **try\-except** ステートメントは、C および C\+\+ 言語に対する Microsoft の拡張機能であり、通常はプログラムの実行を終了するイベントが発生したときに、ターゲット アプリケーションが制御を取得できるようにします。  このようなイベントは例外と呼ばれ、例外を処理する機構は構造化例外処理と呼ばれます。  
  
 関連情報については、「[try\-finally ステートメント](../cpp/try-finally-statement.md)」を参照してください。  
  
 例外は、ハードウェア例外またはソフトウェア例外です。  アプリケーションがハードウェア例外またはソフトウェア例外から完全に回復できない場合でも、構造化例外処理はエラー情報を表示し、問題の診断に役立つアプリケーションの内部状態をトラップすることができます。  これは、簡単に再現できない断続的な問題の場合に特に便利です。  
  
> [!NOTE]
>  構造化例外処理では、C と C\+\+ のソース ファイルの両方で Win32 を使用します。  ただし、特に C\+\+ 用にデザインされたものではありません。  C\+\+ 例外処理を使用して、コードの移植性を高めることができます。  また、C\+\+ 例外処理は、任意の型の例外を処理できるという点で、より柔軟です。  C\+\+ プログラムでは、C\+\+ 例外処理機構 \([try、catch、および throw ステートメント](../cpp/try-throw-and-catch-statements-cpp.md)\) を使用することをお勧めします。  
  
 `__try` 句の後の複合ステートメントは、本体または保護されたセクションです。  `__except` 句の後の複合ステートメントは、例外ハンドラーです。  ハンドラーは、保護されたセクションの本体の実行中に例外が発生した場合に行われる一連の操作を指定します。  次のように実行されます。  
  
1.  保護されたセクションが実行されます。  
  
2.  保護されたセクションの実行中に例外が発生しなかった場合、実行は `__except` 句の後のステートメントから続行されます。  
  
3.  保護されたセクションの実行中に、または保護されたセクションで呼び出された任意のルーチンで、例外が発生した場合、`__except` *expression* \(フィルター式と呼ばれる\) が評価され、その値によって例外の処理方法が決定されます。  次の 3 つの値があります。  
  
     **EXCEPTION\_CONTINUE\_EXECUTION \(–1\)** 例外を破棄します。  例外が発生した位置から実行を継続します。  
  
     **EXCEPTION\_CONTINUE\_SEARCH \(0\)** 例外が認識されていません。  最初に **try\-except** ステートメントを含むハンドラーを検索してから、次に優先順位が最も高いハンドラーについてスタックを検索し続けます。  
  
     **EXCEPTION\_EXECUTE\_HANDLER \(1\)** 例外が認識されています。  `__except` 複合ステートメントの実行によって例外ハンドラーに制御を移動した後、`__except` ブロックの次から実行を続行します。  
  
 \_\_**except** 式は C の式として評価されるため、1 つの値、条件式演算子、またはコンマ演算子に制限されます。  より広範な処理が必要な場合、前に挙げた 3 つの値の 1 つを返すルーチンを式で呼び出すことができます。  
  
 各アプリケーションが独自の例外ハンドラーを持つ場合があります。  
  
 `__try` ステートメント内に移動することはできませんが、外に移動することはできます。  例外ハンドラーは、プロセスが **try\-except** ステートメントの実行中に終了された場合は呼び出されません。  
  
 詳細については、サポート技術情報「HOW TO: Trap Stack Overflow in a Visual C\+\+ Application \(Q315937\)」を参照してください。  
  
## \_\_leave キーワード  
 `__leave` キーワードは、`try-except` ステートメントの保護されたセクション内でのみ有効であり、その効果は保護されたセクションの末尾に移動することです。  実行は、例外ハンドラーの後の最初のステートメントから続行されます。  
  
 `goto` ステートメントでも、保護されたセクションの外部に移動できます。スタック アンワインドが発生しないため `try-finally` ステートメントのようにパフォーマンスが低下しません。  ただし、保護されたセクションが大きい場合や複雑な場合はプログラミングの間違いを犯す可能性を低くするため、`goto` ステートメントではなく `__leave` キーワードを使用することをお勧めします。  
  
### 構造化例外処理の組み込み関数  
 構造化例外処理には、**try\-except** ステートメントで使用できる 2 つの組み込み関数、**GetExceptionCode** および **GetExceptionInformation** が用意されています。  
  
 **GetExceptionCode** は、例外のコード \(32 ビット整数\) を返します。  
  
 組み込み関数 **GetExceptionInformation** は、例外に関する追加情報を含む構造体へのポインターを返します。  このポインターを使用して、ハードウェア例外のときに存在していたコンピューターの状態にアクセスできます。  構造は、次のとおりです。  
  
```  
struct _EXCEPTION_POINTERS {  
      EXCEPTION_RECORD *ExceptionRecord,  
      CONTEXT *ContextRecord }  
```  
  
 ポインター型 \_**EXCEPTION\_RECORD** と \_**CONTEXT** は、インクルード ファイル EXCPT.H で定義されています。  
  
 例外ハンドラー内で **GetExceptionCode** を使用できます。  ただし、**GetExceptionInformation** は例外のフィルター式内でのみ使用できます。  これが示す情報は、一般的にスタックにあり、制御が例外ハンドラーに移されると使用できなくなります。  
  
 組み込み関数 **AbnormalTermination** は終了ハンドラー内で使用できます。  `try-finally` ステートメント本体が順次終了した場合は 0 を返します。  その他の場合は、1 を返します。  
  
 EXCPT.H は、組み込み関数の代替名を次のように定義しています。  
  
 **GetExceptionCode** は \_exception\_code と等価です。  
  
 **GetExceptionInformation** は \_exception\_info と等価です。  
  
 **AbnormalTermination** は \_abnormal\_termination と等価です。  
  
## 使用例  
 `// exceptions_try_except_Statement.cpp`  
  
 `// Example of try-except and try-finally statements`  
  
 `#include <stdio.h>`  
  
 `#include <windows.h> // for EXCEPTION_ACCESS_VIOLATION`  
  
 `#include <excpt.h>`  
  
 `int filter(unsigned int code, struct _EXCEPTION_POINTERS *ep) {`  
  
 `puts("in filter.");`  
  
 `if (code == EXCEPTION_ACCESS_VIOLATION) {`  
  
 `puts("caught AV as expected.");`  
  
 `return EXCEPTION_EXECUTE_HANDLER;`  
  
 `}`  
  
 `else {`  
  
 `puts("didn't catch AV, unexpected.");`  
  
 `return EXCEPTION_CONTINUE_SEARCH;`  
  
 `};`  
  
 `}`  
  
 `int main()`  
  
 `{`  
  
 `int* p = 0x00000000;   // pointer to NULL`  
  
 `puts("hello");`  
  
 `__try{`  
  
 `puts("in try");`  
  
 `__try{`  
  
 `puts("in try");`  
  
 `*p = 13;    // causes an access violation exception;`  
  
 `}__finally{`  
  
 `puts("in finally. termination: ");`  
  
 `puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");`  
  
 `}`  
  
 `}__except(filter(GetExceptionCode(), GetExceptionInformation())){`  
  
 `puts("in except");`  
  
 `}`  
  
 `puts("world");`  
  
 `}`  
  
## 出力  
  
```  
hello  
in try  
in try  
in filter.  
caught AV as expected.  
in finally. termination:  
        abnormal  
in except  
world  
```  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)   
 [構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)