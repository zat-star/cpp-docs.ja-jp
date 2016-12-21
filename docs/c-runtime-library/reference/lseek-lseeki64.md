---
title: "_lseek、_lseeki64 | Microsoft Docs"
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
  - "_lseeki64"
  - "_lseek"
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
  - "_lseeki64"
  - "_lseek"
  - "lseeki64"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_lseek 関数"
  - "_lseeki64 関数"
  - "ファイル ポインター [C++], 移動"
  - "lseek 関数"
  - "lseeki64 関数"
  - "シーク ファイル ポインター"
ms.assetid: aba8a768-d40e-48c3-b38e-473dbd782f93
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _lseek、_lseeki64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定した場所にファイル ポインターを移動します。  
  
## 構文  
  
```  
  
      long _lseek(  
   int fd,  
   long offset,  
   int origin   
);  
__int64 _lseeki64(  
   int fd,  
   __int64 offset,  
   int origin   
);  
```  
  
#### パラメーター  
 `fd`  
 開いているファイルを参照するファイル記述子。  
  
 *オフセット*  
 *原点*からのバイト数。  
  
 *基点*  
 初期位置。  
  
## 戻り値  
 `_lseek` は ファイルの先頭からのオフセットを、新しい位置のバイト数\) を返します。  `_lseeki64` は 64 ビットの整数オフセットを返します。  エラーを示す関数の戻り値–1L。  渡られたら無効なパラメーター、不正なファイル記述子など、または *元* の値が無効な場合や *オフセット* で指定した位置に [パラメーターの検証](../../c-runtime-library/parameter-validation.md)で説明したように、ファイルの先頭の前に、無効なパラメーター ハンドラーが呼び出されます。です。  実行の継続 `EBADF` と戻り \-1L に関数によって設定された `errno`。  検索ではないデバイス \(ターミナルとプリンターなど\)、戻り値は未定義です。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_lseek` 関数は *原点*からの *オフセット* である新しい場所に `fd` に関連付けられたファイル ポインターを移動します。  ファイル内の次のアクションが新しい場所に発生します。  *元の* 引数は Stdio.h で定義されている次の定数の 1 種類があります。  
  
 `SEEK_SET`  
 ファイルの先頭。  
  
 `SEEK_CUR`  
 ファイル ポインターの現在の位置。  
  
 `SEEK_END`  
 ファイルの終わり。  
  
 ファイルまたはファイルの末尾を超えてポインターの任意の場所に移動するには `_lseek` を使用できます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_lseek`|\<io.h\>|  
|`_lseeki64`|\<io.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
```  
// crt_lseek.c  
/* This program first opens a file named lseek.txt.  
 * It then uses _lseek to find the beginning of the file,  
 * to find the current position in the file, and to find  
 * the end of the file.  
 */  
  
#include <io.h>  
#include <fcntl.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
int main( void )  
{  
   int fh;  
   long pos;               /* Position of file pointer */  
   char buffer[10];  
  
   _sopen_s( &fh, "crt_lseek.c_input", _O_RDONLY, _SH_DENYNO, 0 );  
  
   /* Seek the beginning of the file: */  
   pos = _lseek( fh, 0L, SEEK_SET );  
   if( pos == -1L )  
      perror( "_lseek to beginning failed" );  
   else  
      printf( "Position for beginning of file seek = %ld\n", pos );  
  
   /* Move file pointer a little */  
    _read( fh, buffer, 10 );  
  
   /* Find current position: */  
   pos = _lseek( fh, 0L, SEEK_CUR );  
   if( pos == -1L )  
      perror( "_lseek to current position failed" );  
   else  
      printf( "Position for current position seek = %ld\n", pos );  
  
   /* Set the end of the file: */  
   pos = _lseek( fh, 0L, SEEK_END );  
   if( pos == -1L )  
      perror( "_lseek to end failed" );  
   else  
      printf( "Position for end of file seek = %ld\n", pos );  
  
   _close( fh );  
}  
```  
  
## 入力: crt\_lseek.c\_input  
  
```  
Line one.  
Line two.  
Line three.  
Line four.  
Line five.  
```  
  
## 出力  
  
```  
Position for beginning of file seek = 0  
Position for current position seek = 10  
Position for end of file seek = 57  
```  
  
## 参照  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [fseek、\_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_tell、\_telli64](../../c-runtime-library/reference/tell-telli64.md)