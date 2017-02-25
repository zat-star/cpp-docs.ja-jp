---
title: "feof | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "feof"
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
  - "feof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EOF (ファイル終端), テスト"
  - "feof 関数"
ms.assetid: 09081eee-7c4b-4189-861f-2fad95d3ec6d
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# feof
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームの EOF のテスト。  
  
## 構文  
  
```  
int feof(   
   FILE *stream   
);  
```  
  
#### パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## 戻り値  
 読み取り操作はファイルの末尾を超えて読み取ろうとすると `feof` 関数の戻り値 0 以外の値; 長さが 0 以外の場合は false を返します。  ストリーム ポインターが `NULL`の場合、関数は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続 `errno` は `EINVAL` と `feof` は 0 に設定されます。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `feof` ルーチン \(関数とマクロとして実装される\) `stream` の最後に渡されているかどうかを判定します。  ファイルの終端に達した場合が渡された場合、読み取り操作は、ストリームを閉じるか、`rewind`まで、`fsetpos`、`fseek`、または `clearerr` がそれに対して呼び出されるまで EOF を返します。  
  
 たとえば、ファイルが 10 バイトが含まれているファイルの 10 バイトを読み取ると、`feof` は、ファイル ポインターをファイルの末尾にあるが、端を超えて読み取ろうとしていないため、0 を返します。  読み取ろうとした後にのみ、第 11 バイトは `feof` の戻り 0 以外の値。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`feof`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_feof.c  
// This program uses feof to indicate when  
// it reaches the end of the file CRT_FEOF.TXT. It also  
// checks for errors with ferror.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int  count, total = 0;  
   char buffer[100];  
   FILE *stream;  
  
   fopen_s( &stream, "crt_feof.txt", "r" );  
   if( stream == NULL )  
      exit( 1 );  
  
   // Cycle until end of file reached:  
   while( !feof( stream ) )  
   {  
      // Attempt to read in 100 bytes:  
      count = fread( buffer, sizeof( char ), 100, stream );  
      if( ferror( stream ) )      {  
         perror( "Read error" );  
         break;  
      }  
  
      // Total up actual bytes read  
      total += count;  
   }  
   printf( "Number of bytes read = %d\n", total );  
   fclose( stream );  
}  
```  
  
## 入力: crt\_feof.txt  
  
```  
Line one.  
Line two.  
```  
  
### 出力  
  
```  
Number of bytes read = 19  
```  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [エラー処理](../../c-runtime-library/error-handling-crt.md)   
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [\_eof](../../c-runtime-library/reference/eof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror、\_wperror](../../c-runtime-library/reference/perror-wperror.md)