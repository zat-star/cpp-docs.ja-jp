---
title: "_execle、_wexecle | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_execle"
  - "_wexecle"
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
  - "wexecle"
  - "_execle"
  - "_wexecle"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_execle 関数"
  - "_wexecle 関数"
  - "execle 関数"
  - "wexecle 関数"
ms.assetid: 75efa9c5-96b7-4e23-acab-06258901f63a
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _execle、_wexecle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

新しい子プロセスを読み込んで実行します。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
intptr_t _execle(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wexecle(   
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL,  
   const char *const *envp   
);  
```  
  
#### パラメーター  
 `cmdname`  
 実行するファイルのパス。  
  
 `arg0`, `...``argn`  
 パラメーターへのポインターのリスト。  
  
 `envp`  
 環境設定へのポインターの配列。  
  
## 戻り値  
 成功した場合、これらの関数が呼び出しプロセスに戻ることはありません。  戻り値 –1 はエラーを示し、この場合は `errno` グローバル変数が設定されます。  
  
|`errno` の値|説明|  
|----------------|--------|  
|`E2BIG`|引数と環境設定に必要な領域が 32 KB を超えています。|  
|`EACCES`|指定されたファイルでロック違反または共有違反が発生しています。|  
|`EINVAL`|無効なパラメーター。|  
|`EMFILE`|開いているファイルの数が多すぎます   \(指定されたファイルは、実行可能ファイルであるかどうかを確認するために開く必要があります\)。|  
|`ENOENT`|ファイルまたはパスが見つかりません。|  
|`ENOEXEC`|指定されたファイルが実行可能ファイルでないか、無効な実行可能ファイル形式です。|  
|`ENOMEM`|新しいプロセスを実行するのに十分なメモリがないか、使用できるメモリが破損しているか、または無効なブロックが存在します \(これは、呼び出しプロセスが正しく割り当てられていないことを示します\)。|  
  
 これらのリターン コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 これらの各関数は、新しいプロセスを読み込んで実行し、各コマンド ライン引数を個別のパラメーターとして渡し、環境設定へのポインターの配列を渡します。  
  
 `_execle` 関数は、パラメーターを検証します。  `cmdname` または `arg0` が null ポインターであるか、空の文字列である場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、\-1 を返します。  新しいプロセスは開始されません。  
  
## 必要条件  
  
|関数|必須ヘッダー|オプション ヘッダー|  
|--------|------------|----------------|  
|`_execle`|\<process.h\>|\<errno.h\>|  
|`_wexecle`|\<process.h\> または \<wchar.h\>|\<errno.h\>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
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