---
title: "_fflush_nolock | Microsoft Docs"
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
  - "_fflush_nolock"
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
  - "fflush_nolock"
  - "_fflush_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fflush_nolock 関数"
  - "fflush_nolock 関数"
  - "フラッシュ"
  - "ストリーム, フラッシュ"
ms.assetid: 5e33c4a1-b10c-4001-ad01-210757919291
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fflush_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スレッドがロックされていないストリームをフラッシュします。  
  
## 構文  
  
```  
int _fflush_nolock(   
   FILE *stream   
);  
```  
  
#### パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## 戻り値  
 「[fflush](../Topic/fflush.md)」を参照してください。  
  
## 解説  
 この関数は `fflush`をロックしないバージョンです。  これは `fflush` と同じですが、他のスレッドによる干渉から保護されません。  これは、他のスレッドをロックするオーバーヘッドが発生しないため、処理が速くなる場合があります。  呼び出し元のスコープで既に分離を処理している場合にシングルスレッド アプリケーションなどのスレッド セーフのコンテキストでのみ、この関数を使用します。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`_fflush_nolock`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::IO::FileStream::Flush](https://msdn.microsoft.com/en-us/library/2bw4h516.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fclose、\_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)