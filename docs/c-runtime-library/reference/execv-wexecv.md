---
title: "_execv、_wexecv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wexecv"
  - "_execv"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-process-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_execv"
  - "_wexecv"
  - "wexecv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_execv 関数"
  - "_wexecv 関数"
  - "execv 関数"
  - "wexecv 関数"
ms.assetid: 8dbaf7bc-9040-4316-a0c1-db7e866b52af
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _execv、_wexecv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

新しい子プロセスを読み込んで実行します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
intptr_t _execv(   
   const char *cmdname,  
   const char *const *argv   
);  
intptr_t _wexecv(   
   const wchar_t *cmdname,  
   const wchar_t *const *argv   
);  
```  
  
#### パラメーター  
 `cmdname`  
 実行するファイルのパス。  
  
 `argv`  
 パラメーターへのポインターの配列。  
  
## 戻り値  
 成功した場合、これらの関数が呼び出しプロセスに戻ることはありません。  戻り値 –1 はエラーを示し、この場合は `errno` グローバル変数が設定されます。  
  
|`errno` の値|説明|  
|----------------|--------|  
|`E2BIG`|引数と環境設定には、32 KB を超える領域が必要です。|  
|`EACCES`|指定されたファイルでロック違反または共有違反が発生しています。|  
|`EINVAL`|無効なパラメーター。|  
|`EMFILE`|開いているファイルの数が多すぎます \(指定されたファイルは、実行可能ファイルであるかどうかを確認するために開く必要があります\)。|  
|`ENOENT`|ファイルまたはパスが見つかりません。|  
|`ENOEXEC`|指定されたファイルが実行可能ファイルでないか、無効な実行可能ファイル形式です。|  
|`ENOMEM`|新しいプロセスを実行するのに十分なメモリがないか、使用できるメモリが破損しているか、または無効なブロックが存在します \(呼び出しプロセスが正しく割り当てられていないことを示します\)。|  
  
 リターン コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 これらの各関数は新しいプロセスを読み込んで実行し、コマンド ライン引数へのポインターの配列を渡します。  
  
 `_execv` 関数は、パラメーターを検証します。  `cmdname` が null ポインターの場合、または `argv` が null ポインター、または空の配列へのポインターである場合、または配列に最初の引数として空の文字列が含まれている場合、`_execv` 関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、\-1 を返します。  プロセスは起動されません。  
  
## 必要条件  
  
|関数|必須ヘッダー|オプション ヘッダー|  
|--------|------------|----------------|  
|`_execv`|\<process.h\>|\<errno.h\>|  
|`_wexecv`|\<process.h\> または \<wchar.h\>|\<errno.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 「[\_exec、\_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)」の使用例を参照してください。  
  
## 同等の .NET Framework 関数  
  
-   [System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
-   [System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
## 参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [\_exec、\_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [終了、\_Exit、\_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit、\_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_spawn 系関数と \_wspawn 系関数](../Topic/_spawn,%20_wspawn%20Functions.md)   
 [system、\_wsystem](../../c-runtime-library/reference/system-wsystem.md)