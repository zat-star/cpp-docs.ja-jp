---
title: "strtoul、_strtoul_l、wcstoul、_wcstoul_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcstoul_l
- _strtoul_l
- strtoul
- wcstoul
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
- strtoul
- _tcstoul
- wcstoul
dev_langs:
- C++
helpviewer_keywords:
- _wcstoul_l function
- _tcstoul function
- _strtoul_l function
- string conversion, to integers
- wcstoul function
- strtoul function
- wcstoul_l function
- strtoul_l function
- tcstoul function
ms.assetid: 38f2afe8-8178-4e0b-8bbe-d5c6ad66e3ab
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 8916b8645b212f075b9ea575e4bb19e11c5ee975
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="strtoul-strtoull-wcstoul-wcstoull"></a>strtoul、_strtoul_l、wcstoul、_wcstoul_l
文字列を符号なし長整数の値に変換します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned long strtoul(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned long _strtoul_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned long wcstoul(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned long _wcstoul_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nptr`  
 NULL で終わる変換対象の文字列。  
  
 `endptr`  
 スキャンの終了位置を示す文字へのポインター。  
  
 `base`  
 使用する基数。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `strtoul` はオーバーフローについての変換された値 (ある場合) または `ULONG_MAX` を返します。 変換を実行できない場合、`strtoul` は 0 を返します。 `wcstoul` 関数の戻り値は、`strtoul` 関数の戻り値と同じです。 両方の関数とも、オーバーフローまたはアンダーフローが発生した場合、`errno` は `ERANGE` に設定されます。  
  
 リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 これらの関数は入力文字列 `nptr` を `unsigned` `long` に変換します。  
  
 `strtoul` 関数は、数値の一部として認識できない文字を最初に見つけた時点で、文字列 `nptr` の読み取りを終了します。 これは、終端の null 文字または、`base` 以上の最初の数字の場合があります。 ロケールの `LC_NUMERIC` カテゴリの設定に基づいて、`nptr` の小数点文字が認識されます。詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」をご覧ください。 `strtoul` と `wcstoul` は現在のロケールを使用します。`_strtoul_l` と `_wcstoul_l` は代わりに渡されたロケール使用するという点を除いて機能は同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
 `endptr` が `NULL` 以外の場合は、スキャンを停止させた文字へのポインターを `endptr` が指す位置に格納します。 変換できなかった場合 (有効な数字が見つからなかった場合、または無効な base を指定した場合) は、`nptr` の値を `endptr` が指す位置に格納します。  
  
 `wcstoul` 関数は、`strtoul` 関数のワイド文字バージョンで、`nptr` 引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoul`|`strtoul`|`strtoul`|`wcstoul`|  
|`_tcstoul_l`|`strtoul_l`|`_strtoul_l`|`_wcstoul_l`|  
  
 `strtoul` は、`nptr` が次の形式の文字列を指すものと想定します。  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits`]  
  
 `whitespace` は、空白文字とタブ文字で構成でき、無視されます。`digits` は 1 つ以上の 10 進数です。 この形式に一致しない文字を見つけるとスキャンを停止します。 `base` が 2 ～ 36 の間の場合、数値の基数として使用されます。 `base` が 0 の場合、`nptr` が指す文字列の先頭の文字を使用して、基数を判断します。 最初の文字が 0 で、2 番目の文字が 'x' または 'X' 以外の場合、文字列は 8 進数と解釈されます。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。 最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。 'a' ～ 'z' (または 'A' ～ 'Z') の文字には、10 ～ 35 の値が割り当てられています。`base` よりも小さい値が割り当てられている文字のみ許可されます。 基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。 たとえば、`base` が 0 で、スキャンされた最初の文字が '0' の場合、8 進数と見なされ、'8' または '9' の文字が出現すると、スキャンは停止されます。 `strtoul` では正符号 (`+`) または負符号 (`-`) のプレフィックスを使用できます。先頭の負符号は戻り値の符号が反転されることを表します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`strtoul`|\<stdlib.h>|  
|`wcstoul`|\<stdlib.h> または \<wchar.h>|  
|`_strtoul_l`|\<stdlib.h>|  
|`_wcstoul_l`|\<stdlib.h> または \<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 [strtod](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md) の例をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod、_strtod_l、wcstod、_wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol、wcstol、_strtol_l、_wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [atof、_atof_l、_wtof、_wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)
