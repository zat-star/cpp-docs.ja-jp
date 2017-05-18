---
title: "_strupr_s、_strupr_s_l、_mbsupr_s、_mbsupr_s_l、_wcsupr_s、_wcsupr_s_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strupr_s
- _strupr_s_l
- _mbsupr_s
- _wcsupr_s_l
- _mbsupr_s_l
- _wcsupr_s
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strupr_s
- mbsupr_s
- wcsupr_s
- _mbsupr_s_l
- mbsupr_s_l
- wcsupr_s_l
- _wcsupr_s
- _tcsupr_s_l
- _mbsupr_s
- _tcsupr_s
- strupr_s_l
- _wcsupr_s_l
- _strupr_s
- _strupr_s_l
dev_langs:
- C++
helpviewer_keywords:
- mbsupr_s_l function
- strupr_s_l function
- _wcsupr_s_l function
- _tcsupr_s_l function
- mbsupr_s function
- _wcsupr_s function
- uppercase, converting strings to
- tcsupr_s function
- string conversion [C++], case
- strupr_s function
- wcsupr_s_l function
- _mbsupr_s function
- _mbsupr_s_l function
- _strupr_s_l function
- tcsupr_s_l function
- strings [C++], case
- converting case, CRT functions
- _tcsupr_s function
- strings [C++], converting case
- _strupr_s function
- wcsupr_s function
ms.assetid: 82d3a273-9f6f-4a26-9560-919d891e4581
caps.latest.revision: 30
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: da1300ca4ec32d1d771b8a00e0b1cfdf207a58a8
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="struprs-struprsl-mbsuprs-mbsuprsl-wcsuprs-wcsuprsl"></a>_strupr_s、_strupr_s_l、_mbsupr_s、_mbsupr_s_l、_wcsupr_s、_wcsupr_s_l
渡された現在のロケールまたは指定のロケールを使用して、文字列を大文字に変換します。 これらのバージョンの [_strupr、_strupr_l、_mbsupr、_mbsupr_l、_wcsupr_l、_wcsupr](../../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」にあるとおり、セキュリティが強化されています。  
  
> [!IMPORTANT]
>  `_mbsupr_s` および `_mbsupr_s_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _strupr_s(  
   char *str,  
   size_t numberOfElements  
);  
errno_t _wcsupr_s(  
   wchar_t * str,  
   size_t numberOfElements  
);  
errno_t _strupr_s_l(  
   char * str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
errno_t _wcsupr_s_l(  
   wchar_t * str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
errno_t _mbsupr_s(  
   unsigned char *str,  
   size_t numberOfElements  
);  
errno_t _mbsupr_s_l(  
   unsigned char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
template <size_t size>  
errno_t _strupr_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wcsupr_s(  
   wchar_t (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _strupr_s_l(  
   char (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _wcsupr_s_l(  
   wchar_t (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _mbsupr_s(  
   unsigned char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _mbsupr_s_l(  
   unsigned char (&str)[size],  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `str`  
 大文字にする文字列。  
  
 `numberOfElements`  
 バッファーのサイズ。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。失敗した場合は 0 以外のエラー コードを返します。  
  
 これらの関数では、パラメーターの検証が行われます。 `str` が `NULL` ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、関数は `EINVAL` を返し、`errno` を `EINVAL` に設定します。 `numberOfElements` が文字列の長さ未満の場合、関数は `ERANGE` 返し、`errno` を `ERANGE` に設定します。  
  
## <a name="remarks"></a>コメント  
 `_strupr_s` 関数は、`str` 内の小文字を同じ位置で大文字に変換します。 `_wcsupr_s` 関数は、`_strupr_s` 関数のワイド文字バージョンです。 `_mbsupr_s` 関数は、`_strupr_s` のマルチバイト文字バージョンです。  
  
 変換は、ロケールの `LC_CTYPE` カテゴリの設定により決定されます。 他の文字は影響を受けません。 `LC_CTYPE` の詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。 `_l` サフィックスが付いていないこれらの関数のバージョンは、現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、代わりに渡されたロケールを使用する点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
 これらの関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) を使用します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsupr_s`|`_strupr_s`|`_mbsupr_s`|`_wcsupr_s`|  
|`_tcsupr_s_l`|`_strupr_s_l`|`_mbsupr_s_l`|`_wcsupr_s_l`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_strupr_s`, `_strupr_s_l`|\<string.h>|  
|`_wcsupr_s`, `_wcsupr_s_l`, `_mbsupr_s`, `_mbsupr_s_l`|\<string.h> または \<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 [_strlwr_s、_strlwr_s_l、_mbslwr_s、_mbslwr_s_l、_wcslwr_s、_wcslwr_s_l](../../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)の例を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [_strlwr_s、_strlwr_s_l、_mbslwr_s、_mbslwr_s_l、_wcslwr_s、_wcslwr_s_l](../../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)
