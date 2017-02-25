---
title: "_chdrive | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_chdrive"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "chdrive"
  - "_chdrive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_chdrive 関数"
  - "chdrive 関数"
  - "ドライブ, 変更"
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _chdrive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在の作業ドライブを変更します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _chdrive(   
   int drive   
);  
```  
  
#### パラメーター  
 `drive`  
 現在の作業ドライブを指定する 1 ～ 26 の整数 \(1 \= A、2 \= B など\)。  
  
## 戻り値  
 現在の作業ドライブが正常に変更された場合はゼロ \(0\)、それ以外の場合は \-1。  
  
## 解説  
 `drive` が 1 ～ 26 の範囲内の数値でない場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、**\_chdrive** 関数は \-1 を返します。`errno` は `EACCES` に設定され、`_doserrno` は `ERROR_INVALID_DRIVE` に設定されます。  
  
 **\_chdrive** 関数は、スレッド セーフではない **SetCurrentDirectory** 関数に依存するため、スレッド セーフではありません。  マルチスレッド アプリケーションで **\_chdrive** を安全に使用するには、独自のスレッド同期を用意する必要があります。  詳細については、[MSDN ライブラリ](http://go.microsoft.com/fwlink/?LinkID=150542)で **SetCurrentDirectory** を検索してください。  
  
 **\_chdrive** 関数は現在の作業ドライブのみを変更します。**\_chdir** は現在の作業ディレクトリを変更します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|**\_chdrive**|\<direct.h\>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [\_getdrive](../../c-runtime-library/reference/getdrive.md) 関数の例を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## 参照  
 [ディレクトリ制御](../../c-runtime-library/directory-control.md)   
 [\_chdir、\_wchdir](../Topic/_chdir,%20_wchdir.md)   
 [\_fullpath、\_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_getcwd、\_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [\_mkdir、\_wmkdir](../Topic/_mkdir,%20_wmkdir.md)   
 [\_rmdir、\_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [system、\_wsystem](../../c-runtime-library/reference/system-wsystem.md)