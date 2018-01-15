---
title: abort | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: abort
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
f1_keywords: Abort
dev_langs: C++
helpviewer_keywords:
- aborting current process
- abort function
- processes, aborting
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6577ca7927d42e12aa62ed100b9572b7270208f
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2018
---
# <a name="abort"></a>を呼び出してプログラム実行を終了する際、

現在のプロセスを中止し、エラー コードを返します。

> [!NOTE]
> Microsoft ストア アプリケーションをシャット ダウンはこのメソッドを使用しないまたは[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]アプリ、テスト シナリオまたはデバッグ シナリオでは可します。 ストア アプリを閉じる方法はプログラムや UI はに従って許可されていません、 [Microsoft ストアのポリシー](/legal/windows/agreements/store-policies)です。 詳細については、次を参照してください。 [UWP アプリのライフ サイクル](/windows/uwp/launch-resume/app-lifecycle)です。

## <a name="syntax"></a>構文

```c
void abort( void );
```

## <a name="return-value"></a>戻り値

`abort` は、呼び出し元のプロセスに制御を返しません。 既定では、中止シグナル ハンドラーが確認され、それが設定されている場合は `SIGABRT` が発生します。 その後 `abort` は、現在のプロセスを終了し、親プロセスに終了コードを返します。

## <a name="remarks"></a>コメント

**Microsoft 固有の仕様**

既定では、デバッグ ランタイム ライブラリを使用してアプリをビルドしている場合、`abort` ルーチンによってエラー メッセージが表示された後、`SIGABRT` が発生します。 コンソール モードで動作しているコンソール アプリの場合は、`STDERR` にメッセージが送信されます。 ウィンドウ モードで動作している Windows デスクトップ アプリとコンソール アプリでは、メッセージ ボックスにメッセージが表示されます。 メッセージを抑制するには、[_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md) を使用して `_WRITE_ABORT_MSG` フラグをクリアします。 表示されるメッセージは、使用しているランタイム環境のバージョンによって異なります。 Visual C の最新バージョンを使用してビルドされたアプリケーションでは、メッセージのようになります。

> R6010 - abort() が呼び出されました

C ランタイム ライブラリの以前のバージョンでは、次のメッセージが表示されました。

> このアプリケーションは、通常と異なる方法でランタイムにアプリケーションを中止するように要求しました。 詳細については、アプリケーションのサポート チームに問い合わせてください。

プログラムをデバッグ モードでコンパイルしている場合、メッセージ ボックスに **[中止]**、**[再試行]**、または **[無視]** のオプションが表示されます。 ユーザーが **[中止]** をクリックすると、プログラムが即座に終了し、終了コード 3 が返されます。 ユーザーが **[再試行]** をクリックすると、just-in-time デバッグが有効な場合はデバッガーが起動してデバッグが開始します。 ユーザーが **[無視]** をクリックすると、`abort` によって通常の処理が続けられます。

リテール ビルドとデバッグ ビルドのどちらの場合も、`abort` は次に、中止シグナル ハンドラーが設定されているかどうかを確認します。 既定以外のシグナル ハンドラーが設定されている場合、`abort` は `raise(SIGABRT)` を呼び出します。 `SIGABRT` シグナルに中止シグナル ハンドラー関数を関連付けるには、[signal](../../c-runtime-library/reference/signal.md) 関数を使用します。 ハンドラー関数では、カスタム動作 (リソースのクリーンアップや情報のログ記録など) を実行し、独自のエラー コードを発行してアプリを修了できます。 カスタムのシグナル ハンドラーが定義されていない場合、`abort` で `SIGABRT` 通知が発生しません。

既定では、デスクトップまたはコンソール アプリの非デバッグ ビルドで`abort`(災害復旧と呼ばれていました Windows エラー報告サービス メカニズム呼び出します。ワトソン博士) を起動してエラーを Microsoft に報告します。 この動作は、`_set_abort_behavior` を呼び出し、`_CALL_REPORTFAULT` フラグを設定するかマスクして、有効または無効にすることができます。 フラグが設定されていると、Windows でメッセージ ボックスが開き、「問題が発生したため、プログラムが正しく動作しなくなりました」などのテキストが表示されます。 ユーザーは **[デバッグ]** をクリックしてデバッガーを開始するか、**[プログラムの終了]** をクリックすることでオペレーティング システムで定義されているエラー コードを発行してアプリを終了できます。

Windows のエラー レポート ハンドラーが起動しない場合、`abort` は [_exit](../../c-runtime-library/reference/exit-exit-exit.md) を呼び出し、終了コード "3" を発行してプロセスを終了した後、親プロセスまたはオペレーティング システムに制御を戻します。 `_exit` は、ストリーム バッファーをフラッシュせず、`atexit`/`_onexit` 処理を行いません。

CRT デバッグの詳細については、「[CRT のデバッグ技術](/visualstudio/debugger/crt-debugging-techniques)」を参照してください。

**END Microsoft 固有の仕様**

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`abort`|\<process.h> または \<stdlib.h>|

## <a name="example"></a>例

次のプログラムはファイルを開こうとしますが、試みに失敗すると中止されます。

```C
// crt_abort.c
// compile with: /TC
// This program demonstrates the use of
// the abort function by attempting to open a file
// and aborts if the attempt fails.

#include  <stdio.h>
#include  <stdlib.h>

int main( void )
{
    FILE    *stream = NULL;
    errno_t err = 0;

    err = fopen_s(&stream, "NOSUCHF.ILE", "r" );
    if ((err != 0) || (stream == NULL))
    {
        perror( "File could not be opened" );
        abort();
    }
    else
    {
        fclose( stream );
    }
}
```

```Output
File could not be opened: No such file or directory
```

## <a name="see-also"></a>関連項目

[abort の使用](../../cpp/using-abort.md)  
[abort 関数](../../c-language/abort-function-c.md)  
[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)  
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)  
[exit、_Exit、_exit](../../c-runtime-library/reference/exit-exit-exit.md)  
[raise](../../c-runtime-library/reference/raise.md)  
[signal](../../c-runtime-library/reference/signal.md)  
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)  
[_DEBUG](../../c-runtime-library/debug.md)  
[_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md)  
