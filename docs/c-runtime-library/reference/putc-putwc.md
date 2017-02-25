---
title: "putc、putwc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "putwc"
  - "putc"
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
  - "_puttc"
  - "putwc"
  - "putc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_puttc 関数"
  - "文字, 書き込み"
  - "putc 関数"
  - "puttc 関数"
  - "putwc 関数"
  - "ストリーム, 書き込み (文字の)"
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# putc、putwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームに文字を書き込みます。  
  
## 構文  
  
```  
  
      int putc(  
   int c,  
   FILE *stream   
);  
wint_t putwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### パラメーター  
 `c`  
 書き込む文字。  
  
 `stream`  
 **FILE** 構造体へのポインター。  
  
## 戻り値  
 書き込まれた文字を返します。  エラーまたはファイルの終端状態を示すには、`putc` と `putchar` は `EOF` を返します。`putwc` と `putwchar` は **WEOF** を返します。  4 つすべてのルーチンで、[ferror](../../c-runtime-library/reference/ferror.md) または [feof](../../c-runtime-library/reference/feof.md) を使用して、エラーまたはファイルの終端を確認します。  `stream` に null ポインターが渡された場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は `EOF` または **WEOF** を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `putc` ルーチンは、出力 `stream` の現在位置に 1 つの文字 `c` を書き込みます。  任意の整数を `putc` に渡すことができますが、下位 8 ビットのみが書き込まれます。  `putchar` ルーチンは **putc\(** `c`**,stdout\)** と同じです。  各ルーチンでは、読み取りエラーが発生すると、ストリームのエラー インジケーターが設定されます。  `putc` と `putchar` はそれぞれ、`fputc` と `_fputchar` に似ていますが、関数およびマクロとして実装されます \(「[関数とマクロの使い分け](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)」を参照\)。  `putwc`、および `putwchar` は、それぞれ、`putc`、および `putchar` のワイド文字バージョンです。  ストリームが ANSI モードで開かれている場合、`putwc` と `putc` の動作は同じになります。  `putc` では、UNICODE ストリームへの出力はサポートされていません。  
  
 **\_nolock** サフィックスが付いているバージョンは同じものですが、他のスレッドによる干渉から保護されない点が異なります。  詳細については、「**\_putc\_nolock、\_putwc\_nolock**」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_puttc`|`putc`|`putc`|**putwc**|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`putc`|\<stdio.h\>|  
|`putwc`|\<stdio.h\> または \<wchar.h\>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。  コンソール \(`stdin`、`stdout`、および `stderr`\) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。  互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
```  
// crt_putc.c  
/* This program uses putc to write buffer  
 * to a stream. If an error occurs, the program  
 * stops before writing the entire buffer.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char *p, buffer[] = "This is the line of output\n";  
   int  ch;  
  
   ch = 0;  
   /* Make standard out the stream and write to it. */  
   stream = stdout;  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = putc( *p, stream );  
}  
```  
  
## 出力  
  
```  
This is the line of output  
```  
  
## 同等の .NET Framework 関数  
  
-   [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fputc、fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc、getwc](../../c-runtime-library/reference/getc-getwc.md)