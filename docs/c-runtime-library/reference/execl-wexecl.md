---
title: "_execl、_wexecl | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _execl
- _wexecl
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
- _execl
- _wexecl
- wexecl
dev_langs: C++
helpviewer_keywords:
- _execl function
- wexecl function
- _wexecl function
- execl function
ms.assetid: 81fefb8a-0a06-4221-b2bc-be18e38e89f4
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25537940ef37ca6c0bb9b69aa1a1af3a44183059
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="execl-wexecl"></a>_execl、_wexecl
新しい子プロセスを読み込んで実行します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
intptr_t _execl(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL   
);  
intptr_t _wexecl(  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cmdname`  
 実行されるファイルのパス。  
  
 `arg0, ... argn`  
 パラメーターへのポインターのリスト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、これらの関数が呼び出しプロセスに戻ることはありません。 戻り値-1 がいる場合、エラーを示す、`errno`グローバル変数を設定します。  
  
|errno の値|説明|  
|-----------------|-----------------|  
|`E2BIG`|引数と環境設定には、32 KB を超える領域が必要です。|  
|`EACCES`|指定されたファイルでロック違反または共有違反が発生しています。|  
|`EINVAL`|無効なパラメーター (1 つまたは複数のパラメーターが null ポインターまたは空の文字列の場合)。|  
|`EMFILE`|開いているファイルの数が多すぎます (指定されたファイルは、実行可能ファイルであるかどうかを確認するために開く必要があります)。|  
|`ENOENT`|ファイルまたはパスが見つかりません。|  
|`ENOEXEC`|指定されたファイルが実行可能ファイルでないか、無効な実行可能ファイル形式です。|  
|`ENOMEM`|新しいプロセスを実行するのに十分なメモリがないか、使用できるメモリが破損しているか、または無効なブロックが存在します (呼び出しプロセスが正しく割り当てられていないことを示します)。|  
  
## <a name="remarks"></a>コメント  
 これらの各関数は新しいプロセスを読み込んで実行し、各コマンド ライン引数を個別のパラメーターとして渡します。 1 番目の引数はコマンドまたは実行可能ファイルの名前で、2 番目の引数は、1 番目と同じにする必要があります。 これは、実行されるプロセスの `argv[0]` になります。 3 番目の引数は、実行されるプロセスの 1 番目の引数 `argv[1]` です。  
  
 `_execl` 関数は、パラメーターを検証します。 `cmdname` または `arg0` のいずれかが null ポインターまたは空の文字列である場合、これらの関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように無効なパラメーター ハンドラーを呼び出します。実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、-1 を返します。 新しいプロセスは実行されません。  
  
## <a name="requirements"></a>必要条件  
  
|関数|必須ヘッダー|オプション ヘッダー|  
|--------------|---------------------|---------------------|  
|`_execl`|\<process.h>|\<errno.h>|  
|`_wexecl`|\<process.h> または \<wchar.h>|\<errno.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 「[_exec 関数、_wexec 関数](../../c-runtime-library/exec-wexec-functions.md)」の例を参照してください。  
  
## <a name="see-also"></a>参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [_exec 系関数と _wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit、_Exit、_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit、_onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn関数、_wspawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system、_wsystem](../../c-runtime-library/reference/system-wsystem.md)