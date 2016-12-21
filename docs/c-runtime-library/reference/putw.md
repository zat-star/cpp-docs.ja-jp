---
title: "_putw | Microsoft Docs"
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
  - "_putw"
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
  - "_putw"
  - "putw"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_putw 関数"
  - "整数, 書き込み (ストリームへの)"
  - "putw 関数"
  - "ストリーム, 書き込み (整数の)"
ms.assetid: 83d63644-249d-4a39-87e5-3b7aa313968d
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _putw
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームに整数を書き込みます。  
  
## 構文  
  
```  
  
      int _putw(  
   int binint,  
   FILE *stream   
);  
```  
  
#### パラメーター  
 *binint*  
 出力される 2 進整数。  
  
 `stream`  
 **FILE** 構造体へのポインター。  
  
## 戻り値  
 書き込む値を返します。  `EOF` の戻り値はエラーを示す場合もあります。  `EOF` も有効な整数値であるため、エラーを検証するために `ferror` を使用します。  `stream` が null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EOF` を返します。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_putw` 関数は、*ストリーム*の現在の位置に `int` 型のバイナリ値を書き込みます。`_putw` はストリームの項目の配置に、想定して特別な配置には影響しません。  `_putw` は 前のライブラリとの互換性を維持するためです。  移植性の問題は `_putw` と `int` のサイズと `int` 内のバイトの順番がシステム間で異なる場合に発生することがあります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_putw`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
```  
// crt_putw.c  
/* This program uses _putw to write a  
 * word to a stream, then performs an error check.  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   unsigned u;  
   if( fopen_s( &stream, "data.out", "wb" ) )  
      exit( 1 );  
   for( u = 0; u < 10; u++ )  
   {  
      _putw( u + 0x2132, stream );   /* Write word to stream. */  
      if( ferror( stream ) )         /* Make error check. */  
      {  
         printf( "_putw failed" );  
         clearerr_s( stream );  
         exit( 1 );  
      }  
   }  
   printf( "Wrote ten words\n" );  
   fclose( stream );  
}  
```  
  
## 出力  
  
```  
Wrote ten words  
```  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [\_getw](../../c-runtime-library/reference/getw.md)