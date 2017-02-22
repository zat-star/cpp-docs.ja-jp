---
title: "fputc、fputwc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fputc"
  - "fputwc"
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
  - "fputc"
  - "fputwc"
  - "_fputtc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fputtc 関数"
  - "fputc 関数"
  - "fputtc 関数"
  - "fputwc 関数"
  - "ストリーム, 書き込み (文字の)"
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# fputc、fputwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームに文字を書き込みます。  
  
## 構文  
  
```  
int fputc(  
   int c,  
   FILE *stream   
);  
wint_t fputwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### パラメーター  
 `c`  
 書き込む文字。  
  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## 戻り値  
 これらの各関数は、書き込まれた文字を返します。  `fputc` の場合、`EOF` の戻り値はエラーを示します。  `fputwc` の場合、`WEOF` の戻り値はエラーを示します。  `stream` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらは `EOF` を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 これらの各関数は、関連付けられたファイル位置指示子によって示された位置のファイルに単一の文字 `c` を書き込み \(定義されている場合\)、必要に応じて指示子を進めます。  `fputc` および `fputwc` の場合、ファイルは `stream` に関連付けられます。ファイルが配置要求をサポートできない場合、または追加モードでファイルが開かれた場合、文字はストリームの末尾に追加されます。  
  
 ストリームが ANSI モードで開かれている場合、2 つの関数の動作は同じになります。  `fputc` では、UNICODE ストリームへの出力はサポートされていません。  
  
 `_nolock` サフィックス付きのバージョンは同じものですが、他のスレッドによる干渉から保護されない点が異なります。  詳細については、[\_fputc\_nolock、\_fputwc\_nolock](../../c-runtime-library/reference/fputc-nolock-fputwc-nolock.md)を参照します。  
  
 ルーチン固有の解説は、次のとおりです。  
  
|ルーチン|解説|  
|----------|--------|  
|`fputc`|`putc` と同じですが、関数とマクロではなく関数としてのみ実装されています。|  
|`fputwc`|`fputc` のワイド文字バージョン。  `stream` がテキスト モードまたはバイナリ モードで開かれるかどうかに従って、マルチバイト文字またはワイド文字として `c` を書き込みます。|  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_fputtc`|`fputc`|`fputc`|`fputwc`|  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`fputc`|\<stdio.h\>|  
|`fputwc`|\<stdio.h\> または \<wchar.h\>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。  コンソール \(`stdin`、`stdout`、および `stderr`\) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。  互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_fputc.c  
// This program uses fputc  
// to send a character array to stdout.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char strptr1[] = "This is a test of fputc!!\n";  
   char *p;  
  
   // Print line to stream using fputc.   
   p = strptr1;  
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;  
  
}  
```  
  
  **これは fputc のテストです\!\!**   
## 同等の .NET Framework 関数  
  
-   [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fgetc、fgetwc](../Topic/fgetc,%20fgetwc.md)   
 [putc、putwc](../../c-runtime-library/reference/putc-putwc.md)