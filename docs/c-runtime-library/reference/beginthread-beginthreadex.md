---
title: "_beginthread、_beginthreadex | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _beginthread
- _beginthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- beginthread
- _beginthread
- beginthreadex
- _beginthreadex
dev_langs:
- C++
helpviewer_keywords:
- _beginthread function
- threading [C++], creating threads
- beginthreadex function
- _beginthreadex function
- beginthread function
ms.assetid: 0df64740-a978-4358-a88f-fb0702720091
caps.latest.revision: 36
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 3c556e6460f1a39bab23f2612cbf820e284d7605
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="beginthread-beginthreadex"></a>_beginthread、_beginthreadex
スレッドを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
uintptr_t _beginthread( // NATIVE CODE  
   void( __cdecl *start_address )( void * ),  
   unsigned stack_size,  
   void *arglist   
);  
uintptr_t _beginthread( // MANAGED CODE  
   void( __clrcall *start_address )( void * ),  
   unsigned stack_size,  
   void *arglist   
);  
uintptr_t _beginthreadex( // NATIVE CODE  
   void *security,  
   unsigned stack_size,  
   unsigned ( __stdcall *start_address )( void * ),  
   void *arglist,  
   unsigned initflag,  
   unsigned *thrdaddr   
);  
uintptr_t _beginthreadex( // MANAGED CODE  
   void *security,  
   unsigned stack_size,  
   unsigned ( __clrcall *start_address )( void * ),  
   void *arglist,  
   unsigned initflag,  
   unsigned *thrdaddr   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `start_address`  
 新しいスレッドの実行を開始するルーチンの開始アドレス。 `_beginthread`では、 [__cdecl](../../cpp/cdecl.md) (ネイティブ コードの場合) または [__clrcall](../../cpp/clrcall.md) (マネージ コードの場合) の呼び出し規則を使用します。`_beginthreadex`では、 [__stdcall](../../cpp/stdcall.md) (ネイティブ コードの場合) または [__clrcall](../../cpp/clrcall.md) (マネージ コードの場合) の呼び出し規則を使用します。  
  
 `stack_size`  
 新しいスレッドのスタック サイズまたは 0。  
  
 `arglist`  
 新しいスレッドに渡される引数リストまたは NULL。  
  
 `Security`  
 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) 構造体へのポインター。この構造体は、返されたハンドルを子プロセスが継承できるかどうかを決定します。 `Security` が NULL の場合、ハンドルは継承できなくなります。 Windows 95 アプリケーションの場合は、NULL を指定する必要があります。  
  
 `initflag`  
 新しいスレッドの初期状態を制御するフラグ。 即時に実行するには `initflag` を `0` に設定し、一時停止状態でスレッドを作成するには `CREATE_SUSPENDED` に設定します。スレッドを実行するには、 [ResumeThread](http://msdn.microsoft.com/library/windows/desktop/ms685086.aspx) を使用します。 `initflag` をスタックの初期予約サイズ (バイト単位) として使用するには、 `STACK_SIZE_PARAM_IS_A_RESERVATION` を `stack_size` フラグに設定します。このフラグが指定されていない場合、 `stack_size` によってコミット サイズが指定されます。  
  
 `thrdaddr`  
 スレッド識別子を受け取る 32 ビット変数へのポインター。 NULL の場合は使用されません。  
  
## <a name="return-value"></a>戻り値  
 成功すると、各関数は新しく作成されたスレッドのハンドルを返します。ただし、新しく作成されたスレッドの終了が早すぎる場合、 `_beginthread` は有効なハンドルを返さないことがあります (「解説」の説明を参照)。エラーが発生すると、`_beginthread` は -1L を返します。このとき `errno` は、スレッドの数が多すぎる場合は `EAGAIN` に設定され、引数が無効であるかスタック サイズが不適切な場合は `EINVAL` に設定されます。また、リソース不足 (メモリ不足など) の場合は `EACCES` に設定されます。 エラーが発生すると、 `_beginthreadex` は 0 を返します。このとき `errno` と `_doserrno` が設定されます。  
  
 `startaddress` が NULL の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、-1 を返します。  
  
 これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
 `uintptr_t` の詳細については、「[基本データ型](../../c-runtime-library/standard-types.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_beginthread` 関数は、 `start_address`で指定されるルーチンの実行を開始するスレッドを作成します。 `start_address` にあるルーチンは、 `__cdecl` (ネイティブ コードの場合) または `__clrcall` (マネージ コードの場合) の呼び出し規約を使用する必要があり、戻り値を持つことはできません。 スレッドは、ルーチンから戻ると自動的に終了します。 スレッドの詳細については、「[旧形式のコードのためのマルチスレッド サポート (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)」を参照してください。  
  
 `_beginthreadex` は、`_beginthread` よりも Win32[ CreateThread ](http://msdn.microsoft.com/library/windows/desktop/ms682453.aspx) API に似ています。 `_beginthreadex` は、次の点で `_beginthread` と異なります。  
  
-   `_beginthreadex` には、 `initflag`、 `security`、および `threadaddr`の 3 つの追加パラメーターがあります。 セキュリティを指定し、一時停止状態で新しいスレッドを作成できます。新しいスレッドには、スレッド識別子 `thrdaddr`を使用してアクセスできます。  
  
-   `start_address` に渡される `_beginthreadex` のルーチンは、 `__stdcall` (ネイティブ コードの場合) または `__clrcall` (マネージ コードの場合) の呼び出し規約を使用する必要があり、スレッドの終了コードを返す必要があります。  
  
-   `_beginthreadex` は、エラーの発生時に -1L ではなく 0 を返します。  
  
-   `_beginthreadex` を使用して作成したスレッドは、 [_endthreadex](../../c-runtime-library/reference/endthread-endthreadex.md)の呼び出しで終了します。  
  
 `_beginthreadex` 関数は、スレッドの作成において `_beginthread` 関数よりも制御を詳細に行うことができます。 また、 `_endthreadex` 関数も、より柔軟性があります。 たとえば、 `_beginthreadex`では、セキュリティ情報の使用、スレッドの初期状態 (実行中または一時停止中) の設定、新しく作成されたスレッドのスレッド識別子の取得を行うことができます。 また、 `_beginthreadex` が返すスレッド ハンドルを同期 API と共に使用することもできます。 `_beginthread`では使用できません。  
  
 `_beginthreadex` よりも `_beginthread`を使用した方が安全です。 `_beginthread` によって生成されたスレッドの終了が早すぎると、 `_beginthread` の呼び出し元に返されるハンドルが無効になる可能性や、別のスレッドを指す可能性があります。 しかし、 `_beginthreadex` から返されるハンドルは `_beginthreadex`の呼び出し元で閉じられる必要があるため、 `_beginthreadex` がエラーを返さなかった場合には確実にハンドルが有効です。  
  
 [_endthread](../../c-runtime-library/reference/endthread-endthreadex.md) または `_endthreadex` を明示的に呼び出してスレッドを終了できます。ただし、 `_endthread` または `_endthreadex` は、パラメーターとして渡されたルーチンからスレッドが戻ると自動的に呼び出されます。 `_endthread` または `_endthreadex` を呼び出してスレッドを終了すると、スレッドに割り当てられていたリソースを確実に解放できます。  
  
 `_endthread` は、スレッド ハンドルを自動的に終了しますが、 `_endthreadex` は自動的に終了しません。 このため、 `_beginthread` および `_endthread`を使用するときには、Win32 [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) API を呼び出してスレッド ハンドルを明示的に終了しないでください。 この動作は、Win32 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) API とは異なります。  
  
> [!NOTE]
>  Libcmt.lib にリンクされている実行可能ファイルでは、Win32 の `ExitThread` API を呼び出さないでください。呼び出すと、割り当てられたリソースをランタイム システムで再利用することができなくなります。 `_endthread` と `_endthreadex` は、割り当てられているスレッド リソースを解放し、 `ExitThread`を呼び出します。  
  
 `_beginthread` または `_beginthreadex` が呼び出されると、オペレーティング システムがスタックの割り当てを処理します。したがって、スレッド スタックのアドレスをこれらの関数に渡す必要はありません。 また、引数 `stack_size` に 0 を指定すると、オペレーティング システムはメイン スレッドに対して指定したスタックと同じ値を使用します。  
  
 `arglist` は新しく作成したスレッドに渡すパラメーターです。 通常、文字列などのデータ項目のアドレスを指定します。 `arglist` には、不要な場合は NULL を設定できますが、 `_beginthread` と `_beginthreadex` には、新しいスレッドに渡す何らかの値を設定する必要があります。 いずれかのスレッドが `abort`、 `exit`、 `_exit`、または `ExitProcess`を呼び出すと、すべてのスレッドが終了します。  
  
 新しいスレッドのロケールは親スレッドから継承されます。 [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md) の呼び出しにより、スレッドごとのロケールが (グローバルまたは新しいスレッドのみに対して) 有効になっている場合は、スレッドで `setlocale` または `_wsetlocale`を呼び出すことで、そのスレッドのロケールを親とは関係なく変更できます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
 混合コードと純粋なコードでは、 `_beginthread` と `_beginthreadex` にはそれぞれ 2 つのオーバーロードがあります。1 つはネイティブの呼び出し規約関数ポインターを受け取り、もう 1 つは `__clrcall` 関数ポインターを受け取ります。 最初のオーバーロードは、アプリケーション ドメインセーフではなく、以降もそうなることはありません。 混合コードまたは純粋なコードを記述する場合、新しいスレッドがマネージ リソースにアクセスする前に確実に正しいアプリケーション ドメインに入るようにする必要があります。 そのためには、[call_in_appdomain 関数](../../dotnet/call-in-appdomain-function.md)などを使用します。 2 番目のオーバーロードはアプリケーション ドメイン セーフであり、新しく作成されたスレッドは、必ず `_beginthread` または `_beginthreadex`の呼び出し元のアプリケーション ドメインで終了します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_beginthread`|\<process.h>|  
|`_beginthreadex`|\<process.h>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md) のマルチスレッド バージョンのみ。  
  
 `_beginthread` または `_beginthreadex`を使用するには、アプリケーションをマルチスレッドの C ラインタイム ライブラリにリンクする必要があります。  
  
## <a name="example"></a>例  
 `_beginthread` および `_endthread`の使用例は、次のようになります。  
  
```  
// crt_BEGTHRD.C  
// compile with: /MT /D "_X86_" /c  
// processor: x86  
#include <windows.h>  
#include <process.h>    /* _beginthread, _endthread */  
#include <stddef.h>  
#include <stdlib.h>  
#include <conio.h>  
  
void Bounce( void * );  
void CheckKey( void * );  
  
// GetRandom returns a random integer between min and max.  
#define GetRandom( min, max ) ((rand() % (int)(((max) + 1) - (min))) + (min))  
// GetGlyph returns a printable ASCII character value  
#define GetGlyph( val ) ((char)((val + 32) % 93 + 33))  
  
BOOL repeat = TRUE;                 // Global repeat flag   
HANDLE hStdOut;                     // Handle for console window  
CONSOLE_SCREEN_BUFFER_INFO csbi;    // Console information structure  
  
int main()  
{  
    int param = 0;  
    int * pparam = &param;  
  
    // Get display screen's text row and column information.  
    hStdOut = GetStdHandle( STD_OUTPUT_HANDLE );  
    GetConsoleScreenBufferInfo( hStdOut, &csbi );  
  
    // Launch CheckKey thread to check for terminating keystroke.  
    _beginthread( CheckKey, 0, NULL );  
  
    // Loop until CheckKey terminates program or 1000 threads created.   
    while( repeat && param < 1000 )  
    {  
        // launch another character thread.  
        _beginthread( Bounce, 0, (void *) pparam );  
  
        // increment the thread parameter  
        param++;  
  
        // Wait one second between loops.  
        Sleep( 1000L );  
    }  
}  
  
// CheckKey - Thread to wait for a keystroke, then clear repeat flag.  
void CheckKey( void * ignored )  
{  
    _getch();  
    repeat = 0;    // _endthread implied  
}  
  
// Bounce - Thread to create and and control a colored letter that moves  
// around on the screen.  
//  
// Params: parg - the value to create the character from  
void Bounce( void * parg )  
{  
    char       blankcell = 0x20;  
    CHAR_INFO  ci;  
    COORD      oldcoord, cellsize, origin;  
    DWORD      result;  
    SMALL_RECT region;  
  
    cellsize.X = cellsize.Y = 1;  
    origin.X = origin.Y = 0;  
  
    // Generate location, letter and color attribute from thread argument.  
    srand( _threadid );  
    oldcoord.X = region.Left = region.Right =   
        GetRandom(csbi.srWindow.Left, csbi.srWindow.Right - 1);  
    oldcoord.Y = region.Top = region.Bottom =   
        GetRandom(csbi.srWindow.Top, csbi.srWindow.Bottom - 1);  
    ci.Char.AsciiChar = GetGlyph(*((int *)parg));  
    ci.Attributes = GetRandom(1, 15);  
  
    while (repeat)  
    {  
        // Pause between loops.  
        Sleep( 100L );  
  
        // Blank out our old position on the screen, and draw new letter.  
        WriteConsoleOutputCharacterA(hStdOut, &blankcell, 1, oldcoord, &result);  
        WriteConsoleOutputA(hStdOut, &ci, cellsize, origin, &region);  
  
        // Increment the coordinate for next placement of the block.  
        oldcoord.X = region.Left;  
        oldcoord.Y = region.Top;  
        region.Left = region.Right += GetRandom(-1, 1);  
        region.Top = region.Bottom += GetRandom(-1, 1);  
  
        // Correct placement (and beep) if about to go off the screen.  
        if (region.Left < csbi.srWindow.Left)  
            region.Left = region.Right = csbi.srWindow.Left + 1;  
        else if (region.Right >= csbi.srWindow.Right)  
            region.Left = region.Right = csbi.srWindow.Right - 2;  
        else if (region.Top < csbi.srWindow.Top)  
            region.Top = region.Bottom = csbi.srWindow.Top + 1;  
        else if (region.Bottom >= csbi.srWindow.Bottom)  
            region.Top = region.Bottom = csbi.srWindow.Bottom - 2;  
  
        // If not at a screen border, continue, otherwise beep.  
        else  
            continue;  
        Beep((ci.Char.AsciiChar - 'A') * 100, 175);  
    }  
    // _endthread given to terminate  
    _endthread();  
}  
```  
  
 任意のキーを押してサンプル アプリケーションを終了します。  
  
## <a name="example"></a>例  
 `_beginthreadex` から返されたスレッド ハンドルを同期 API [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx)と共に使用する方法を次のサンプル コードで示します。 メイン スレッドは、2 番目のスレッドが終了するのを待って処理を継続します。 2 番目のスレッドが `_endthreadex`を呼び出すと、2 番目のスレッドのスレッド オブジェクトがシグナル状態になります。 これにより、1 番目のスレッドの実行が継続されます。 `_beginthread` および `_endthread`では、継続できません。 `_endthread` は `CloseHandle`を呼び出して、シグナル状態になる前にスレッド オブジェクトを破棄するためです。  
  
```  
// crt_begthrdex.cpp  
// compile with: /MT  
#include <windows.h>  
#include <stdio.h>  
#include <process.h>  
  
unsigned Counter;   
unsigned __stdcall SecondThreadFunc( void* pArguments )  
{  
    printf( "In second thread...\n" );  
  
    while ( Counter < 1000000 )  
        Counter++;  
  
    _endthreadex( 0 );  
    return 0;  
}   
  
int main()  
{   
    HANDLE hThread;  
    unsigned threadID;  
  
    printf( "Creating second thread...\n" );  
  
    // Create the second thread.  
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc, NULL, 0, &threadID );  
  
    // Wait until second thread terminates. If you comment out the line  
    // below, Counter will not be correct because the thread has not  
    // terminated, and Counter most likely has not been incremented to  
    // 1000000 yet.  
    WaitForSingleObject( hThread, INFINITE );  
    printf( "Counter should be 1000000; it is-> %d\n", Counter );  
    // Destroy the thread object.  
    CloseHandle( hThread );  
}  
```  
  
```Output  
Creating second thread...  
In second thread...  
Counter should be 1000000; it is-> 1000000  
```  
  
## <a name="see-also"></a>関連項目  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [_endthread、_endthreadex](../../c-runtime-library/reference/endthread-endthreadex.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [exit、_Exit、_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)
