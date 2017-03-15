---
title: "fseek、_fseeki64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fseeki64"
  - "fseek"
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
apitype: "DLLExport"
f1_keywords: 
  - "fseek"
  - "_fseeki64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fseeki64 関数"
  - "ファイル ポインター [C++]"
  - "ファイル ポインター [C++], 移動"
  - "fseek 関数"
  - "fseeki64 関数"
  - "シーク ファイル ポインター"
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# fseek、_fseeki64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定した場所にファイル ポインターを移動します。  
  
## 構文  
  
```  
int fseek(   
   FILE *stream,  
   long offset,  
   int origin   
);  
int _fseeki64(   
   FILE *stream,  
   __int64 offset,  
   int origin   
);  
```  
  
#### パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
 `offset`  
 `origin`のバイト数。  
  
 `origin`  
 初期位置。  
  
## 戻り値  
 0、`fseek` と `_fseeki64` の成功します。  それ以外の場合は、0 以外の値を返します。  検索ではないデバイス、戻り値は未定義です。  `stream` が null ポインターの場合、または `origin` は次の許容値のいずれか 1 つがである `fseek` と `_fseeki64` は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、\-1 を返します。  
  
## 解説  
 `fseek` と `_fseeki64` は移動 `origin`から `offset` バイトの新しい場所に `stream` に関連付けられたファイル ポインター \(ある場合\) 機能します*。*ストリームの次のアクションが新しい場所で発生します。  更新用に開いたストリームで次の操作には、読み取りまたは書き込みのいずれかです。  引数の原点は、STDIO.H で定義された次の定数の 1 つが必要があります:  
  
 `SEEK_CUR`  
 ファイル ポインターの現在の位置。  
  
 `SEEK_END`  
 ファイルの終わり。  
  
 `SEEK_SET`  
 ファイルの先頭。  
  
 ファイル ポインターの位置で位置の変更に `fseek` と `_fseeki64` を使用できます。  ポインターは、ファイルの末尾に配置できます。  `fseek` と `_fseeki64`はEOF をクリアし、`stream`に対して `ungetc` の前の呼び出しの影響を無効にします。  
  
 ファイルがデータを付けるために開いたときは、ファイルの現在の位置が発生した場所によって作成または最後の I\/O 操作によって、決定されます。  I\/O 操作を付けるように開かれたファイルに行われていないファイル位置はファイルの先頭になります。  
  
 テキスト モードで開かれたストリームにキャリッジ return–linefeed 変換によって`fseek` と `_fseeki64`は予期しない結果を生成できるため、`fseek` と `_fseeki64`に制限されています。  テキスト モードで開かれたストリームで動作することが保証されている `_fseeki64`唯一の `fseek` と操作は次の操作:  
  
-   開始値に関連して 0 のオフセットで探します。  
  
-   `_fseeki64`を使用するときに `fseek`または `_ftelli64`を使用する場合の呼び出しから `ftell` に返されるオフセット値のファイルの先頭からシークします。  
  
 、テキスト モードでは、Ctrl \+ Z は入力時にファイルの終端の文字として解釈されます。  ファイルの末尾に\/書き込み用に読み取ること、Ctrl \+ Z の `fopen` および関連するすべてのチェックは、開くファイルでは、可能な場合は削除します。  これは `fseek` の組み合わせと `ftell`または`_fseeki64``_ftelli64`と使用すると、CTRL\+Z で終わるファイル内で移動するには、`fseek` または `_fseeki64` がファイル末尾付近で正しく動作してしまうためです。  
  
 CRT がバイト順マーク \(BOM\) で始まるファイルを開くと、ファイル ポインターは、BOM の後に配置されます \(つまり、ファイルの実際のコンテンツの先頭に\)。  それに初期位置と `fseek` を取得するファイルの先頭に、使用 `ftell``fseek` ではなく 0 を配置する場合。  
  
 この関数は実行中に他のスレッドのロック、スレッド セーフです。  ロックしないバージョンについては、「[\_fseek\_nolock、\_fseeki64\_nolock](../../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md)」を参照してください。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`fseek`|\<stdio.h\>|  
|`_fseeki64`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_fseek.c  
// This program opens the file FSEEK.OUT and  
// moves the pointer to the file's beginning.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[81];  
   int  result;  
  
   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )  
   {  
      printf( "The file fseek.out was not opened\n" );  
      return -1;  
   }  
   fprintf( stream, "The fseek begins here: "  
                    "This is the file 'fseek.out'.\n" );  
   result = fseek( stream, 23L, SEEK_SET);  
   if( result )  
      perror( "Fseek failed" );  
   else  
   {  
      printf( "File pointer is set to middle of first line.\n" );  
      fgets( line, 80, stream );  
      printf( "%s", line );  
    }  
   fclose( stream );  
}  
```  
  
  **ファイル ポインターは先頭行の中央に設定されます。**  
**これはファイル「fseek.out」です。**   
## 同等の .NET Framework 関数  
  
-   [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
-   [System::IO::FileStream::Seek](https://msdn.microsoft.com/en-us/library/system.io.filestream.seek.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fopen、\_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [ftell、\_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [\_lseek、\_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)