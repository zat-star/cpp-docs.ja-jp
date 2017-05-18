---
title: _resetstkoflw | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _resetstkoflw
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- resetstkoflw
- _resetstkoflw
dev_langs:
- C++
helpviewer_keywords:
- resetstkoflw function
- stack overflow
- stack, recovering
- _resetstkoflw function
ms.assetid: 319529cd-4306-4d22-810b-2063f3ad9e14
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 16d166f205f026977673e39bd539b377496bdc0c
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="resetstkoflw"></a>_resetstkoflw
スタック オーバーフローから復元します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
  
int _resetstkoflw ( void );  
  
```  
  
## <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外、失敗した場合は 0。  
  
## <a name="remarks"></a>コメント  
 `_resetstkoflw` 関数は、スタック オーバーフローが発生した状態からプログラムを回復させ、実行中の操作を致命的な例外エラーが発生したとして失敗させるのではなく、続行できるようにします。 `_resetstkoflw` 関数を呼び出さなければ、前回の例外の後にガード ページは作成されません。 次にスタック オーバーフローが発生したときに例外は発生しないので、プロセスは警告なしで終了します。  
  
 アプリケーションのスレッドにより **EXCEPTION_STACK_OVERFLOW** の例外が発生した場合、そのスレッドによってスタックは破損したままの状態になります。 これは、スタックが破損しない **EXCEPTION_ACCESS_VIOLATION** や **EXCEPTION_INT_DIVIDE_BY_ZERO** などの他の例外とは対照的です。 プログラムが最初に読み込まれたときには、スタックには小さい値が設定されます。 その後、スタックはスレッドのニーズに対応して必要に応じて大きくなります。 これは、現在のスタックの末尾に PAGE_GUARD のアクセス権を使用してページを設定することによって実装されます。 詳細については、「[Creating Guard Pages](http://msdn.microsoft.com/library/windows/desktop/aa366549)」 (ガード ページの作成) をご覧ください。  
  
 コードによってスタック ポインターがこのページのアドレスをポイントすると、例外が発生し、システムは次の 3 つのことを実行します。  
  
-   ガード ページの PAGE_GUARD の保護を削除して、スレッドがメモリにデータを読み書きできるようにします。  
  
-   最後のページの下のページにある新しいガード ページを割り当てます。  
  
-   例外を発生させた命令を再実行します。  
  
 この方法では、システムがスレッドに対するスタック サイズを自動的にインクリメントできます。 プロセスの各スレッドには最大スタック サイズがあります。 スタック サイズはコンパイル時に [/STACK (Stack Allocations)](../../build/reference/stack-stack-allocations.md)、またはプロジェクトの .def ファイルの [STACKSIZE](../../build/reference/stacksize.md) ステートメントによって設定されます。  
  
 この最大スタック サイズを超えると、システムは次の 3 つのことを実行します。  
  
-   前述のようにガード ページの PAGE_GUARD の保護を削除します。  
  
-   最後のページの下に新しいガード ページの割り当てを試みます。 ただし、これは最大スタック サイズを超過しているため失敗します。  
  
-   例外を発生させて、スレッドが例外ブロックで処理できるようにします。  
  
 その時点ではスタックにガード ページがないことに注意してください。 次にプログラムによってスタックのサイズが最後まで拡張されると、この場合はガード ページがある必要があり、プログラムはスタックの末尾を越えて書き込みを行い、アクセス違反が発生します。  
  
 `_resetstkoflw` を呼び出して、スタック オーバーフロー例外の後で回復が行われるたびにガード ページを復元します。 この関数は、`__except` ブロックのメイン部分の内側から、または **__except** ブロックの外側から呼び出すことができます。 ただし、使用する必要がある場合には、いくつかの制限があります。 `_resetstkoflw` は次のものから絶対に呼び出さないでください。  
  
-   フィルター式。  
  
-   フィルター関数。  
  
-   フィルター関数から呼び出される関数。  
  
-   **catch** ブロック。  
  
-   A `__finally` ブロック。  
  
 これらの時点では、スタックは完全にはアンワインドされていません。  
  
 スタック オーバーフロー例外は構造化例外として (C++ 例外ではない) 生成されます。そのため、`_resetstkoflw` が通常の **catch** ブロックで役に立たなくなります。これはスタック オーバーフロー例外をキャッチできないためです。 ただし、[_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) を使用して C++ 例外をスローする構造化例外の変換を実装すると (2 番目の例のように)、スタック オーバーフロー例外によって C ++ 例外が発生します。これは C++ の catch ブロックで処理できます。  
  
 構造化例外変換関数によってスローされる例外から到達した C ++ catch ブロックでの **_resetstkoflw** の呼び出しは安全ではありません。 この場合、catch ブロックの前で消滅させられるオブジェクトに対してデストラクターが呼び出された場合でも、catch ブロックの外部に出るまでスタック領域は解放されず、スタック ポインターはリセットされません。 この関数は、スタック領域が解放され、スタック ポインターがリセットされるまで呼び出さないようにする必要があります。 したがって、catch ブロックが終了した後でのみ呼び出すようにします。 catch ブロックではできるだけ小さなスタック領域を使用するようにします。これは、前回のスタック オーバーフローから自身で回復しようとしている catch ブロックでスタック オーバーフローが発生すると回復できなくなり、catch ブロック内でのオーバーフローによって同じ catch ブロックによってハンドルされる例外がトリガーされてプログラムの応答が停止するおそれがあるためです。  
  
 **_resetstkoflw** が **__except** ブロック内などの適切な位置で使用されていても、エラーになる場合があります。 スタックのアンワインドを実行した後でも、スタックの最後のページに書き込みをしないで **_resetstkoflw** を実行するためのスタック領域が十分にない場合は、**_resetstkoflw** はスタックの最後のページをガード ページとしてリセットすることに失敗し、エラーを表す 0 を返します。 したがってこの関数を安全に使用するには、スタックを使用しても安全であると想定するのではなく、戻り値をチェックする必要があります。  
  
 構造化例外処理は検出されません、`STATUS_STACK_OVERFLOW`アプリケーションをコンパイルしたときに例外`/clr`(を参照してください[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md))。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_resetstkoflw`|\<malloc.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
 **ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のすべてのバージョンです。  
  
## <a name="example"></a>例  
 `_resetstkoflw` 関数の推奨する使用例を次に示します。  
  
```  
// crt_resetstkoflw.c  
// Launch program with and without arguments to observe  
// the difference made by calling _resetstkoflw.  
  
#include <malloc.h>  
#include <stdio.h>  
#include <windows.h>  
  
void recursive(int recurse)  
{  
   _alloca(2000);  
   if (recurse)  
      recursive(recurse);  
}  
  
// Filter for the stack overflow exception.  
// This function traps the stack overflow exception, but passes  
// all other exceptions through.   
int stack_overflow_exception_filter(int exception_code)  
{  
   if (exception_code == EXCEPTION_STACK_OVERFLOW)  
   {  
       // Do not call _resetstkoflw here, because  
       // at this point, the stack is not yet unwound.  
       // Instead, signal that the handler (the __except block)  
       // is to be executed.  
       return EXCEPTION_EXECUTE_HANDLER;  
   }  
   else  
       return EXCEPTION_CONTINUE_SEARCH;  
}  
  
int main(int ac)  
{  
   int i = 0;  
   int recurse = 1, result = 0;  
  
   for (i = 0 ; i < 10 ; i++)  
   {  
      printf("loop #%d\n", i + 1);  
      __try  
      {  
         recursive(recurse);  
  
      }  
  
      __except(stack_overflow_exception_filter(GetExceptionCode()))  
      {  
         // Here, it is safe to reset the stack.  
  
         if (ac >= 2)  
         {  
            puts("resetting stack overflow");  
            result = _resetstkoflw();  
         }  
      }  
  
      // Terminate if _resetstkoflw failed (returned 0)  
      if (!result)  
         return 3;  
   }  
  
   return 0;  
}  
```  
  
## <a name="sample-output"></a>出力例  
 プログラムの引数がありません:  
  
```  
loop #1  
```  
  
 プログラムはこれ以上のイテレーションを実行せずに応答を停止します。  
  
 プログラムの引数があります:  
  
```  
loop #1  
resetting stack overflow  
loop #2  
resetting stack overflow  
loop #3  
resetting stack overflow  
loop #4  
resetting stack overflow  
loop #5  
resetting stack overflow  
loop #6  
resetting stack overflow  
loop #7  
resetting stack overflow  
loop #8  
resetting stack overflow  
loop #9  
resetting stack overflow  
loop #10  
resetting stack overflow  
```  
  
### <a name="description"></a>説明  
 構造化例外が C++ 例外に変換されるプログラムにおける `_resetstkoflw` の推奨される使用法を次に示します。  
  
### <a name="code"></a>コード  
  
```  
// crt_resetstkoflw2.cpp  
// compile with: /EHa  
// _set_se_translator requires the use of /EHa  
#include <malloc.h>  
#include <stdio.h>  
#include <windows.h>  
#include <eh.h>  
  
class Exception { };  
  
class StackOverflowException : Exception { };  
  
// Because the overflow is deliberate, disable the warning that  
// this function will cause a stack overflow.  
#pragma warning (disable: 4717)  
void CauseStackOverflow (int i)  
{  
        // Overflow the stack by allocating a large stack-based array  
        // in a recursive function.  
        int a[10000];  
        printf("%d ", i);  
        CauseStackOverflow (i + 1);  
}  
  
void __cdecl SEHTranslator (unsigned int code, _EXCEPTION_POINTERS*)  
{  
   // For stack overflow exceptions, throw our own C++   
   // exception object.  
   // For all other exceptions, throw a generic exception object.  
   // Use minimal stack space in this function.  
   // Do not call _resetstkoflw in this function.  
  
   if (code == EXCEPTION_STACK_OVERFLOW)  
      throw StackOverflowException ( );  
   else  
      throw Exception( );  
}  
  
int main ( )  
{  
        bool stack_reset = false;  
        bool result = false;  
  
        // Set up a function to handle all structured exceptions,  
        // including stack overflow exceptions.  
        _set_se_translator (SEHTranslator);  
  
        try  
        {  
            CauseStackOverflow (0);  
        }  
        catch (StackOverflowException except)  
        {  
                // Use minimal stack space here.  
                // Do not call _resetstkoflw here.  
                printf("\nStack overflow!\n");  
                stack_reset = true;  
        }  
        catch (Exception except)  
        {  
                // Do not call _resetstkoflw here.  
                printf("\nUnknown Exception!\n");  
        }  
        if (stack_reset)  
        {  
          result = _resetstkoflw();  
          // If stack reset failed, terminate the application.  
          if (result == 0)  
             exit(1);  
        }  
  
        void* pv = _alloca(100000);  
        printf("Recovered from stack overflow and allocated 100,000 bytes"  
               " using _alloca.");  
  
   return 0;  
}  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24  
Stack overflow!  
Recovered from stack overflow and allocated 100,000 bytes using _alloca.  
```  
  
## <a name="see-also"></a>関連項目  
 [_alloca](../../c-runtime-library/reference/alloca.md)
