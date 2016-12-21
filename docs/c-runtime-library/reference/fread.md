---
title: "fread | Microsoft Docs"
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
  - "fread"
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
  - "fread"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "データ [C++], 読み取り (入力ストリームから)"
  - "fread 関数"
  - "読み取り (データを) [C++], 入力ストリームから"
  - "ストリーム [C++], 読み取り (データを)"
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fread
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームからデータを読み取ります。  
  
## 構文  
  
```  
size_t fread(   
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
 `fread` で エラーが発生したり、ファイルの末尾に到達する `count`の前に発生した実際に読み込まれる `count` 未満である、完全な項目数を返します*。*EOF が見つかりました。読み取りエラー状態とを区別するために `feof` または `ferror` 関数を使用します。  `size` または `count` が 0 の場合、`fread` は 0 を返し、バッファーの内容は変更されません。  `stream` または `buffer` が null ポインターの場合、`fread` は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、0 を返します。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `fread` 関数は入力 `stream` から `size` バイトの `count` 項目まで読み取り、`buffer`に保存します*。*`stream` に関連付けられたファイル ポインターは実際に読み込まれるバイト数 \(1\) は大きくなります。  特定のストリームがテキスト モードで開いて、キャリッジ return–linefeed ペアは単一のライン フィードの文字に置き換えられます。  置換は、ファイル ポインターまたは戻り値には影響しません。  ファイル ポインターの位置でエラーが発生した場合は不確定です。  部分的に入力項目の値を決定する必要があります。  
  
 この機能により、別のスレッドがロックされます。  ロックされていないバージョンが必要な場合は、`_fread_nolock`を使用します。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`fread`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_fread.c  
// This program opens a file named FREAD.OUT and  
// writes 25 characters to the file. It then tries to open  
// FREAD.OUT and read in 25 characters. If the attempt succeeds,  
// the program displays the number of actual items read.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char list[30];  
   int  i, numread, numwritten;  
  
   // Open file in text mode:  
   if( fopen_s( &stream, "fread.out", "w+t" ) == 0 )  
   {  
      for ( i = 0; i < 25; i++ )  
         list[i] = (char)('z' - i);  
      // Write 25 characters to stream   
      numwritten = fwrite( list, sizeof( char ), 25, stream );  
      printf( "Wrote %d items\n", numwritten );  
      fclose( stream );  
  
   }  
   else  
      printf( "Problem opening the file\n" );  
  
   if( fopen_s( &stream, "fread.out", "r+t" ) == 0 )  
   {  
      // Attempt to read in 25 characters   
      numread = fread( list, sizeof( char ), 25, stream );  
      printf( "Number of items read = %d\n", numread );  
      printf( "Contents of buffer = %.25s\n", list );  
      fclose( stream );  
   }  
   else  
      printf( "File could not be opened\n" );  
}  
```  
  
  **25 項目の作成**  
**25 \= 読み込んだ項目数**  
**バッファーの内容 zyxwvutsrqponmlkjihgfedcb \=**   
## 同等の .NET Framework 関数  
 [System::IO::FileStream::Read](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../Topic/fwrite.md)   
 [\_read](../Topic/_read.md)