---
title: "_tell、_telli64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_telli64"
  - "_tell"
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
  - "tell"
  - "telli64"
  - "_telli64"
  - "_tell"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tell 関数"
  - "_telli64 関数"
  - "ファイル ポインター [C++]"
  - "ファイル ポインター [C++], 取得"
  - "tell 関数"
  - "telli64 関数"
ms.assetid: 1500e8f9-8fec-4253-9eec-ec66125dfc9b
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _tell、_telli64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイル ポインターの位置を取得します。  
  
## 構文  
  
```  
long _tell(  
   int handle  
);  
__int64 _telli64(  
   int handle   
);  
```  
  
#### パラメーター  
 `handle`  
 開いているファイルを参照するファイル記述子。  
  
## 戻り値  
 ファイル ポインターの現在の位置。  検索ではないデバイス、戻り値は未定義です。  
  
 –1L の戻り値はエラーを示します。  `handle` が無効なファイル記述子の場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続 `EBADF` と戻り \-1L に関数によって設定された `errno`。  
  
 戻り値の詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_tell` 関数は `handle` の引数に関連付けられたファイル ポインターの現在の位置を取得します。  位置はファイルの先頭からバイト数で表されます。  `_telli64` 関数の場合、この値は 64 ビットの整数として表現されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_tell`, `_telli64`|\<io.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_tell.c  
// This program uses _tell to tell the  
// file pointer position after a file read.  
//  
  
#include <io.h>  
#include <stdio.h>  
#include <fcntl.h>  
#include <share.h>  
#include <string.h>  
  
int main( void )  
{  
   int  fh;  
   char buffer[500];  
  
   if ( _sopen_s( &fh, "crt_tell.txt", _O_RDONLY, _SH_DENYNO, 0) )  
   {  
      char buff[50];  
      _strerror_s( buff, sizeof(buff), NULL );  
      printf( buff );  
      exit( -1 );  
   }  
  
   if( _read( fh, buffer, 500 ) > 0 )  
      printf( "Current file position is: %d\n", _tell( fh ) );  
   _close( fh );  
}  
```  
  
## 入力: crt\_tell.txt  
  
```  
Line one.  
Line two.  
```  
  
### 出力  
  
```  
Current file position is: 20  
```  
  
## 参照  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [ftell、\_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [\_lseek、\_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)