---
title: "fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l | Microsoft Docs"
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
  - "_fprintf_s_l"
  - "fwprintf_s"
  - "fprintf_s"
  - "_fwprintf_s_l"
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
apitype: "DLLExport"
f1_keywords: 
  - "_ftprintf_s"
  - "fprintf_s"
  - "fwprintf_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fprintf_s_l 関数"
  - "_ftprintf_s 関数"
  - "_ftprintf_s_l 関数"
  - "_fwprintf_s_l 関数"
  - "fprintf_s 関数"
  - "fprintf_s_l 関数"
  - "ftprintf_s 関数"
  - "ftprintf_s_l 関数"
  - "fwprintf_s 関数"
  - "fwprintf_s_l 関数"
  - "出力 (ストリームに書式付きデータを)"
ms.assetid: 16067c3c-69ce-472a-8272-9aadf1f5beed
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームに出力書式付きデータ。  これらの関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
int fprintf_s(   
   FILE *stream,  
   const char *format [,  
   argument ]...  
);  
int _fprintf_s_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument ]...  
);  
int fwprintf_s(   
   FILE *stream,  
   const wchar_t *format [,  
   argument ]...  
);  
int _fwprintf_s_l(   
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ]…  
);  
```  
  
#### パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
 `format`  
 書式指定文字列。  
  
 `argument`  
 省略可能な引数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 `fprintf_s` を書き込むバイト数を返します。  `fwprintf_s` を書き込むワイド文字数を返します。  これらの関数は、出力エラーが発生した場合は負の値を返します。  
  
## 解説  
 `fprintf_s` は 出力 `stream`、一連の文字と値の書式を指定して、出力します*。*各関数 `argument` は `format`の対応する書式指定に従って \(存在する場合\) に変換され、出力`fprintf_s`では、`format` 引数に `printf_s`と同じ構文を使用できます。  
  
 `fwprintf_s` は `fprintf_s`のワイド文字バージョンであり、; `fwprintf_s`で、`format` はワイド文字列です。  ストリームが ANSI モードで開かれている場合、これらの関数の動作は同じになります。  `fprintf_s` では、UNICODE ストリームへの出力はサポートされていません。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
> [!IMPORTANT]
>  `format` にユーザー定義の文字列を指定しないでください。  
  
 セキュリティが万全ではないバージョンと同様に `stream` または `format` が null ポインターの場合、\([fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)を参照してください\) は、これらの関数は、パラメーターを検証し、[パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  これらの関数は、セキュリティが万全ではないバージョンと書式指定文字列自体の検証も行うことです。  未知の書式指定子や作成の指定子がある場合、これらの関数は無効なパラメーターの例外を生成します。  すべての場合において、実行の継続が許可された場合、関数は \-1 を返し、`errno` を `EINVAL` に設定します。  エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_ftprintf_s`|`fprintf_s`|`fprintf_s`|`fwprintf_s`|  
|`_ftprintf_s_l`|`_fprintf_s_l`|`_fprintf_s_l`|`_fwprintf_s_l`|  
  
 詳細については、「[scanf 関数と wscanf 関数の書式指定フィールド](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)」を参照してください。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`fprintf_s`, `_fprintf_s_l`|\<stdio.h\>|  
|`fwprintf_s`, `_fwprintf_s_l`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_fprintf_s.c  
// This program uses fprintf_s to format various  
// data and print it to the file named FPRINTF_S.OUT. It  
// then displays FPRINTF_S.OUT on the screen using the system  
// function to invoke the operating-system TYPE command.  
  
#include <stdio.h>  
#include <process.h>  
  
FILE *stream;  
  
int main( void )  
{  
   int    i = 10;  
   double fp = 1.5;  
   char   s[] = "this is a string";  
   char   c = '\n';  
  
   fopen_s( &stream, "fprintf_s.out", "w" );  
   fprintf_s( stream, "%s%c", s, c );  
   fprintf_s( stream, "%d\n", i );  
   fprintf_s( stream, "%f\n", fp );  
   fclose( stream );  
   system( "type fprintf_s.out" );  
}  
```  
  
  **これは文字列です。**  
**10**  
**1.500000**   
## 同等の .NET Framework 関数  
 [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [\_cprintf、\_cprintf\_l、\_cwprintf、\_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf、\_fscanf\_l、fwscanf、\_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)