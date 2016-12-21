---
title: "setvbuf | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "setvbuf"
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
  - "setvbuf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "制御 (ストリーム バッファリングを)"
  - "setvbuf 関数"
  - "ストリームのバッファリング"
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
caps.latest.revision: 16
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# setvbuf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームのバッファリングとバッファー サイズを制御します。  
  
## 構文  
  
```  
int setvbuf(  
   FILE *stream,  
   char *buffer,  
   int mode,  
   size_t size   
);  
```  
  
#### パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
 `buffer`  
 ユーザーが割り当てたバッファー。  
  
 `mode`  
 バッファリングのモード。  
  
 `size`  
 バッファー サイズ \(バイト単位\)。  許容範囲: 2 \<\= `size` \<\= INT\_MAX \(2147483647\)。  この値は、内部的には 2 の倍数に切り捨てられます。  
  
## 戻り値  
 処理が正常に終了した場合は 0 を返します。  
  
 `stream` が `NULL` の場合、または `mode` か `size` が有効な範囲内にない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、この関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `setvbuf` 関数を使用すると、プログラムで `stream` のバッファリングとバッファー サイズを制御できます。  `stream` は、まだ読み取りも書き込みも行われていない開いているファイルを指している必要があります。  `buffer` が指す配列は、`NULL` でない限り、バッファーとして使用されます。NULL の場合、`setvbuf` は自動的に割り当てられる長さ `size`\/2 \* 2 バイトのバッファーを使用します。  
  
 *mode* は、`_IOFBF`、`_IOLBF`、または `_IONBF` のいずれかにします。  `mode` が `_IOFBF` または `_IOLBF` の場合、バッファーのサイズとして `size` が使用されます。  `mode` が `_IONBF` の場合、ストリームのバッファリングは行われないため、`size` と `buffer` は無視されます。  `mode` の値およびその意味は、次のとおりです。  
  
 `_IOFBF`  
 フル バッファリング。つまり `buffer` がバッファーとして、`size` がバッファー サイズとして使用されます。  `buffer` が `NULL` の場合は、自動的に割り当てられた `size` バイトのバッファーが使用されます。  
  
 `_IOLBF`  
 一部のシステムでは、行バッファリングを使用できます。  ただし、Win32 の場合、動作は `_IOFBF` \(フル バッファリング\) と同じです。  
  
 `_IONBF`  
 `buffer` と `size` に関係なく、バッファーは使用されません。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`setvbuf`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
```  
// crt_setvbuf.c  
// This program opens two streams: stream1  
// and stream2. It then uses setvbuf to give stream1 a  
// user-defined buffer of 1024 bytes and stream2 no buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[1024];  
   FILE *stream1, *stream2;  
  
   if( fopen_s( &stream1, "data1", "a" ) == 0 &&  
       fopen_s( &stream2, "data2", "w" ) == 0 )  
   {  
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )  
         printf( "Incorrect type or size of buffer for stream1\n" );  
      else  
         printf( "'stream1' now has a buffer of 1024 bytes\n" );  
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )  
         printf( "Incorrect type or size of buffer for stream2\n" );  
      else  
         printf( "'stream2' now has no buffer\n" );  
      _fcloseall();  
   }  
}  
```  
  
  **「stream1」で 1024 バイトのバッファーがあります。**  
**「stream2」に、バッファーがありません**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fclose、\_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../Topic/fflush.md)   
 [fopen、\_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setbuf](../../c-runtime-library/reference/setbuf.md)