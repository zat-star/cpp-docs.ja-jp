---
title: "_spawnle、_wspawnle | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _spawnle
- _wspawnle
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
- spawnle
- _spawnle
- wspawnle
- _wspawnle
dev_langs:
- C++
helpviewer_keywords:
- spawnle function
- processes, creating
- _wspawnle function
- processes, executing new
- process creation
- wspawnle function
- _spawnle function
ms.assetid: 80308892-2815-49b1-8cca-53894c366f5a
caps.latest.revision: 17
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 4607528d5e7d5bdeb71c560f8f5890fe469a531e
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="spawnle-wspawnle"></a>_spawnle、_wspawnle
新しいプロセスを作成して実行します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
intptr_t _spawnle(  
   int mode,  
   const char *cmdname,  
   const char *arg0,  
   const char *arg1,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wspawnle(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   const wchar_t *arg1,  
   ... const wchar_t *argn,  
   NULL,  
   const wchar_t *const *envp   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `mode`  
 呼び出しプロセスの実行モード。  
  
 `cmdname`  
 実行されるファイルのパス。  
  
 `arg0, arg1, ... argn`  
 引数へのポインターのリスト。 `arg0` 引数は通常、 `cmdname`へのポインターです。 引数 `arg1` ～ `argn` は、新しい引数リストを構成する文字列へのポインターです。 `argn`の後には、引数リストの末尾を示すために `NULL` ポインターが必要です。  
  
 `envp`  
 環境設定へのポインターの配列。  
  
## <a name="return-value"></a>戻り値  
 同期 `_spawnle` または `_wspawnle` (`_P_WAIT` 向けに指定された `mode`) からの戻り値が新しいプロセスの終了ステータスです。 非同期 `_spawnle` または `_wspawnle` (`_P_NOWAIT` 向けに指定された `_P_NOWAITO` または `mode`) からの戻り値がプロセス ハンドルです。 プロセスが正常に終了した場合、終了ステータスは 0 です。 起動されたプロセスで、0 以外の引数を指定して `exit` ルーチンを明示的に呼び出すと、終了ステータスを 0 以外の値に設定できます。 新しいプロセスが明示的に終了ステータスを正の値に設定しなかった場合、正の値の終了ステータスは中止または割り込みによる異常終了を示します。 戻り値-1 は、(新しいプロセスは開始されません) エラーを示します。 この場合、 `errno` は次のいずれかの値に設定されます。  
  
 `E2BIG`  
 引数リストが 1024 バイトを超えています。  
  
 `EINVAL`  
 `mode` 引数が無効です。  
  
 `ENOENT`  
 ファイルまたはパスが見つかりません。  
  
 `ENOEXEC`  
 指定されたファイルが実行可能ファイルでないか、無効な実行可能ファイル形式です。  
  
 `ENOMEM`  
 新しいプロセスを実行するのに十分なメモリがありません。  
  
 これらのリターン コードとその他のリターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 これらの関数は、新しいプロセスを作成して実行し、各コマンド ライン引数を個別のパラメーターとして渡します。また環境設定へのポインターの配列も渡します。  
  
 これらの関数では、パラメーターの検証が行われます。 `cmdname` または `arg0` が空の文字列または null ポインターの場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、-1 を返します。 新しいプロセスは起動されません。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_spawnle`|\<process.h>|  
|`_wspawnle`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 「 [_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)」の使用例を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec 系関数と _wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)   
 [exit、_Exit、_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_onexit、_onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system、_wsystem](../../c-runtime-library/reference/system-wsystem.md)
