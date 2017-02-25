---
title: "fread_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fread_s"
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
  - "fread_s"
  - "stdio/fread_s"
dev_langs: 
  - "C++"
ms.assetid: ce735de0-f005-435d-a8f2-6f4b80ac775e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# fread_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームからデータを読み取ります。  [fread](../../c-runtime-library/reference/fread.md) のこのバージョンに [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)"に説明されているように、セキュリティが強化されたバージョンがあります。  
  
## 構文  
  
```  
size_t fread_s(   
   void *buffer,  
   size_t bufferSize,  
   size_t elementSize,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### パラメーター  
 `buffer`  
 データの格納場所。  
  
 `bufferSize`  
 バイトのコピー先のバッファーのサイズ。  
  
 `elementSize`  
 バイトを読み取るとき項目のサイズ。  
  
 `count`  
 読み取る項目の最大数。  
  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## 戻り値  
 `fread_s` \(`count` に達する前に、ファイルの読み取りエラーまたは終了が発生した場合 `count` 未満である可能性がある、バッファーに読込まれた全体\) 項目数を返します。  ファイルの終端に達した場合はエラー状態とを区別するために `feof` または `ferror` 関数を使用します。  `size` または `count` が 0 の場合、`fread_s` は 0 を返し、バッファーの内容は変更されません。  `stream` または `buffer` が null ポインターの場合、`fread_s` は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、0 を返します。  
  
 エラー コードの詳細については、「[" \_doserrno、errno、\_sys\_errlist、および\_sys\_nerr "](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `fread_s` 関数は入力 `stream` から `elementSize` バイトの `count` 項目まで読み取り、`buffer`に保存します。1 `stream` \(ある場合\) に関連付けられたファイル ポインターは実際に読み込まれるバイト数が大きくなります。  特定のストリームがテキスト モードで開いて、キャリッジ return–linefeed ペアは単一のライン フィードの文字に置き換えられます。  置換は、ファイル ポインターまたは戻り値には影響しません。  ファイル ポインターの位置でエラーが発生した場合は不確定です。  部分的に入力項目の値を決定する必要があります。  
  
 この機能により、別のスレッドがロックされます。  ロックされていないバージョンが必要な場合は、`_fread_nolock`を使用します。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`fread_s`|\<stdio.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```cpp  
  
// crt_fread_s.c  
// Command line: cl /EHsc /nologo /W4 crt_fread_s.c  
//  
// This program opens a file that's named FREAD.OUT and  
// writes characters to the file. It then tries to open  
// FREAD.OUT and read in characters by using fread_s. If the attempt succeeds,  
// the program displays the number of actual items read.  
  
#include <stdio.h>  
  
#define BUFFERSIZE 30  
#define DATASIZE 22  
#define ELEMENTCOUNT 2  
#define ELEMENTSIZE (DATASIZE/ELEMENTCOUNT)  
#define FILENAME "FREAD.OUT"  
  
int main( void )  
{  
   FILE *stream;  
   char list[30];  
   int  i, numread, numwritten;  
  
   for ( i = 0; i < DATASIZE; i++ )  
      list[i] = (char)('z' - i);  
   list[DATASIZE] = '\0'; // terminal null so we can print it  
  
   // Open file in text mode:  
   if( fopen_s( &stream, FILENAME, "w+t" ) == 0 )  
   {  
      // Write DATASIZE characters to stream   
      printf( "Contents of buffer before write/read:\n\t%s\n\n", list );  
      numwritten = fwrite( list, sizeof( char ), DATASIZE, stream );  
      printf( "Wrote %d items\n\n", numwritten );  
      fclose( stream );  
   } else {  
      printf( "Problem opening the file\n" );  
      return -1;  
   }  
  
   if( fopen_s( &stream, FILENAME, "r+t" ) == 0 )   {  
      // Attempt to read in characters in 2 blocks of 11  
      numread = fread_s( list, BUFFERSIZE, ELEMENTSIZE, ELEMENTCOUNT, stream );  
      printf( "Number of %d-byte elements read = %d\n\n", ELEMENTSIZE, numread );  
      printf( "Contents of buffer after write/read:\n\t%s\n", list );  
      fclose( stream );  
   } else {  
      printf( "File could not be opened\n" );  
      return -1;  
   }  
}  
```  
  
  **バッファーの内容は前の読み取り\/書き込み:**  
 **zyxwvutsrqponmlkjihgfe**  
 **22 項目の作成**   
 **読み取り \= 11 バイトの要素数 2**   
 **バッファーの内容はの後の読み取り\/書き込み:**   
 **zyxwvutsrqponmlkjihgfe**    
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../Topic/fwrite.md)   
 [\_read](../Topic/_read.md)