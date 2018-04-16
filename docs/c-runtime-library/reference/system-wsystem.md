---
title: "system、_wsystem | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- system
- _wsystem
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
- _tsystem
- _wsystem
dev_langs:
- C++
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3d46fd4b4df463bfce940360744a0a548652e2b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="system-wsystem"></a>system、_wsystem
コマンドを実行します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、次を参照してください。[ユニバーサル Windows プラットフォーム アプリでサポートされない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
int system(  
   const char *command   
);  
int _wsystem(  
   const wchar_t *command   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `command`  
 実行するコマンド。  
  
## <a name="return-value"></a>戻り値  
 `command` が `NULL` の場合に、コマンド インタープリターが見つかると、0 以外の値を返します。 コマンド インタープリターが見つからない場合は、0 を返し、`errno` を `ENOENT` に設定します。 `command` が `NULL` でない場合、`system` は、コマンド インタープリターから返された値を返します。 コマンド インタープリターから値 0 が返された場合にのみ、値 0 を返します。 戻り値 1 が、エラーを示すと`errno`値は次のいずれかに設定されています。  
  
 `E2BIG`  
 引数リスト (システムに依存する) が大きすぎます。  
  
 `ENOENT`  
 コマンド インタープリターが見つかりません。  
  
 `ENOEXEC`  
 形式が無効なため、コマンド インタープリター ファイルを実行できません。  
  
 `ENOMEM`  
 コマンドを実行するために十分なメモリがないか、使用できるメモリが破損しているか、または無効なブロックが存在します (これは、呼び出しを実行しているプロセスが正しく割り当てられなかったことを示します)。  
  
 これらのリターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `system` 関数は `command` をコマンド インタープリターに渡し、その文字列がオペレーティング システム コマンドとして実行されます。 `system` は、`COMSPEC` および `PATH` の各環境変数を使用して、コマンド インタープリター ファイル CMD.exe を見つけます。 `command` が `NULL` の場合、この関数はコマンド インタープリターの存在を確認するだけです。  
  
 `system` 関数を呼び出す前に、`fflush` または `_flushall` を使用してストリームを明示的にフラッシュするか、ストリームを閉じる必要があります。  
  
 `_wsystem` 関数は、`system` 関数のワイド文字バージョンです。`command` 関数の引数 `_wsystem` は、ワイド文字列です。 それ以外では、これらの関数の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsystem`|`system`|`system`|`_wsystem`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`system`|\<process.h> または \<stdlib.h>|  
|`_wsystem`|\<process.h> または \<stdlib.h> または \<wchar.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 この例では、`system` を使用してテキスト ファイルをタイプします。  
  
```  
// crt_system.c  
  
#include <process.h>  
  
int main( void )  
{  
   system( "type crt_system.txt" );  
}  
```  
  
## <a name="input-crtsystemtxt"></a>入力: crt_system.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>出力  
  
```  
Line one.  
Line two.  
```  
  
## <a name="see-also"></a>参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [_exec 系関数と _wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)   
 [exit、_Exit、_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)