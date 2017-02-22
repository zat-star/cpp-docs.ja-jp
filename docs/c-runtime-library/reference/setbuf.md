---
title: "setbuf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "setbuf"
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
  - "setbuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "setbuf 関数"
  - "ストリームのバッファリング"
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# setbuf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームのバッファリングを制御します。  この関数は使用されなくなりました; [setvbuf](../../c-runtime-library/reference/setvbuf.md) を代わりに使用します。  
  
## 構文  
  
```  
void setbuf(  
   FILE *stream,  
   char *buffer   
);  
```  
  
#### パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
 `buffer`  
 ユーザーが割り当てたバッファー。  
  
## 解説  
 `setbuf` 関数は `stream`のバッファリングを制御します。  `stream` の引数は読まれなかったし、または作成してファイルを開く必要があります。  `buffer` の引数が `NULL`の場合、ストリームは、バッファリングされます。  そうでない場合、バッファーは `BUFSIZ` がインクルード.で定義されているバッファー サイズである `BUFSIZ`長さの文字配列を指している必要があります。  特定のストリームの既定システムによって割り当てられるバッファーの代わりにユーザーが指定したバッファーは、I\/O のバッファリングするために使用します。  `stderr` のストリームは、既定で非バッファリングされますが、`stderr`にバッファーを割り当てるに `setbuf` を使用できます。  
  
 `setbuf` は [setvbuf](../../c-runtime-library/reference/setvbuf.md)で置き換えられました、新しいコードの推奨ルーチンです。  `setbuf` は 既存のコードとの互換性のために残されています。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`setbuf`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_setbuf.c  
// compile with: /W3  
// This program first opens files named DATA1 and  
// DATA2. Then it uses setbuf to give DATA1 a user-assigned  
// buffer and to change DATA2 so that it has no buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[BUFSIZ];  
   FILE *stream1, *stream2;  
  
   fopen_s( &stream1, "data1", "a" );  
   fopen_s( &stream2, "data2", "w" );  
  
   if( (stream1 != NULL) && (stream2 != NULL) )  
   {  
      // "stream1" uses user-assigned buffer:  
      setbuf( stream1, buf ); // C4996  
      // Note: setbuf is deprecated; consider using setvbuf instead  
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );  
  
      // "stream2" is unbuffered  
      setbuf( stream2, NULL ); // C4996  
      printf( "stream2 buffering disabled\n" );  
      _fcloseall();  
   }  
}  
```  
  
  **ユーザー定義のバッファーに設定されている stream1: 0012FCDC**  
**無効になる stream2 バッファリング**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fclose、\_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../Topic/fflush.md)   
 [fopen、\_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)