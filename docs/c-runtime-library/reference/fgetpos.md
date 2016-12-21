---
title: "fgetpos | Microsoft Docs"
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
  - "fgetpos"
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
  - "fgetpos"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fgetpos 関数"
  - "ストリーム, ファイル位置インジケーター"
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fgetpos
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームのファイル位置インジケーターを取得します。  
  
## 構文  
  
```  
int fgetpos(   
   FILE *stream,  
   fpos_t *pos   
);  
```  
  
#### パラメーター  
 `stream`  
 ターゲット ストリーム。  
  
 `pos`  
 位置インジケーターのストレージ。  
  
## 戻り値  
 `fgetpos`、正常終了した場合は 0 を返します。  失敗すると、0 以外の値を返し、次のマニフェスト定数の 1 種類に `errno` を設定します \(インクルード\) を定義する: `EBADF`のいずれかが null ポインターの場合 `pos` の `stream` 値または指定したストリームを意味する値が無効であることを意味する有効なファイル ポインターではなく、アクセス可能、または `EINVAL`などではありません。  `stream` または `pos` が `NULL` のポインターの場合、関数は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  
  
## 解説  
 `fgetpos` 関数は `stream` 引数のファイル位置インジケーターおよび格納の現在の値を `pos`が指すオブジェクトに格納します。  `fsetpos` 関数は `pos` で `fgetpos` が呼び出されたときの位置に `stream` 引数のポインターをリセットするために保存されている情報を使用できます。  `pos` 値は内部形式で格納および使用に `fgetpos` と `fsetpos`でのみ使用されます。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`fgetpos`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_fgetpos.c  
// This program uses fgetpos and fsetpos to  
// return to a location in a file.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE   *stream;  
   fpos_t pos;  
   char   buffer[20];  
  
   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {  
      perror( "Trouble opening file" );  
      return -1;  
   }  
  
   // Read some data and then save the position.   
   fread( buffer, sizeof( char ), 8, stream );  
   if( fgetpos( stream, &pos ) != 0 ) {  
      perror( "fgetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fgetpos: %.13s\n", buffer );  
  
   // Restore to old position and read data   
   if( fsetpos( stream, &pos ) != 0 ) {  
      perror( "fsetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fsetpos: %.13s\n", buffer );  
   fclose( stream );  
}  
```  
  
## 入力: crt\_fgetpos.txt  
  
```  
fgetpos gets a stream's file-position indicator.  
```  
  
### 出力 crt\_fgetpos.txt  
  
```  
after fgetpos: gets a stream  
after fsetpos: gets a stream  
```  
  
## 同等の .NET Framework 関数  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fsetpos](../Topic/fsetpos.md)