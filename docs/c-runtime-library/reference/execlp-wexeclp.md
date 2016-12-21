---
title: "_execlp、_wexeclp | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wexeclp"
  - "_execlp"
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
  - "_wexeclp"
  - "wexeclp"
  - "_execlp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_execlp 関数"
  - "_wexeclp 関数"
  - "execlp 関数"
  - "wexeclp 関数"
ms.assetid: 7b179163-4bcd-4d6a-8baf-68f886791928
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _execlp、_wexeclp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

新しい子プロセスを読み込んで実行します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
intptr_t _execlp(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL   
);  
intptr_t _wexeclp(   
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL   
);  
```  
  
#### パラメーター  
 `cmdname`  
 実行するファイルのパス。  
  
 `arg0`, `...``argn`  
 パラメーターへのポインターのリスト。  
  
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
 これらの各関数は、新しいプロセスを読み込んで実行し、各コマンド ライン引数を個別のパラメーターとして渡すと共に、`PATH` 環境変数を使用して実行するファイルを探します。  
  
 `_execlp` 関数は、パラメーターを検証します。  `cmdname` または `arg0` が null ポインターまたは空の文字列の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、\-1 を返します。  新しいプロセスは開始されません。  
  
## 必要条件  
  
|関数|必須ヘッダー|オプション ヘッダー|  
|--------|------------|----------------|  
|`_execlp`|\<process.h\>|\<errno.h\>|  
|`_wexeclp`|\<process.h\> または \<wchar.h\>|\<errno.h\>|  
  
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