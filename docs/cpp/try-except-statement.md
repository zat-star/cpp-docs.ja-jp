---
title: "再試行のステートメントを除く |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- EXCEPTION_CONTINUE_SEARCH
- _exception_info
- __except
- EXCEPTION_CONTINUE_EXECUTION
- _exception_code
- __except_cpp
- _exception_info_cpp
- EXCEPTION_EXECUTE_HANDLER
- _abnormal_termination
dev_langs:
- C++
helpviewer_keywords:
- __try keyword [C++]
- EXCEPTION_CONTINUE_EXECUTION macro
- EXCEPTION_CONTINUE_SEARCH macro
- EXCEPTION_EXECUTE_HANDLER macro
- GetExceptionCode function
- try-catch keyword [C++], try-except keyword [C++]
- _exception_code keyword [C++]
- try-except keyword [C++]
- _exception_info keyword [C++]
- _abnormal_termination keyword [C++]
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: e7a9b4aebd0ae60feeedc64644d3e50b8859f7cf
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="try-except-statement"></a>try-except ステートメント
**Microsoft 固有の仕様**  
  
 次の構文は、try-except ステートメントを示しています。  
  
## <a name="syntax"></a>構文  
  
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
  
## <a name="remarks"></a>コメント  
 **を再試行してください-を除く**ステートメントは、C の Microsoft 拡張機能および C++ 言語を取得するために対象アプリケーションを有効にするは、通常プログラムの実行を終了するイベントが発生する可能性を制御します。 このようなイベントは例外と呼ばれ、例外を処理する機構は構造化例外処理と呼ばれます。  
  
 関連情報については、次を参照してください。、 [try-finally ステートメント](../cpp/try-finally-statement.md)です。  
  
 例外は、ハードウェア例外またはソフトウェア例外です。 アプリケーションがハードウェア例外またはソフトウェア例外から完全に回復できない場合でも、構造化例外処理はエラー情報を表示し、問題の診断に役立つアプリケーションの内部状態をトラップすることができます。 これは、簡単に再現できない断続的な問題の場合に特に便利です。  
  
> [!NOTE]
>  構造化例外処理では、C と C++ のソース ファイルの両方で Win32 を使用します。 ただし、特に C++ 用にデザインされたものではありません。 C++ 例外処理を使用して、コードの移植性を高めることができます。 また、C++ 例外処理は、任意の型の例外を処理できるという点で、より柔軟です。 C++ プログラムのことをお勧め、C++ 例外処理機構を使用すること ([try、catch、および throw](../cpp/try-throw-and-catch-statements-cpp.md)ステートメント)。  
  
 `__try` 句の後の複合ステートメントは、本体または保護されたセクションです。 `__except` 句の後の複合ステートメントは、例外ハンドラーです。 ハンドラーは、保護されたセクションの本体の実行中に例外が発生した場合に行われる一連の操作を指定します。 次のように実行されます。  
  
1.  保護されたセクションが実行されます。  
  
2.  保護されたセクションの実行中に例外が発生しなかった場合、実行は `__except` 句の後のステートメントから続行されます。  
  
3.  保護されたセクションの実行中に例外が発生した場合または任意のルーチンで、保護されたセクションを呼び出すと、 `__except` *式*(と呼ばれる、*フィルター*式) が評価されると、値例外の処理方法を決定します。 次の 3 つの値があります。  
  
     **EXCEPTION_CONTINUE_EXECUTION (-1)**例外を破棄します。 例外が発生した位置から実行を継続します。  
  
     **EXCEPTION_CONTINUE_SEARCH (0)**例外が認識されていません。 最初に **try-except** ステートメントを含むハンドラーを検索してから、次に優先順位が最も高いハンドラーについてスタックを検索し続けます。  
  
     **EXCEPTION_EXECUTE_HANDLER (1)**例外を認識します。 `__except` 複合ステートメントの実行によって例外ハンドラーに制御を移動した後、`__except` ブロックの次から実行を続行します。  
  
 _ _**を除く**式は C の式として評価される、単一の値、条件式演算子、またはコンマ演算子に制限します。 より広範な処理が必要な場合、前に挙げた 3 つの値の 1 つを返すルーチンを式で呼び出すことができます。  
  
 各アプリケーションが独自の例外ハンドラーを持つ場合があります。  
  
 `__try` ステートメント内に移動することはできませんが、外に移動することはできます。 実行中のプロセスが終了した場合、例外ハンドラーは呼び出されませんが、**を再試行してください-を除く**ステートメントです。  
  
 詳細については、サポート技術情報「HOW TO: Trap Stack Overflow in a Visual C++ Application (Q315937)」を参照してください。  
  
## <a name="the-leave-keyword"></a>__leave キーワード  
 `__leave` キーワードは、`try-except` ステートメントの保護されたセクション内でのみ有効であり、その効果は保護されたセクションの末尾に移動することです。 実行は、例外ハンドラーの後の最初のステートメントから続行されます。  
  
 `goto` ステートメントでも、保護されたセクションの外部に移動できます。スタック アンワインドが発生しないため `try-finally` ステートメントのようにパフォーマンスが低下しません。 ただし、保護されたセクションが大きい場合や複雑な場合はプログラミングの間違いを犯す可能性を低くするため、`__leave` ステートメントではなく `goto` キーワードを使用することをお勧めします。  
  
### <a name="structured-exception-handling-intrinsic-functions"></a>構造化例外処理の組み込み関数  
 構造化例外処理で使用する使用可能な 2 つの組み込み関数を提供する、**を再試行してください-を除く**ステートメント: **GetExceptionCode**と**GetExceptionInformation**.  
  
 **GetExceptionCode**例外のコード (32 ビット整数) を返します。  
  
 組み込み関数**GetExceptionInformation**例外に関する追加情報を含む構造体へのポインターを返します。 このポインターを使用して、ハードウェア例外のときに存在していたコンピューターの状態にアクセスできます。 構造は、次のとおりです。  
  
```  
struct _EXCEPTION_POINTERS {  
      EXCEPTION_RECORD *ExceptionRecord,  
      CONTEXT *ContextRecord }  
```  
  
 ポインター型 _**EXCEPTION_RECORD**と\_**コンテキスト**EXCPT にインクルード ファイルで定義されます。H.  
  
 使用することができます**GetExceptionCode**例外ハンドラー内で。 ただし、使用することができます**GetExceptionInformation**例外フィルター式内でのみです。 これが示す情報は、一般的にスタックにあり、制御が例外ハンドラーに移されると使用できなくなります。  
  
 組み込み関数**AbnormalTermination**は終了ハンドラー内で使用できます。 `try-finally` ステートメント本体が順次終了した場合は 0 を返します。 その他の場合は、1 を返します。  
  
 EXCPT.H は、組み込み関数の代替名を次のように定義しています。  
  
 **GetExceptionCode**は _exception_code と等価  
  
 **GetExceptionInformation**は _exception_info と等価  
  
 **AbnormalTermination**は _abnormal_termination と等価  
  
## <a name="example"></a>例  
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
  
 `int* p = 0x00000000;   // pointer to NULL`  
  
 `puts("hello");`  
  
 `__try{`  
  
 `puts("in try");`  
  
 `__try{`  
  
 `puts("in try");`  
  
 `*p = 13;    // causes an access violation exception;`  
  
 `}__finally{`  
  
 `puts("in finally. termination: ");`  
  
 `puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");`  
  
 `}`  
  
 `}__except(filter(GetExceptionCode(), GetExceptionInformation())){`  
  
 `puts("in except");`  
  
 `}`  
  
 `puts("world");`  
  
 `}`  
  
## <a name="output"></a>出力  
  
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
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)   
 [構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)
