---
title: "ftell、_ftelli64 | Microsoft Docs"
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
  - "_ftelli64"
  - "ftell"
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
  - "_ftelli64"
  - "ftell"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftelli64 関数"
  - "ファイル ポインター [C++]"
  - "ファイル ポインター [C++], 取得 (現在の位置を)"
  - "ftell 関数"
  - "ftelli64 関数"
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ftell、_ftelli64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイル ポインターの現在の位置を取得します。  
  
## 構文  
  
```  
long ftell(   
   FILE *stream   
);  
__int64 _ftelli64(   
   FILE *stream   
);  
```  
  
#### パラメーター  
 `stream`  
 ターゲット `FILE` 構造体。  
  
## 戻り値  
 `ftell` と `_ftelli64` はファイルの現在の位置を返します。  `ftell` と `_ftelli64` によって返される値は、テキスト モードでキャリッジ return–linefeed 変換が発生するため、テキスト モードで開かれたストリームの物理的なバイト オフセットを表していないことがあります。  ファイルの場所に適切に戻るために `fseek`の`ftell` または`_fseeki64` の`_ftelli64`を使用します。  エラーの場合、`ftell`と`_ftelli64` は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらの関数は–1L と 2 桁の定数の 1 つがに設定 `errno`、ERRNO.H.で定義されています。  `EBADF` の定数は `stream` の引数に有効なファイル ポインター値ではなく、開いているファイルを参照しないことを意味します。  `EINVAL` は `stream` の無効な引数が関数に渡されたことを意味します。  到達できないのデバイスで `stream` が開いているファイルがない場合 \(ターミナルとプリンターなど\)、または、戻り値は未定義です。  
  
 リターン コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `ftell` と `_ftelli64`関数は `stream`に関連付けられたファイル ポインターの現在の位置 \(ある場合\) を取得します*。*位置は、ストリームの先頭を基準としたオフセットとして表現されます。  
  
 次の発生した場所によって作成またはファイルのデータを付けるために開いたときは、ファイルの現在の位置は最後の I\/O 操作によって決定されることで、注意してください。  たとえば、ファイルを追加するためにその直前の操作を読み取り、ファイル位置は、次の場所に書き込み、次の読み取り操作を開始するポイントであり、開始します。ファイルを追加するために開く場合、ファイル位置は、書き込み操作の前に、ファイルの終端に移動されます\)。I\/O 操作を付けるように開かれたファイルに行われていないファイル位置はファイルの先頭です。  
  
 テキスト モードでは、Ctrl \+ Z は入力のファイルの終端の文字として解釈されます。  ファイルの末尾に\/書き込み用に読み取ること、Ctrl \+ Z の `fopen` および関連するすべてのチェックは、開くファイルでは、可能な場合は削除します。  これは `ftell` の組み合わせと `fseek` または `_ftelli64``_fseeki64`と使用すると、CTRL\+Z で終わるファイル内で移動するには、`ftell` または `_ftelli64` がファイル末尾付近で正しく動作してしまうためです。  
  
 この関数は、実行時に呼び出し元のスレッドをロックし、スレッド セーフです。  ロックしないバージョンについては、「`_ftell_nolock`」を参照してください。  
  
## 必要条件  
  
|関数|必須ヘッダー|省略可能なヘッダー|  
|--------|------------|---------------|  
|`ftell`|\<stdio.h\>|\<errno.h\>|  
|`_ftelli64`|\<stdio.h\>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_ftell.c  
// This program opens a file named CRT_FTELL.C  
// for reading and tries to read 100 characters. It  
// then uses ftell to determine the position of the  
// file pointer and displays this position.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long position;  
   char list[100];  
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )  
   {  
      // Move the pointer by reading data:   
      fread( list, sizeof( char ), 100, stream );  
      // Get position after read:   
      position = ftell( stream );  
      printf( "Position after trying to read 100 bytes: %ld\n",  
              position );  
      fclose( stream );  
   }  
}  
```  
  
  **100 バイトを読み取ろうとした後の位置: 100**   
## 同等の .NET Framework 関数  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fopen、\_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek、\_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek、\_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)