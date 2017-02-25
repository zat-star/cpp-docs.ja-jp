---
title: "clearerr_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "clearerr_s"
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
  - "clearerr_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "clearerr_s 関数"
  - "エラー インジケーター (ストリームの)"
  - "リセット (ストリーム エラー インジケーターを)"
ms.assetid: b74d014d-b7a8-494a-a330-e5ffd5614772
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# clearerr_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームのエラー インジケーターをリセットします。  これは [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)"に説明されているように、セキュリティが強化された [clearerr](../../c-runtime-library/reference/clearerr.md) のバージョンです。  
  
## 構文  
  
```  
errno_t clearerr_s(  
   FILE *stream   
);  
```  
  
#### パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## 戻り値  
 正常終了した場合は; `stream` が NULL の場合 `EINVAL`。  
  
## 解説  
 `clearerr_s` 関数は `stream`のエラー インジケーターと EOF をリセットします。  エラー インジケーターが自動的にオフになりません; 一度指定したストリームのエラー インジケーターが設定されている場合、そのストリームの操作は、`clearerr_s``clearerr`、`fseek`、`fsetpos`までのエラー値を返し、または `rewind` が呼び出されます。  
  
 `stream` が NULL の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`clearerr_s`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_clearerr_s.c  
// This program creates an error  
// on the standard input stream, then clears  
// it so that future reads won't fail.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int c;  
   errno_t err;  
  
   // Create an error by writing to standard input.  
   putc( 'c', stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Write error" );  
      err = clearerr_s( stdin );  
      if (err != 0)  
      {  
         abort();  
      }  
   }  
  
   // See if read causes an error.  
   printf( "Will input cause an error? " );  
   c = getc( stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Read error" );  
      err = clearerr_s( stdin );  
      if (err != 0)  
      {  
         abort();  
      }  
   }  
}  
```  
  
  **`nnWrite の` エラー: 不正なファイル記述子**  
**入力するとエラーが発生します。n**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [エラー処理](../../c-runtime-library/error-handling-crt.md)   
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [\_eof](../../c-runtime-library/reference/eof.md)   
 [feof](../../c-runtime-library/reference/feof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror、\_wperror](../../c-runtime-library/reference/perror-wperror.md)