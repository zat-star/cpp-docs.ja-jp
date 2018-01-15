---
title: "exit、_Exit、_exit | Microsoft ドキュメント"
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _exit
- exit
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
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
dev_langs: C++
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dbb54b756363da2069bbc4bface4e971fcab91e4
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2018
---
# <a name="exit-exit-exit"></a>終了、_Exit、_exit

呼び出しプロセスを終了します。 `exit` 関数はクリーンアップ後に呼び出しプロセスを終了させます。一方、 `_exit` と `_Exit` は直ちに終了させます。

> [!NOTE]
> このメソッドを使用して、テスト シナリオまたはデバッグ シナリオにを除き、ユニバーサル Windows プラットフォーム (UWP) アプリをシャット ダウンしないでください。 ストア アプリを閉じる方法はプログラムや UI はに従って許可されていません、 [Microsoft ストアのポリシー](/legal/windows/agreements/store-policies)です。 詳細については、次を参照してください。 [UWP アプリのライフ サイクル](/windows/uwp/launch-resume/app-lifecycle)です。 Windows 10 アプリについて詳しくは、「 [Windows 10 アプリの使用方法のガイド](http://go.microsoft.com/fwlink/p/?linkid=619133)」をご覧ください。

## <a name="syntax"></a>構文

```C
void exit(
   int const status
);
void _Exit(
   int const status
);
void _exit( 
   int const status
);
```

### <a name="parameters"></a>パラメーター

_status_  
終了ステータス コード。

## <a name="remarks"></a>コメント

`exit`関数、 `_Exit` 関数、 `_exit` 関数は呼び出しプロセスを終了します。 `exit` 関数はスレッド ローカル オブジェクトのデストラクターを呼び出してから、 `atexit` と `_onexit`によって登録された関数を、後入れ先出し (LIFO) の順序で呼び出し、プロセスが終了する前にすべてのファイル バッファーをフラッシュします。 `_Exit` 関数と `_exit` 関数は、スレッド ローカル オブジェクトの破棄も、 `atexit` や `_onexit` 関数の処理もせず、ストリーム バッファーのフラッシュもしないでプロセスを終了します。

`exit`、`_Exit`と`_exit`呼び出しは、値の値を返しません_ステータス_ある場合は、プロセスが終了した後で、ホスト環境または呼び出し元プロセスの待機に使用可能になります。 呼び出し元のセットでは通常、_ステータス_値を 0 に通常の終了を示すため、または他のエラーを示す値。 _ステータス_値は、オペレーティング システムのバッチ コマンドを使用可能な`ERRORLEVEL`、2 つの定数のいずれかで表されます: `EXIT_SUCCESS`、0 の値を表すまたは`EXIT_FAILURE`1 の値を表します。

`exit`、 `_Exit`、 `_exit`、 `quick_exit`、 `_cexit`、 `_c_exit` 関数は次のように動作します。

|関数|説明|
|--------------|-----------------|
|`exit`|完全な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|`_Exit`|最低限の C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|`_exit`|最低限の C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|`quick_exit`|高速な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|`_cexit`|完全な C ライブラリの終了処理を実行し、呼び出し元に戻ります。 プロセスを終了しません。|
|`_c_exit`|最低限の C ライブラリの終了処理を実行し、呼び出し元に戻ります。 プロセスを終了しません。|

`exit`関数、  `_Exit` 関数、または `_exit` 関数を呼び出す場合、呼び出し時に存在する一時オブジェクトまたは自動オブジェクトのデストラクターは呼び出されません。 自動オブジェクトは、関数で定義されている非静的ローカル オブジェクトです。 一時オブジェクトは、関数呼び出しによって返される値など、コンパイラによって作成されるオブジェクトです。 呼び出す前に自動オブジェクトを破棄する`exit`、 `_Exit`、または`_exit`、明示的に次のように、オブジェクトのデストラクターを呼び出します。

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

`DLL_PROCESS_ATTACH` から `exit` を呼び出すために `DllMain`を使用しないでください。 終了する、`DLLMain`関数を返す`FALSE`から`DLL_PROCESS_ATTACH`です。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|`exit`、 `_Exit`、 `_exit`|\<process.h> または \<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_exit.c
// This program returns an exit code of 1. The
// error code could be tested in a batch file.

#include <stdlib.h>

int main( void )
{
   exit( 1 );
}
```

## <a name="see-also"></a>参照

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)  
[abort](../../c-runtime-library/reference/abort.md)  
[atexit](../../c-runtime-library/reference/atexit.md)  
[_cexit、_c_exit](../../c-runtime-library/reference/cexit-c-exit.md)  
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)  
[_onexit、_onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)  
[quick_exit](../../c-runtime-library/reference/quick-exit1.md)  
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)  
[system、_wsystem](../../c-runtime-library/reference/system-wsystem.md)  
