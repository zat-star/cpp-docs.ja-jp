---
title: "strtod、_strtod_l、wcstod、_wcstod_l | Microsoft Docs"
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
  - "wcstod"
  - "_wcstod_l"
  - "_strtod_l"
  - "strtod"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tcstod"
  - "strtod"
  - "wcstod"
  - "_strtod_l"
  - "_wcstod_l"
  - "stdlib/strtod"
  - "corecrt_wstdlib/wcstod"
  - "stdlib/_strtod_l"
  - "corecrt_wstdlib/_wcstod_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strtod_l 関数"
  - "_tcstod 関数"
  - "_tcstod_l 関数"
  - "_wcstod_l 関数"
  - "文字列変換, 浮動小数点値への"
  - "strtod 関数"
  - "strtod_l 関数"
  - "tcstod 関数"
  - "tcstod_l 関数"
  - "wcstod 関数"
  - "wcstod_l 関数"
ms.assetid: 0444f74a-ba2a-4973-b7f0-1d77ba88c6ed
caps.latest.revision: 20
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strtod、_strtod_l、wcstod、_wcstod_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列を倍精度の値に変換します。  
  
## 構文  
  
```  
double strtod(  
   const char *nptr,  
   char **endptr   
);  
double _strtod_l(  
   const char *nptr,  
   char **endptr,  
   _locale_t locale  
);  
double wcstod(  
   const wchar_t *nptr,  
   wchar_t **endptr   
);  
double wcstod_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `nptr`  
 NULL で終わる変換対象の文字列。  
  
 `endptr`  
 スキャンの終了位置を示す文字へのポインター。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 `strtod` 関数は、オーバーフローを引き起こす場合を除き、浮動小数点数の値を返します。オーバーフローの場合は、\+\/\-`HUGE_VAL` を返します。  `HUGE_VAL` の符号は、表現できない値の符号と一致します。  変換を実行できない場合、またはアンダーフローが発生する場合、`strtod` 関数は 0 を返します。  
  
 `wcstod` 関数の戻り値は、`strtod` 関数の戻り値と同じです。  「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、両方の関数に対して、オーバーフローまたはアンダーフローが発生し、無効なパラメーター ハンドラーが呼び出された場合、`errno` は `ERANGE` に設定されます。  
  
 戻り値の詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 各関数は、入力文字列 `nptr` を `double` に変換します。  `strtod` 関数は、`nptr` を倍精度浮動小数点値に変換します。  `strtod` 関数は、数値の一部として認識できない文字を最初に見つけた時点で、文字列 `nptr` の読み取りを終了します。  数値として認識できない最初の文字が、終端の NULL 文字の場合もあります。  `wcstod` 関数は、`strtod` 関数のワイド文字バージョンで、`nptr` 引数はワイド文字列です。  それ以外では、これらの関数の動作は同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcstod`|`strtod`|`strtod`|`wcstod`|  
|`_tcstod_l`|`_strtod_l`|`_strtod_l`|`_wcstod_l`|  
  
 現在のロケールの `LC_NUMERIC` カテゴリの設定に基づいて、`nptr` の小数点文字が認識されます。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていない関数は、現在のロケールを使用します。`_strtod_l` は、渡されたロケールを使用することを除いて `_strtod_l` と同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `endptr` が `NULL` 以外の場合は、スキャンを停止させた文字へのポインターを `endptr` が指す位置に格納します。  変換できなかった場合 \(有効な数字が見つからなかった場合、または無効な base を指定した場合\) は、`nptr` の値を `endptr` が指す位置に格納します。  
  
 `strtod` は、`nptr` が次の形式の文字列を指すものと想定します。  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\] \[`.digits`\] \[ {`d` &#124; `D` &#124; `e` &#124; `E`}\[`sign`\]`digits`\]  
  
 `whitespace` はスペースやタブで構成され、無視されます。`sign` はプラス \(`+`\) またはマイナス \(`–`\) のいずれかで、`digits` は 1 つ以上の 10 進数字です。  小数点文字の前に数字がない場合は、少なくとも 1 つの数字が小数点文字の後に必要です。  10 進数の後には指数部を指定できます。指数部は、指数部の開始文字 \(`d`、`D`、`e`、または `E`\) および必要に応じて符号付き整数で構成されます。  指数部と小数点文字のいずれも指定されない場合は、文字列の最後の数字の後に小数点文字が続くと想定されます。  この形式に一致しない文字を見つけるとスキャンを停止します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`strtod`, `_strtod_l`|\<stdlib.h\>|  
|`wcstod`, `_wcstod_l`|\<stdlib.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_strtod.c  
// This program uses strtod to convert a  
// string to a double-precision value; strtol to  
// convert a string to long integer values; and strtoul  
// to convert a string to unsigned long-integer values.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char   *string, *stopstring;  
   double x;  
   long   l;  
   int    base;  
   unsigned long ul;  
  
   string = "3.1415926This stopped it";  
   x = strtod( string, &stopstring );  
   printf( "string = %s\n", string );  
   printf("   strtod = %f\n", x );  
   printf("   Stopped scan at: %s\n\n", stopstring );  
  
   string = "-10110134932This stopped it";  
   l = strtol( string, &stopstring, 10 );  
   printf( "string = %s\n", string );  
   printf("   strtol = %ld\n", l );  
   printf("   Stopped scan at: %s\n\n", stopstring );  
  
   string = "10110134932";  
   printf( "string = %s\n", string );  
  
   // Convert string using base 2, 4, and 8:  
   for( base = 2; base <= 8; base *= 2 )  
   {  
      // Convert the string:  
      ul = strtoul( string, &stopstring, base );  
      printf( "   strtol = %ld (base %d)\n", ul, base );  
      printf( "   Stopped scan at: %s\n", stopstring );  
   }  
}  
```  
  
  **文字列 3.1415926This \= は、プロセスを停止します。**  
 **strtod \= 3.141593**  
 **次で停止: This stopped it**  
**文字列 \-10110134932This \= は、プロセスを停止します。**  
 **strtol \= \-2147483648**  
 **次で停止: This stopped it**  
**文字列 \= 10110134932**  
 **strtol \= 45 \(基数 2\)**   
 **停止されたスキャンの: 34932**  
 **strtol \= 4423 \(基数 4\)**   
 **停止されたスキャンの: 4932**  
 **strtol \= 2134108 \(基数 8\)**   
 **停止されたスキャンの: 932**   
## 同等の .NET Framework 関数  
 [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtol、wcstol、\_strtol\_l、\_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul、\_strtoul\_l、wcstoul、\_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof、\_atof\_l、\_wtof、\_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_create\_locale、\_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)