---
title: _cwait | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _cwait
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cwait
dev_langs:
- C++
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 483b98f005a77ff41d2a319a9d07ccc88ad32721
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="cwait"></a>_cwait
ほかのプロセスが終了するまで待機します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、次を参照してください。[ユニバーサル Windows プラットフォーム アプリでサポートされない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
intptr_t _cwait(   
   int *termstat,  
   intptr_t procHandle,  
   int action   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `termstat`  
 指定されたプロセスの結果コードを格納するバッファーへのポインターまたは NULL。  
  
 `procHandle`  
 待機するプロセス (つまり、`_cwait` が処理を戻す前に終了する必要のあるプロセス) へのハンドル。  
  
 `action`  
 Windows オペレーティング システムのアプリケーションでは無視されて、NULL を返します。それ以外のアプリケーションでは、`procHandle` に対して実行するアクション コードを返します。  
  
## <a name="return-value"></a>戻り値  
 指定されたプロセスが正常に完了すると、プロセスのハンドルを返し、`termstat` にプロセスの結果コードを設定します。 それ以外の場合、-1 を返し、設定`errno`次のようにします。  
  
|[値]|説明|  
|-----------|-----------------|  
|`ECHILD`|指定されたプロセスが存在しないか、`procHandle` が無効か、[GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx) API または [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx) API の呼び出しが失敗しました。|  
|`EINVAL`|`action` が無効です。|  
  
 これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_cwait` 関数は、`procHandle` で指定されたプロセスのプロセス ID が終了するまで待機します。 `procHandle` に渡された `_cwait` の値には、指定されたプロセスを作成する [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) 関数の呼び出しによって返される値を指定します。 プロセス ID が `_cwait` の呼び出し前に終了した場合、`_cwait` はすぐに処理を戻します。 プロセスで `_cwait` を使用すると、有効なハンドル (`procHandle`) を持つ別のプロセスを待機できます。  
  
 `termstat` は、指定されたプロセスのリターン コードを格納するバッファーへのポインターです。 `termstat` の値は、指定されたプロセスが Windows [ExitProcess](http://msdn.microsoft.com/library/windows/desktop/ms682658.aspx) API の呼び出しによって正常に終了したかどうかを示します。 指定されたプロセスが `ExitProcess` または `exit` を呼び出した場合、`_exit` から戻った場合、`main` の終端に達した場合のいずれかで、`main` が内部的に呼び出されます。 `termstat` 経由で返される値の詳細については、「[GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx)」を参照してください。 `_cwait` に NULL 値を指定して `termstat` を呼び出すと、指定したプロセスのリターン コードは格納されません。  
  
 Windows オペレーティング システムの環境では、プロセスの親子関係が実装されていないため、`action` パラメーターは無視されます。  
  
 `procHandle` が -1 または -2 (現在のプロセスまたはスレッドへのハンドル) でない限り、ハンドルは閉じられます。 したがって、この状況では、返されたハンドルは使用しないでください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_cwait`|\<process.h>|\<errno.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```C  
// crt_cwait.c  
// compile with: /c  
// This program launches several processes and waits  
// for a specified process to finish.  
  
#define _CRT_RAND_S  
  
#include <windows.h>  
#include <process.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <time.h>  
  
// Macro to get a random integer within a specified range  
#define getrandom( min, max ) (( (rand_s (&number), number) % (int)((( max ) + 1 ) - ( min ))) + ( min ))  
  
struct PROCESS  
{  
   int     nPid;  
   char    name[40];  
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };  
  
int main( int argc, char *argv[] )  
{  
   int termstat, c;  
   unsigned int number;  
  
   srand( (unsigned)time( NULL ) );    // Seed randomizer  
  
   // If no arguments, this is the calling process  
   if ( argc == 1 )  
   {  
      // Spawn processes in numeric order  
      for ( c = 0; c < 4; c++ ) {  
         _flushall();  
         process[c].nPid = _spawnl( _P_NOWAIT, argv[0], argv[0],   
                                    process[c].name, NULL );  
      }  
  
      // Wait for randomly specified process, and respond when done   
      c = getrandom( 0, 3 );  
      printf( "Come here, %s.\n", process[c].name );  
      _cwait( &termstat, process[c].nPid, _WAIT_CHILD );  
      printf( "Thank you, %s.\n", process[c].name );  
  
   }  
   // If there are arguments, this must be a spawned process   
   else  
   {  
      // Delay for a period that's determined by process number  
      Sleep( (argv[1][0] - 'A' + 1) * 1000L );  
      printf( "Hi, Dad. It's %s.\n", argv[1] );  
   }  
}  
```  
  
```Output  
Hi, Dad. It's Ann.  
Come here, Ann.  
Thank you, Ann.  
Hi, Dad. It's Beth.  
Hi, Dad. It's Carl.  
Hi, Dad. It's Dave.  
```  
  
## <a name="see-also"></a>参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)