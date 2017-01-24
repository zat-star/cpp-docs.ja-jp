---
title: "getc、getwc | Microsoft Docs"
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
  - "getwc"
  - "getc"
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
  - "_gettc"
  - "getwc"
  - "_gettchar"
  - "getc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_gettc 関数"
  - "文字, 読み取り"
  - "getc 関数"
  - "gettc 関数"
  - "getwc 関数"
  - "getwchar 関数"
  - "読み取り (ストリームから文字を)"
  - "ストリーム, 読み取り (文字を)"
ms.assetid: 354ef514-d0c7-404b-92f5-995f6a834bb3
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# getc、getwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームから文字を読み取ります。  
  
## 構文  
  
```  
int getc(   
   FILE *stream   
);  
wint_t getwc(   
   FILE *stream   
);  
```  
  
#### パラメーター  
 `stream`  
 入力ストリーム。  
  
## 戻り値  
 読み取られた文字を返します。  読み取りエラーまたはファイルの終端に達した場合は、状態 `getc` の戻り `EOF`、`getwc` の戻り `WEOF`表示します。  `getc` の場合、`ferror` または `feof` を使用して、エラーまたはファイルの終端を確認します。  `stream` が `NULL`の場合、`getc` と `getwc` は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらの関数は `EOF` の \(または`getwc`の`WEOF`\) と `EINVAL`に設定 `errno`。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 各ルーチンは、現在位置からファイルから一つの文字を読み取り、次の文字を指すように関連ファイル ポインター \(を定義する場合は、インクリメントします。  ファイルは `stream`に関連付けられます。  
  
 これらの関数は呼び出し元スレッドをロックするため、スレッド セーフです。  ロックしないバージョンについては、「[\_getc\_nolock、\_getwc\_nolock](../../c-runtime-library/reference/getc-nolock-getwc-nolock.md)」を参照してください。  
  
 ルーチン固有の解説は、次のとおりです。  
  
|ルーチン|解説|  
|----------|--------|  
|`getc`|`fgetc`と同様ですが、関数とマクロとして実装されています。|  
|`getwc`|`getc` のワイド文字バージョン。  `stream` がテキスト モードまたはバイナリ モードで開くかによってマルチバイト文字またはワイド文字を読み取ります。|  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_gettc`|`getc`|`getc`|`getwc`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`getc`|\<stdio.h\>|  
|`getwc`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_getc.c  
// Use getc to read a line from a file.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
    FILE* fp;  
  
    // Read a single line from the file "crt_getc.txt".   
  
    fopen_s(&fp, "crt_getc.txt", "r");  
    if (!fp)  
    {  
       printf("Failed to open file crt_getc.txt.\n");  
       exit(1);  
    }  
  
    for (i = 0; (i < 80) && ((ch = getc(fp)) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
  
    fclose(fp);  
}  
```  
  
## 入力: crt\_getc.txt  
  
```  
Line one.  
Line two.  
```  
  
### 出力  
  
```  
Input was: Line one.  
```  
  
## 同等の .NET Framework 関数  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx)  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fgetc、fgetwc](../Topic/fgetc,%20fgetwc.md)   
 [\_getch、\_getwch](../Topic/_getch,%20_getwch.md)   
 [putc、putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc、ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)