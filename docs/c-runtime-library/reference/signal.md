---
title: signal | Microsoft Docs
ms.custom: 
ms.date: 02/12/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- signal
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
- signal
dev_langs:
- C++
helpviewer_keywords:
- signal function
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 23eae404bf5f8e2227d68189938defb2308f5e6b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="signal"></a>signal

割り込みシグナル処理を設定します。

> [!IMPORTANT]
> このメソッドを使用して、テスト シナリオまたはデバッグ シナリオを除く、Microsoft ストアのアプリをシャット ダウンしないでください。 ストア アプリを閉じる方法はプログラムや UI はに従って許可されていません、 [Microsoft ストアのポリシー](http://go.microsoft.com/fwlink/?LinkId=865936)です。 詳細については、次を参照してください。 [UWP アプリのライフ サイクル](http://go.microsoft.com/fwlink/p/?LinkId=865934)です。

## <a name="syntax"></a>構文

```C
void __cdecl *signal(int sig, int (*func)(int, int));
```

### <a name="parameters"></a>パラメーター
_sig_  
シグナル値。

_func_  
2 番目のパラメーターは、実行される関数へのポインターです。 最初のパラメーターはシグナル値で、2 番目のパラメーターは、最初のパラメーターが SIGFPE のときに使用できるサブコードです。

## <a name="return-value"></a>戻り値

`signal` 指定されたシグナルに関連付けられている func の前の値を返します。 たとえば場合の前の値_func_が`SIG_IGN`、戻り値も`SIG_IGN`します。 戻り値 `SIG_ERR` はエラーを示します。その場合、`errno` は `EINVAL` に設定されます。

リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

`signal` 関数を使用すると、プロセスで、オペレーティング システムからの割り込みシグナルを処理する複数の方法から 1 つの方法を選択できます。 _Sig_引数は、割り込みを`signal`が応答シグナルで定義されている次のマニフェスト定数のいずれかにする必要があります。H.

|_sig_値|説明|
|-----------------|-----------------|
|`SIGABRT`|異常終了|
|`SIGFPE`|浮動小数点エラー|
|`SIGILL`|無効な命令|
|`SIGINT`|Ctrl + C シグナル|
|`SIGSEGV`|ストレージへの無効なアクセス|
|`SIGTERM`|終了要求|

場合_sig_は 1 つで、上記の値の無効なパラメーター ハンドラーが呼び出されるで定義されている[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`SIG_ERR` を返します。

既定では、`signal`の値に関係なく、終了コード 3 で呼び出し元のプログラムを終了_sig_です。

> [!NOTE]
> `SIGINT` はすべての Win32 アプリケーションでサポートされていません。 Ctrl + C 割り込みが発生すると、Win32 オペレーティング システムは、その割り込みを処理する専用の新しいスレッドを生成します。 これにより、UNIX のアプリケーションなどのシングル スレッド アプリケーションがマルチスレッドになり、予期しない動作が発生する可能性があります。

_Func_引数は、アドレスを記述したシグナル ハンドラーまたは定義済みの定数のいずれかに`SIG_DFL`または`SIG_IGN`信号で定義されています。H. 場合_func_関数は、指定したシグナルのシグナル ハンドラーとしてインストールされます。 シグナル ハンドラーのプロトタイプには、1 つの仮引数が必要です。 _sig_、型の`int`します。 オペレーティング システムは使用して実引数_sig_引数は、割り込みを生成したシグナルで割り込みが発生したときにします。 したがって、シグナル ハンドラーで (前の表の) 6 つのマニフェスト定数を使用して、発生した割り込みを特定し、適切なアクションを実行できます。 たとえば、呼び出す`signal`同じハンドラーを 2 つの異なるシグナルに割り当てるし、テストを 2 回、 _sig_受け取ったシグナルに基づいて異なるアクションを実行するハンドラーの引数。

浮動小数点例外用にテストしている場合 (`SIGFPE`)、 _func_をいくつかのマニフェスト定数のいずれか、省略可能な 2 番目の引数を受け取る関数を指して: 浮動小数点数で定義されています。H: フォームの`FPE_xxx`します。 `SIGFPE` シグナルが発生したときに、2 番目の引数の値をテストして、浮動小数点例外の種類を特定し、適切なアクションを実行できます。 この引数とその有効な値は Microsoft 拡張機能です。

値、浮動小数点例外用_func_シグナルを受け取ったときにリセットされません。 浮動小数点例外から回復するには、try/except 句で浮動小数点演算を囲みます。 [setjmp](../../c-runtime-library/reference/setjmp.md) と [longjmp](../../c-runtime-library/reference/longjmp.md) を使用して回復することもできます。 いずれの場合も、呼び出し元プロセスは実行を再開し、プロセスの浮動小数点状態を未定義のままにします。

シグナル ハンドラーが戻った場合、呼び出し元プロセスは、割り込みシグナルを受け取った位置の直後から実行を再開します。 この動作は、どの種類のシグナルまたは動作モードにも当てはまります。

指定された関数が実行される前に、値の_func_に設定されている`SIG_DFL`です。 次の割り込みシグナルは、間に行われる `SIG_DFL` の呼び出しで特に指定されない限り、`signal` に関する説明のとおりに処理されます。 この機能を使用して、呼び出された関数でシグナルをリセットできます。

シグナル ハンドラー ルーチンは、通常、割り込みの発生時に非同期的に呼び出されるので、実行時の操作が未完了で、不明な状態の場合は、シグナル ハンドラー関数が制御を取得することがあります。 次の一覧に、シグナル ハンドラー ルーチンで使用できる関数が決まる制限事項について説明します。

- 下位レベルのルーチンまたは STDIO.H I/O ルーチン (`printf`、`fread` など) を発行しない。

- ヒープ ルーチンまたはヒープ ルーチンを使用するルーチン (`malloc`、`_strdup`、`_putenv` など) を呼び出さない。 詳細については、「[malloc](../../c-runtime-library/reference/malloc.md)」を参照してください。

- システム コールを生成する関数 (`_getcwd`、`time` など) を使用しない。

- 使用しないでください`longjmp`割り込みが浮動小数点の例外が発生した場合を除き、(つまり、 _sig_は`SIGFPE`)。 この場合、最初に `_fpreset` への呼び出しを使用して浮動小数点パッケージを再初期化します。

- オーバーレイ ルーチンを使用しない。

関数を使用して `SIGFPE` 例外をトラップする場合は、浮動小数点コードをプログラムに含める必要があります。 プログラムに浮動小数点コードがなく、ランタイム ライブラリのシグナル処理コードが必要な場合は、次のように volatile double を宣言して、ゼロに初期化します。

`volatile double d = 0.0f;`

`SIGILL` シグナルと `SIGTERM` シグナルは Windows では生成されません。 これは、ANSI との互換性を維持するために用意されています。 したがって、`signal` を使用してこれらのシグナルのシグナル ハンドラーを設定できます。また、[raise](../../c-runtime-library/reference/raise.md) を呼び出してこれらのシグナルを明示的に生成することもできます。

`_exec` 関数または `_spawn` 関数を呼び出して作成し、開始したプロセスでは、シグナル設定が保持されません。 シグナル設定は、新しいプロセスでは既定値にリセットされます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`signal`|\<signal.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

次の例は、`signal` を使用してカスタム動作を `SIGABRT` シグナルに追加する方法を示しています。 中止動作の詳細については、「[_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md)」を参照してください。

```C
// crt_signal.c
// compile with: /EHsc /W4
// Use signal to attach a signal handler to the abort routine
#include <stdlib.h>
#include <signal.h>
#include <tchar.h>

void SignalHandler(int signal)
{
    if (signal == SIGABRT) {
        // abort signal handler code
    } else {
        // ...
    }
}

int main()
{
    typedef void (*SignalHandlerPointer)(int);

    SignalHandlerPointer previousHandler;
    previousHandler = signal(SIGABRT, SignalHandler);

    abort();
}
```

```Output
This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)  
[abort](../../c-runtime-library/reference/abort.md)  
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)  
[exit、_Exit、_exit](../../c-runtime-library/reference/exit-exit-exit.md)  
[_fpreset](../../c-runtime-library/reference/fpreset.md)  
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)  
