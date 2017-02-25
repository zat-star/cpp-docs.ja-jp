---
title: "scanf、_scanf_l、wscanf、_wscanf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wscanf_l"
  - "scanf"
  - "_scanf_l"
  - "wscanf"
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
  - "_tscanf"
  - "_scanf_l"
  - "wscanf"
  - "_wscanf_l"
  - "scanf"
  - "_tscanf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_scanf_l 関数"
  - "_tscanf 関数"
  - "_tscanf_l 関数"
  - "_wscanf_l 関数"
  - "データ [C++], 読み取り (入力ストリームから)"
  - "書式付きデータ [C++], 入力ストリームから"
  - "読み取り (データを) [C++], 入力ストリームから"
  - "scanf 関数"
  - "scanf_l 関数"
  - "tscanf 関数"
  - "tscanf_l 関数"
  - "wscanf 関数"
  - "wscanf_l 関数"
ms.assetid: 73eac607-117f-4be4-9ff0-4afd9cf3c848
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# scanf、_scanf_l、wscanf、_wscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

標準入力ストリームから書式付きデータを読み取ります。  これらの関数のセキュリティを強化したバージョンについては、「[scanf\_s、\_scanf\_s\_l、wscanf\_s、\_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)」を参照してください。  
  
## 構文  
  
```  
int scanf(  
   const char *format [,  
   argument]...   
);  
int _scanf_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wscanf(  
   const wchar_t *format [,  
   argument]...   
);  
int _wscanf_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### パラメーター  
 `format`  
 書式指定文字列。  
  
 `argument`  
 省略可能な引数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 正常に変換され、代入されたフィールドの数を返します。この数には、読み取られても代入されなかったフィールドは含まれません。  戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。  
  
 `format` が `NULL` ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は `EOF` を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `scanf` 関数は、標準入力ストリーム `stdin` からデータを読み取り、そのデータを `argument` で指定されている位置に書き込みます。  各 `argument` は、`format` の型指定子に対応する型の変数へのポインターにする必要があります。  重なり合う文字列間でコピーした場合の動作は未定義です。  
  
> [!IMPORTANT]
>  `scanf` の文字列を読み取るときは、`%s` の書式向けに幅を必ず指定します \(たとえば、`"%s"` の代わりに `"%32s"`\)。それ以外の場合は、不適切な書式を入力するとバッファー オーバーランが発生しやすくなる場合があります。  または、[scanf\_s、\_scanf\_s\_l、wscanf\_s、\_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) か [fgets](../../c-runtime-library/reference/fgets-fgetws.md) の使用を検討してください。  
  
 `wscanf` 関数は、`scanf` 関数のワイド文字バージョンです。`wscanf` 関数の引数 `format` は、ワイド文字列です。  ストリームが ANSI モードで開かれている場合、`wscanf` と `scanf` の動作は同じになります。  `scanf` では、UNICODE ストリームからの入力はサポートされていません。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tscanf`|`scanf`|`scanf`|`wscanf`|  
|`_tscanf_l`|`_scanf_l`|`_scanf_l`|`_wscanf_l`|  
  
 詳細については、「[scanf 関数と wscanf 関数の書式指定フィールド](../Topic/Format%20Specification%20Fields:%20scanf%20and%20wscanf%20Functions.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`scanf`, `_scanf_l`|\<stdio.h\>|  
|`wscanf`, `_wscanf_l`|\<stdio.h\> または \<wchar.h\>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。  コンソール \(`stdin`、`stdout`、および `stderr`\) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。  互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_scanf.c  
// compile with: /W3  
 /* This program uses the scanf and wscanf functions  
  * to read formatted input.  
  */  
  
#include <stdio.h>  
  
int main( void )  
{  
   int   i, result;  
   float fp;  
   char  c, s[81];  
   wchar_t wc, ws[81];  
   result = scanf( "%d %f %c %C %80s %80S", &i, &fp, &c, &wc, s, ws ); // C4996  
   // Note: scanf and wscanf are deprecated; consider using scanf_s and wscanf_s  
   printf( "The number of fields input is %d\n", result );  
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);  
   result = wscanf( L"%d %f %hc %lc %80S %80ls", &i, &fp, &c, &wc, s, ws ); // C4996  
   wprintf( L"The number of fields input is %d\n", result );  
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);  
}  
```  
  
  **`71 98.6 h z バイト文字 36 92.3 y n ワイド文字`フィールドの入力数は 6 です。**  
**内容: 71 98.599998 h z バイトの文字**  
**フィールドの入力数は 6 です**  
**内容: 36 92.300003 y n 幅の文字**   
## 同等の .NET Framework 関数  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
-   [System::Console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)  
  
-   [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx) などの `Parse` メソッドも参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [fscanf、\_fscanf\_l、fwscanf、\_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sscanf、\_sscanf\_l、swscanf、\_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)