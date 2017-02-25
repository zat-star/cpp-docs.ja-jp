---
title: "strtoimax、_strtoimax_l、wcstoimax、_wcstoimax_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcstoimax"
  - "_wcstoimax_l"
  - "_strtoimax_l"
  - "strtoimax"
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
  - "wcstoimax"
  - "_tcstoimax"
  - "strtoimax"
  - "_wcstoimax_l"
  - "_strtoimax_l"
  - "_tcstoimax_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtoimax_l 関数"
  - "_wcstoimax_l 関数"
  - "変換関数"
  - "strtoimax 関数"
  - "wcstoimax 関数"
ms.assetid: 4530d3dc-aaac-4a76-b7cf-29ae3c98d0ae
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# strtoimax、_strtoimax_l、wcstoimax、_wcstoimax_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

サポートされる最大の符号付き整数型の整数値に文字列を変換します。  
  
## 構文  
  
```  
intmax_t strtoimax(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
intmax_t wcstoimax(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
intmax_t _strtoimax_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
intmax_t _wcstoimax_l(  
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
 `strtoimax` は、オーバーフローを引き起こす場合を除き、文字列 `nptr` で表現される値を返します。オーバーフローの場合は、`INTMAX_MAX` または `INTMAX_MIN` を返し、`errno` は `ERANGE` に設定されます。  この関数は、変換を実行できない場合には 0 を返します。  `wcstoimax` 関数の戻り値は、`strtoimax` 関数の戻り値と同じです。  
  
 `INTMAX_MAX` および `INTMAX_MIN` は、stdint.h で定義されます。  
  
 `nptr` が `NULL` または `base` がゼロ以外で 2 未満または 36 を超える場合、`errno` は `EINVAL` に設定されます。  
  
 リターン コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `strtoimax` 関数は、`nptr` を `intmax_t` に変換します。  `strtoimax` のワイド文字バージョンは `wcstoimax` です。`nptr` 引数はワイド文字列です。  それ以外では、これらの関数の動作は同じです。  どちらの関数も、数値の一部として認識できない文字に最初に遭遇した時点で `nptr` 文字列の読み取りを停止します。  これは、終端の null 文字または、`base` 以上の最初の数字の場合があります。  
  
 ロケールの `LC_NUMERIC` カテゴリの設定に基づいて、`nptr` の小数点文字が認識されます。詳細については、「[setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていない関数は現在のロケールを使用します。`_strtoimax_l` および `_wcstoimax_l` は、渡されたロケールを代わりに使用する点を除いて、`_l` サフィックスが付いていない関数と同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `endptr` が `NULL` 以外の場合は、スキャンを停止させた文字へのポインターを `endptr` が指す位置に格納します。  変換できなかった場合 \(有効な数字が見つからなかった場合、または無効な base を指定した場合\) は、`nptr` の値を `endptr` が指す位置に格納します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcstoimax`|`strtoimax`|`strtoimax`|`wcstoimax`|  
|`_tcstoimax_l`|`strtoimax_l`|`_strtoimax_l`|`_wcstoimax_l`|  
  
 `strtoimax` は、`nptr` が次の形式の文字列を指すものと想定します。  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits` &#124; `letters`\]  
  
 `whitespace` はスペースやタブ文字で構成することができ、無視されます。`digits` は 1 つ以上の 10 進数です。`letters` は 1 つ以上の文字 \('a' ～ 'z' または 'A' ～ 'Z'\) です。  この形式に一致しない文字を見つけるとスキャンを停止します。  `base` が 2 ～ 36 の間の場合、数値の基数として使用されます。  `base` が 0 の場合、`nptr` が指す文字列の先頭の文字を使用して、基数を判断します。  最初の文字が '0' で、2 番目の文字が 'x' または 'X' 以外の場合、文字列は 8 進数と解釈されます。  最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。  最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。  'a' ～ 'z' \(または 'A' ～ 'Z'\) の文字には、10 ～ 35 の値が割り当てられています。`base` よりも小さい値が割り当てられている文字のみ許可されます。  基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。  たとえば、`base` が 0 で、スキャンされた最初の文字が '0' の場合、8 進数と見なされ、'8' または '9' の文字が出現すると、スキャンは停止されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`strtoimax`, `_strtoimax_l`, `wcstoimax`, `_wcstoimax_l`|\<inttypes.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod、\_strtod\_l、wcstod、\_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol、wcstol、\_strtol\_l、\_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul、\_strtoul\_l、wcstoul、\_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [strtoumax、\_strtoumax\_l、wcstoumax、\_wcstoumax\_l](../Topic/strtoumax,%20_strtoumax_l,%20wcstoumax,%20_wcstoumax_l.md)   
 [atof、\_atof\_l、\_wtof、\_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)