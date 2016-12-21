---
title: "_ftell_nolock、_ftelli64_nolock | Microsoft Docs"
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
  - "_ftelli64_nolock"
  - "_ftell_nolock"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ftelli64_nolock"
  - "ftelli64_nolock"
  - "ftell_nolock"
  - "_ftell_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftell_nolock 関数"
  - "_ftelli64_nolock 関数"
  - "ファイル ポインター [C++], 取得 (現在の位置を)"
  - "ftell_nolock 関数"
  - "ftelli64_nolock 関数"
ms.assetid: 84e68b0a-32f8-4c4a-90ad-3f2387685ede
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ftell_nolock、_ftelli64_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スレッドがロックされていないファイル ポインターの現在の位置を取得します。  
  
## 構文  
  
```  
long _ftell_nolock(   
   FILE *stream   
);  
__int64 _ftelli64_nolock(   
   FILE *stream   
);  
```  
  
#### パラメーター  
 `stream`  
 `FILE` 構造体を対象とします。  
  
## 戻り値  
 `ftell` と `_ftelli64`と同じです。  詳細については、「[ftell、\_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)**」を参照してください。**  
  
## 解説  
 これらの関数は `ftell` と `_ftelli64`をロックしないバージョン、それぞれです。  これらは `ftell` と `_ftelli64`と同じですが、他のスレッドによる干渉から保護されません。  これらの関数は、他のスレッドをロックするオーバーヘッドが発生しないため、処理が速くなる場合があります。  これらの関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみ使用してください。  
  
## 必要条件  
  
|関数|必須ヘッダー|オプション ヘッダー|  
|--------|------------|----------------|  
|`ftell_nolock`|\<stdio.h\>|\<errno.h\>|  
|`_ftelli64_nolock`|\<stdio.h\>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek、\_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek、\_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [ftell、\_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)