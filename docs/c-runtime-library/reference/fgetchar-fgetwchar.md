---
title: "_fgetchar、_fgetwchar | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fgetchar"
  - "_fgetwchar"
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
  - "fgetwchar"
  - "_fgettchar"
  - "_fgetchar"
  - "_fgetwchar"
  - "fgettchar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fgetchar 関数"
  - "_fgettchar 関数"
  - "_fgetwchar 関数"
  - "fgetchar 関数"
  - "fgettchar 関数"
  - "fgetwchar 関数"
  - "標準入力, 読み取り"
ms.assetid: 8bce874c-701a-41a3-b1b2-feff266fb5b9
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _fgetchar、_fgetwchar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`stdin` から文字を読み取ります。  
  
## 構文  
  
```  
int _fgetchar( void );  
wint_t _fgetwchar( void );  
```  
  
## 戻り値  
 `_fgetchar` は、読み込まれた文字を `int` として返すか、エラーまたはファイルの末尾を示す `EOF` を返します。  \_`fgetwchar` は、読み込まれた文字に相当するワイド文字を [wint\_t](../../c-runtime-library/standard-types.md) として返すか、エラーまたはファイルの末尾を示す `WEOF` を返します。  両方の関数に対して、エラーと、ファイルの末尾の条件を識別するため `feof` または `ferror` を使用します。  
  
## 解説  
 これらの関数は `stdin` から 1 つの文字を読み取ります。  関数は、次の文字 \(定義されている場合\) を指すように、関連ファイルのポインターをインクリメントします。  ストリームがファイルの末尾にある場合、ストリームのファイルの末尾を示すインジケーターが設定されます。  
  
 `_fgetchar` は `fgetc( stdin )` と同じです。  これは、`getchar` とも同じですが、関数とマクロではなく関数としてのみ実装されています。  `_fgetwchar` 関数は、`_fgetchar` 関数のワイド文字バージョンです。  
  
 これらの関数は ANSI 規格と互換性がありません。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_fgettchar`|`_fgetchar`|`_fgetchar`|`_fgetwchar`|  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`_fgetchar`|\<stdio.h\>|  
|`_fgetwchar`|\<stdio.h\> または \<wchar.h\>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。  コンソール \(`stdin`、`stdout`、および `stderr`\) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。  互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_fgetchar.c  
// This program uses _fgetchar to read the first  
// 80 input characters (or until the end of input)  
// and place them into a string named buffer.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char buffer[81];  
   int  i, ch;  
  
   // Read in first 80 characters and place them in "buffer":  
   ch = _fgetchar();  
   for( i=0; (i < 80 ) && ( feof( stdin ) == 0 ); i++ )  
   {  
      buffer[i] = (char)ch;  
      ch = _fgetchar();  
   }  
  
   // Add null to end string   
   buffer[i] = '\0';  
   printf( "%s\n", buffer );  
}  
```  
  
  **`1 行目。 2 行目。`1 行目。**  
**2 行目。**   
## 同等の .NET Framework 関数  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx)  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fputc、fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc、getwc](../../c-runtime-library/reference/getc-getwc.md)