---
title: "_fgetc_nolock、_fgetwc_nolock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fgetc_nolock"
  - "_fgetwc_nolock"
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
  - "_fgetwc_nolock"
  - "fgettc_nolock"
  - "fgetwc_nolock"
  - "_fgetc_nolock"
  - "_fgettc_nolock"
  - "fgetc_nolock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fgetc_nolock 関数"
  - "_fgettc_nolock 関数"
  - "_fgetwc_nolock 関数"
  - "文字, 読み取り"
  - "fgetc_nolock 関数"
  - "fgettc_nolock 関数"
  - "fgetwc_nolock 関数"
  - "読み取り (ストリームから文字を)"
  - "ストリーム, 読み取り (文字を)"
ms.assetid: fb8e7c5b-4503-493a-879e-6a1db75aa114
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _fgetc_nolock、_fgetwc_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スレッドがロックされていないストリームから文字を読み取ります。  
  
## 構文  
  
```  
int _fgetc_nolock(   
   FILE *stream   
);  
wint_t _fgetwc_nolock(   
   FILE *stream   
);  
```  
  
#### パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## 戻り値  
 [fgetc、fgetwc](../Topic/fgetc,%20fgetwc.md)を参照してください。  
  
## 解説  
 他のスレッドによる干渉から保護されないことを除き、`_fgetc_nolock` および `_fgetwc_nolock` は、それぞれ、`fgetc` および`fgetwc` と同じです。  他のスレッドをロックアウトするオーバーヘッドが発生しないため、処理が速くなる場合があります。  これらの関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみ使用してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_fgettc_nolock`|`_fgetc_nolock`|`_fgetc_nolock`|`_fgetwc_nolock`|  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`_fgetc_nolock`|\<stdio.h\>|  
|`_fgetwc_nolock`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_fgetc_nolock.c  
// This program uses getc to read the first  
// 80 input characters (or until the end of input)  
// and place them into a string named buffer.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   char buffer[81];  
   int  i, ch;  
  
   // Open file to read line from:   
   if( fopen_s( &stream, "crt_fgetc_nolock.txt", "r" ) != 0 )  
      exit( 0 );  
  
   // Read in first 80 characters and place them in "buffer":  
   ch = fgetc( stream );  
   for( i=0; (i < 80 ) && ( feof( stream ) == 0 ); i++ )  
   {  
      buffer[i] = (char)ch;  
      ch = _fgetc_nolock( stream );  
   }  
  
   // Add null to end string   
   buffer[i] = '\0';  
   printf( "%s\n", buffer );  
   fclose( stream );  
}  
```  
  
## 入力: crt\_fgetc\_nolock.txt  
  
```  
Line one.  
Line two.  
```  
  
### 出力  
  
```  
Line one.  
Line two.  
```  
  
## 同等の .NET Framework 関数  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx)  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fputc、fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc、getwc](../../c-runtime-library/reference/getc-getwc.md)