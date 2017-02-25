---
title: "strtol、wcstol、_strtol_l、_wcstol_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strtol"
  - "wcstol"
  - "_strtol_l"
  - "_wcstol_l"
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
  - "_wcstol_l"
  - "strtol"
  - "_tcstol"
  - "wcstol"
  - "_strtol_l"
  - "_tcstol_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtol_l 関数"
  - "_tcstol 関数"
  - "_wcstol_l 関数"
  - "文字列変換, 整数への"
  - "strtol 関数"
  - "strtol_l 関数"
  - "tcstol 関数"
  - "wcstol 関数"
  - "wcstol_l 関数"
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# strtol、wcstol、_strtol_l、_wcstol_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列を長整数値に変換します。  
  
## 構文  
  
```  
long strtol(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
long wcstol(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
long _strtol_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
long _wcstol_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `nptr`  
 NULL で終わる変換対象の文字列。  
  
 `endptr`  
 スキャンの終了位置を示す文字へのポインター。  
  
 `base`  
 使用する基数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 `strtol` は、オーバーフローを引き起こす場合を除き、文字列 `nptr` で表現される値を返します。オーバーフローの場合は、`LONG_MAX` または `LONG_MIN` を返します。  変換を実行できない場合、`strtol` は 0 を返します。  `wcstol` 関数の戻り値は、`strtol` 関数の戻り値と同じです。  両方の関数とも、オーバーフローまたはアンダーフローが発生した場合、`errno` は `ERANGE` に設定されます。  
  
 リターン コードの詳細については、「[\_doserrno, errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `strtol` 関数は `nptr` を `long` に変換します。  `strtol` 関数は、数値の一部として認識できない文字を最初に見つけた時点で、文字列 `nptr` の読み取りを終了します。  これは、終端の null 文字または、`base` 以上の最初の数字の場合があります。  
  
 `wcstol` 関数は、`strtol` 関数のワイド文字バージョンで、`nptr` 引数はワイド文字列です。  それ以外では、これらの関数の動作は同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcstol`|`strtol`|`strtol`|`wcstol`|  
|`_tcstol_l`|`_strtol_l`|`_strtol_l`|`_wcstol_l`|  
  
 現在のロケールの `LC_NUMERIC`  カテゴリの設定に基づいて、`nptr` の小数点文字が認識されます。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていない関数は、現在のロケールを使用します。`_strtol_l` および `_wcstol_l` は、渡されたロケールを使用することを除いて、`_l` サフィックスが付いていない対応する関数と同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `endptr` が `NULL` 以外の場合は、スキャンを停止させた文字へのポインターを `endptr` が指す位置に格納します。  変換できなかった場合 \(有効な数字が見つからなかった場合、または無効な base を指定した場合\) は、`nptr` の値を `endptr` が指す位置に格納します。  
  
 `strtol` は、`nptr` が次の形式の文字列を指すものと想定します。  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits`\]  
  
 `whitespace` は、空白文字とタブ文字で構成でき、無視されます。`digits` は 1 つ以上の 10 進数です。  この形式に一致しない文字を見つけるとスキャンを停止します。  `base` が 2 ～ 36 の間の場合、数値の基数として使用されます。  `base` が 0 の場合、`nptr` が指す文字列の先頭の文字を使用して、基数を判断します。  最初の文字が 0 で、2 番目の文字が 'x' または 'X' 以外の場合、文字列は 8 進数と解釈されます。  最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。  最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。  'a' ～ 'z' \(または 'A' ～ 'Z'\) の文字には、10 ～ 35 の値が割り当てられています。`base` よりも小さい値が割り当てられている文字のみ許可されます。  基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。  たとえば、`base` が 0 で、スキャンされた最初の文字が '0' の場合、8 進数と見なされ、'8' または '9' の文字が出現すると、スキャンは停止されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`strtol`|\<stdlib.h\>|  
|`wcstol`|\<stdlib.h\> または \<wchar.h\>|  
|`_strtol_l`|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [strtod](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md) の例を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Convert::ToInt64](https://msdn.microsoft.com/en-us/library/system.convert.toint64.aspx)  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod、\_strtod\_l、wcstod、\_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoul、\_strtoul\_l、wcstoul、\_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof、\_atof\_l、\_wtof、\_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)