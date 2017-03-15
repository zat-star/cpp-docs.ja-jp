---
title: "strtoumax、_strtoumax_l、wcstoumax、_wcstoumax_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcstoumax_l
- _strtoumax_l
- wcstoumax
- strtoumax
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
- wcstoumax
- _tcstoumax
- _strtoumax_l
- _wcstoumax_l
- _tcstoumax_l
- strtoumax
dev_langs:
- C++
helpviewer_keywords:
- _strtoumax_l function
- conversion functions
- wcstoumax function
- _wcstoumax_l function
- strtoumax function
ms.assetid: 566769f9-495b-4508-b9c6-02217a578897
caps.latest.revision: 5
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: e855cf1733b0eeee0bf192e33335525452dbe8c8
ms.lasthandoff: 02/24/2017

---
# <a name="strtoumax-strtoumaxl-wcstoumax-wcstoumaxl"></a>strtoumax、_strtoumax_l、wcstoumax、_wcstoumax_l
サポートされる最大の符号なし整数型の整数値に文字列を変換します。  
  
## <a name="syntax"></a>構文  
  
```  
uintmax_t strtoumax(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
uintmax_t _strtoumax_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
uintmax_t wcstoumax(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
uintmax_t _wcstoumax_l(  
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
 `strtoumax` はオーバーフローについての変換された値 (ある場合) または `UINTMAX_MAX` を返します。 変換を実行できない場合、`strtoumax` は 0 を返します。 `wcstoumax` 関数の戻り値は、`strtoumax` 関数の戻り値と同じです。 両方の関数とも、オーバーフローまたはアンダーフローが発生した場合、`errno` は `ERANGE` に設定されます。  
  
 リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 これらの関数は入力文字列 `nptr` を `uintmax_t` の整数値に変換します。  
  
 `strtoumax` 関数は、数値の一部として認識できない文字を最初に見つけた時点で、文字列 `nptr` の読み取りを終了します。 これは、終端の null 文字または、`base` 以上の最初の数字の場合があります。 ロケールの `LC_NUMERIC` カテゴリの設定によって、`nptr` の小数点文字が認識されます。 詳細については、「[setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。 `strtoumax` と `wcstoumax` は現在のロケールを使用します。`_strtoumax_l` と `_wcstoumax_l` は渡されたロケールを代わりに使用するという点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `endptr` が `NULL` 以外の場合は、スキャンを停止させた文字へのポインターを `endptr` が指す位置に格納します。 変換できなかった場合 (有効な数字が見つからなかった場合、または無効な base を指定した場合) は、`nptr` の値を `endptr` が指す位置に格納します。  
  
 `strtoumax` のワイド文字バージョンは `wcstoumax` です。`nptr` 引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoumax`|`strtoumax`|`strtoumax`|`wcstoumax`|  
|`_tcstoumax_l`|`strtoumax_l`|`_strtoumax_l`|`_wcstoumax_l`|  
  
 `strtoumax` は、`nptr` が次の形式の文字列を指すものと想定します。  
  
 [`whitespace`] [{`+` &#124; `–`}] [`0` [{ `x` &#124; `X` }]] [`digits` &#124; [`letters`]]  
  
 `whitespace` はスペースやタブ文字で構成することができ、無視されます。`digits` は&1; つ以上の&10; 進数です。`letters` は&1; つ以上の文字 ('a' ～ 'z' または 'A' ～ 'Z') です。 この形式に一致しない文字を見つけるとスキャンを停止します。 `base` が 2 ～ 36 の間の場合、数値の基数として使用されます。 `base` が 0 の場合、`nptr` が指す文字列の先頭の文字を使用して、基数を判断します。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' 以外の場合、文字列は&8; 進数と解釈されます。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は&16; 進数と解釈されます。 最初の文字が '1' ～ '9' の間の数値の場合、文字列は&10; 進数と解釈されます。 'a' ～ 'z' (または 'A' ～ 'Z') の文字には、10 ～ 35 の値が割り当てられています。`base` よりも小さい値が割り当てられている文字のみ許可されます。 基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。 たとえば、`base` が 0 で、スキャンされた最初の文字が '0' の場合、8 進数と見なされ、'8' または '9' の文字が出現すると、スキャンは停止されます。 `strtoumax` により、正符号 (`+`) または負符号 (`–`) のプレフィックスを使用できます。先頭の負符号は、戻り値が変換された文字列の絶対値の&2; つの補数であることを示します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`strtoumax`|\<stdlib.h>|  
|`wcstoumax`|\<stdlib.h> または \<wchar.h>|  
|`_strtoumax_l`|\<stdlib.h>|  
|`_wcstoumax_l`|\<stdlib.h> または \<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 [strtod](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md) の例をご覧ください。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod、_strtod_l、wcstod、_wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoimax、_strtoimax_l、wcstoimax、_wcstoimax_l](../../c-runtime-library/reference/strtoimax-strtoimax-l-wcstoimax-wcstoimax-l.md)   
 [strtol、wcstol、_strtol_l、_wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul、_strtoul_l、wcstoul、_wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [strtoll、_strtoll_l、wcstoll、_wcstoll_l](../../c-runtime-library/reference/strtoll-strtoll-l-wcstoll-wcstoll-l.md)   
 [atof、_atof_l、_wtof、_wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)
