---
title: "_strtoui64、_wcstoui64、_strtoui64_l、_wcstoui64_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strtoui64
- _strtoui64_l
- _wcstoui64
- _wcstoui64_l
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
- _wcstoui64_l
- strtoui64_l
- wcstoui64
- _wcstoui64
- _strtoui64_l
- strtoui64
- _strtoui64
- wcstoui64_l
dev_langs: C++
helpviewer_keywords:
- _strtoui64_l function
- _wcstoui64_l function
- string conversion, to integers
- wcstoui64_l function
- _strtoui64 function
- _wcstoui64 function
- wcstoui64 function
- strtoui64_l function
- strtoui64 function
ms.assetid: 7fcb537e-4554-4ceb-a5b6-bc09244e72ef
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 73f648d9b895c7947892fa91fa1efd5d45773a45
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="strtoui64-wcstoui64-strtoui64l-wcstoui64l"></a>_strtoui64、_wcstoui64、_strtoui64_l、_wcstoui64_l
文字列を unsigned `__int64` 値に変換します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned __int64 _strtoui64(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned __int64 _wcstoui64(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned __int64 _strtoui64_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned __int64 _wcstoui64(  
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
 `_strtoui64` は、オーバーフローを引き起こす場合を除き、文字列 `nptr` で表現される値を返します。オーバーフローの場合は、`_UI64_MAX` を返します。 変換を実行できない場合、`_strtoui64` は 0 を返します。  
  
 `_UI64_MAX` は、LIMITS.H で定義されます。  
  
 `nptr` が `NULL` または `base` がゼロ以外で 2 未満または 36 を超える場合、`errno` は `EINVAL` に設定されます。  
  
 リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `_strtoui64`関数に変換`nptr`を`unsigned``__int64`です。 `_wcstoui64` 関数は、`_strtoui64` 関数のワイド文字バージョンで、`nptr` 引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。  
  
 どちらの関数も、数値の一部として認識できない文字に最初に遭遇した時点で `nptr` 文字列の読み取りを停止します。 これは、終端の null 文字または、`base` 以上の最初の数字の場合があります。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoui64`|`_strtoui64`|`_strtoui64`|`_wstrtoui64`|  
|`_tcstoui64_l`|`_strtoui64_l`|`_strtoui64_l`|`_wstrtoui64_l`|  
  
 現在のロケールの `LC_NUMERIC` カテゴリの設定に基づいて、`nptr` の小数点文字が認識されます。詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」をご覧ください。 _L サフィックスが付いていない関数は現在のロケールを使用します。`_strtoui64_l`と`_wcstoui64_l`せず、対応する関数と同じでは、`_l`サフィックスを代わりに渡されたロケール パラメーターを使用する点を除いて。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
 `endptr` が `NULL` 以外の場合は、スキャンを停止させた文字へのポインターを `endptr` が指す位置に格納します。 変換できなかった場合 (有効な数字が見つからなかった場合、または無効な base を指定した場合) は、`nptr` の値を `endptr` が指す位置に格納します。  
  
 `_strtoui64` は、`nptr` が次の形式の文字列を指すものと想定します。  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits`]  
  
 `whitespace` は、空白文字とタブ文字で構成でき、無視されます。`digits` は 1 つ以上の 10 進数です。 この形式に一致しない文字を見つけるとスキャンを停止します。 `base` が 2 ～ 36 の間の場合、数値の基数として使用されます。 `base` が 0 の場合、`nptr` が指す文字列の先頭の文字を使用して、基数を判断します。 最初の文字が 0 で、2 番目の文字が 'x' または 'X' 以外の場合、文字列は 8 進数と解釈されます。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。 最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。 'a' ～ 'z' (または 'A' ～ 'Z') の文字には、10 ～ 35 の値が割り当てられています。`base` よりも小さい値が割り当てられている文字のみ許可されます。 基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。 たとえば、`base` が 0 で、スキャンされた最初の文字が '0' の場合、8 進数と見なされ、'8' または '9' の文字が出現すると、スキャンは停止されます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_strtoui64`|\<stdlib.h>|  
|`_wcstoui64`|\<stdlib.h> または \<wchar.h>|  
|`_strtoui64_l`|\<stdlib.h>|  
|`_wcstoui64_l`|\<stdlib.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_strtoui64.c  
#include <stdio.h>  
  
unsigned __int64 atoui64(const char *szUnsignedInt) {  
   return _strtoui64(szUnsignedInt, NULL, 10);  
}  
  
int main() {  
   unsigned __int64 u = atoui64("18446744073709551615");  
   printf( "u = %I64u\n", u );  
}  
```  
  
```Output  
u = 18446744073709551615  
```  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod、_strtod_l、wcstod、_wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoul、_strtoul_l、wcstoul、_wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof、_atof_l、_wtof、_wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)