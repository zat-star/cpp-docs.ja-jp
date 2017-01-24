---
title: "_fread_nolock | Microsoft Docs"
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
  - "_fread_nolock"
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
  - "_fread_nolock"
  - "fread_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fread_nolock 関数"
  - "データ [C++], 読み取り (入力ストリームから)"
  - "fread_nolock 関数"
  - "読み取り (データを) [C++], 入力ストリームから"
  - "ストリーム [C++], 読み取り (データを)"
ms.assetid: 60e4958b-1097-46f5-a77b-94af5e7dba40
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fread_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

他のスレッドをロックしないでストリームからデータを読み取ります。  
  
## 構文  
  
```  
size_t _fread_nolock(   
   void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### パラメーター  
 `buffer`  
 データの格納場所。  
  
 `size`  
 項目のバイト単位のサイズ。  
  
 `count`  
 読み取る項目の最大数。  
  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## 戻り値  
 「[fread](../../c-runtime-library/reference/fread.md)」を参照してください。  
  
## 解説  
 この関数は `fread`をロックしないバージョンです。  これは `fread` と同じですが、他のスレッドによる干渉から保護されません。  これは、他のスレッドをロックするオーバーヘッドが発生しないため、処理が速くなる場合があります。  呼び出し元のスコープで既に分離を処理している場合にシングルスレッド アプリケーションなどのスレッド セーフのコンテキストでのみ、この関数を使用します。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`_fread_nolock`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::IO::FileStream::Read](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../Topic/fwrite.md)   
 [\_read](../Topic/_read.md)