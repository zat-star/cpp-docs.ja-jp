---
title: "fgets、fgetws | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fgets"
  - "fgetws"
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
  - "_fgetts"
  - "fgetws"
  - "fgets"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fgetts 関数"
  - "fgets 関数"
  - "fgetts 関数"
  - "fgetws 関数"
  - "ストリーム, 取得 (文字列を)"
  - "ストリーム, 読み取り"
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# fgets、fgetws
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームから文字列を取得します。  
  
## 構文  
  
```  
char *fgets(   
   char *str,  
   int n,  
   FILE *stream   
);  
wchar_t *fgetws(   
   wchar_t *str,  
   int n,  
   FILE *stream   
);  
```  
  
#### パラメーター  
 `str`  
 データの格納場所。  
  
 `n`  
 読み込む最大文字数。  
  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## 戻り値  
 これらの各関数は、`str` を返します。  `NULL` で エラーや、ファイルの終端を示すために戻ります。  エラーが発生したかどうかを判断するために `feof` または `ferror` を使用します。  `str` または `stream` が null ポインターの場合、または `n` がゼロ以下の場合、この関数は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `NULL` が返されます。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `fgets` 関数は入力 `stream` 引数やストアから文字列を `str`内で読み込みます。  `fgets` は 現在のストリーム内の位置の文字を読み取り、ストリームの末尾に、または読み込まれた文字数までの最初の改行文字が含まれていると、最初にあるスレッドがいずれか、`n` – 1 と同じです。  `str` に格納される結果は null 文字が付けられます。  改行文字または文字列に、読み取られたとなります。  
  
 `fgetws` 関数は、`fgets` 関数のワイド文字バージョンです。  
  
 `fgetws` は マルチバイト文字またはワイド文字列として `stream` がテキスト モードまたはバイナリ モードで開くかによってワイド文字の引数 `str` をそれぞれ読み取ります。  Unicode およびマルチバイトのストリーム入出力におけるテキスト モードおよびバイナリ モードの使い方の詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」および「[テキスト モードとバイナリ モードの Unicode ストリーム入出力](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_fgetts`|`fgets`|`fgets`|`fgetws`|  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`fgets`|\<stdio.h\>|  
|`fgetws`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_fgets.c  
// This program uses fgets to display  
// a line from a file on the screen.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[100];  
  
   if( fopen_s( &stream, "crt_fgets.txt", "r" ) == 0 )  
   {  
      if( fgets( line, 100, stream ) == NULL)  
         printf( "fgets error\n" );  
      else  
         printf( "%s", line);  
      fclose( stream );  
   }  
}  
```  
  
## 入力: crt\_fgets.txt  
  
```  
Line one.  
Line two.  
```  
  
### 出力  
  
```  
Line one.  
```  
  
## 同等の .NET Framework 関数  
  
-   [System::IO::StreamReader::ReadLine](https://msdn.microsoft.com/en-us/library/system.io.streamreader.readline.aspx)  
  
-   [System::IO::TextReader::ReadBlock](https://msdn.microsoft.com/en-us/library/system.io.textreader.readblock.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fputs、fputws](../Topic/fputs,%20fputws.md)   
 [gets、\_getws](../../c-runtime-library/gets-getws.md)   
 [puts、\_putws](../Topic/puts,%20_putws.md)