---
title: "getchar、getwchar | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "getchar"
  - "getwchar"
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
  - "getwchar"
  - "GetChar"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_gettchar 関数"
  - "文字, 読み取り"
  - "gettchar 関数"
  - "getwchar 関数"
  - "標準入力, 読み取り"
ms.assetid: 19fda588-3e33-415c-bb60-dd73c028086a
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# getchar、getwchar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

標準入力から文字を読み取ります。  
  
## 構文  
  
```  
int getchar();  
wint_t getwchar();  
```  
  
## 戻り値  
 読み取られた文字を返します。  読み取りエラーまたはファイルの終端に達した場合は、状態 `getchar``returns EOF`、`getwchar` の戻り `WEOF`表示します。  `getchar` の場合、`ferror` または `feof` を使用して、エラーまたはファイルの終端を確認します。  
  
## 解説  
 各ルーチンは `stdin` から 1 つの文字を読み取り、関連付けられたファイル ポインターが次の文字を指すようにそのポインターをインクリメントします。  `getchar` は [\_fgetchar](../Topic/fgetc,%20fgetwc.md) と同じですが、関数およびマクロとして実装されます。  
  
 これらの関数は呼び出し元スレッドをロックするため、スレッド セーフです。  ロックしないバージョンについては、「[\_getchar\_nolock、\_getwchar\_nolock](../Topic/_getchar_nolock,%20_getwchar_nolock.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_gettchar`|`getchar`|`getchar`|`getwchar`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`getchar`|\<stdio.h\>|  
|`getwchar`|\<stdio.h\> または \<wchar.h\>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。  コンソール \(`stdin`、`stdout`、および `stderr`\) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。  互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_getchar.c  
// Use getchar to read a line from stdin.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
  
    for (i = 0; (i < 80) && ((ch = getchar()) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
}  
```  
  
  **`This text`入力: This text**   
## 同等の .NET Framework 関数  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx)  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [getc、getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [fgetc、fgetwc](../Topic/fgetc,%20fgetwc.md)   
 [\_getch、\_getwch](../Topic/_getch,%20_getwch.md)   
 [putc、putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc、ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)