---
title: "strtold、_strtold_l、wcstold、_wcstold_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcstold
- strtold
- _strtold_l
- _wcstold_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcstold_l
- _wcstold_l
- _tcstold
- strtold
- _strtold_l
- wcstold
dev_langs: C++
ms.assetid: 928c0c9a-bc49-445b-8822-100eb5954115
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3ff8aa3f62a50ae544de61953054bd8906ed5971
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="strtold-strtoldl-wcstold-wcstoldl"></a>strtold、_strtold_l、wcstold、_wcstold_l
文字列を long double 精度浮動小数点値に変換します。  
  
## <a name="syntax"></a>構文  
  
```  
long double strtold(  
   const char *nptr,  
   char **endptr   
);  
long double _strtold_l(  
   const char *nptr,  
   char **endptr,  
   _locale_t locale  
);  
long double wcstold(  
   const wchar_t *nptr,  
   wchar_t **endptr   
);  
long double wcstold_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nptr`  
 NULL で終わる変換対象の文字列。  
  
 `endptr`  
 スキャンの終了位置を示す文字へのポインター。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `strtold`浮動小数点数としての値を返します、 `long double`、形式がオーバーフローを発生する場合を除く — +/-関数が返す場合は、`HUGE_VALL`です。 `HUGE_VALL` の符号は、表現できない値の符号と一致します。 変換を実行できない場合、またはアンダーフローが発生する場合、`strtold` 関数は 0 を返します。  
  
 `wcstold` 関数の戻り値は、`strtold` 関数の戻り値と同じです。 「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、両方の関数に対して、オーバーフローまたはアンダーフローが発生し、無効なパラメーター ハンドラーが呼び出された場合、`errno` は `ERANGE` に設定されます。  
  
 リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 各関数は、入力文字列 `nptr` を `long double` に変換します。 `strtold` 関数は `nptr` を long double 精度値に変換します。 `strtold` 関数は、数値の一部として認識できない文字を最初に見つけた時点で、文字列 `nptr` の読み取りを終了します。 数値として認識できない最初の文字が、終端の NULL 文字の場合もあります。 `strtold` のワイド文字バージョンは `wcstold` です。`nptr` 引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstold`|`strtold`|`strtold`|`wcstold`|  
|`_tcstold_l`|`_strtold_l`|`_strtold_l`|`_wcstold_l`|  
  
 現在のロケールの `LC_NUMERIC` カテゴリの設定によって、`nptr` の小数点文字が認識されます。 詳細については、「[setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。 `_l` サフィックスが付いていない関数は、現在のロケールを使用します。`_strtold_l` および `_wcstold_l` は、渡されたロケールを代わりに使用する点を除いて `_strtold` および `_wcstold` と同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `endptr` が `NULL` 以外の場合は、スキャンを停止させた文字へのポインターを `endptr` が指す位置に格納します。 変換できなかった場合 (有効な数字が見つからなかった場合、または無効な base を指定した場合) は、`nptr` の値を `endptr` が指す位置に格納します。  
  
 `strtold` は、`nptr` が次の形式の文字列を指すものと想定します。  
  
 [`whitespace`] [`sign`] [`digits`] [`.digits`] [ {`d` &#124; `D` &#124; `e` &#124; `E`}[`sign`]`digits`]  
  
 `whitespace` はスペースやタブで構成され、無視されます。`sign` はプラス (`+`) またはマイナス (`-`) のいずれかで、`digits` は 1 つ以上の 10 進数字です。 小数点文字の前に数字がない場合は、少なくとも 1 つの数字が小数点文字の後に必要です。 10 進数の後には指数部を指定できます。指数部は、指数部の開始文字 (`d`、`D`、`e`、または `E`) および必要に応じて符号付き整数で構成されます。 指数部と小数点文字のいずれも指定されない場合は、文字列の最後の数字の後に小数点文字が続くと想定されます。 この形式に一致しない文字を見つけるとスキャンを停止します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`strtold`, `_strtold_l`|\<stdlib.h>|  
|`wcstold`, `_wcstold_l`|\<stdlib.h> または \<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_strtold.c  
// Build with: cl /W4 /Tc crt_strtold.c  
// This program uses strtold to convert a  
// string to a long double-precision value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char *string;  
   char *stopstring;  
   long double x;  
  
   string = "3.1415926535898This stopped it";  
   x = strtold(string, &stopstring);  
   printf("string = %s\n", string);  
   printf("   strtold = %.13Lf\n", x);  
   printf("   Stopped scan at: %s\n\n", stopstring);  
}  
```  
  
```Output  
string = 3.1415926535898This stopped it  
   strtold = 3.1415926535898  
   Stopped scan at: This stopped it  
  
```  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod、_strtod_l、wcstod、_wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol、wcstol、_strtol_l、_wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul、_strtoul_l、wcstoul、_wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof、_atof_l、_wtof、_wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_create_locale、_wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)