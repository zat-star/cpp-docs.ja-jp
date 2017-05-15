---
title: "_stricoll、_wcsicoll、_mbsicoll、_stricoll_l、_wcsicoll_l、_mbsicoll_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsicoll_l
- _stricoll_l
- _mbsicoll
- _wcsicoll_l
- _wcsicoll
- _stricoll
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
- stricoll
- _stricoll
- _wcsicoll
- mbsicoll_l
- _mbsicoll
- _ftcsicoll
- wcsicoll_l
- _tcsicoll
- mbsicoll
- stricoll_l
dev_langs:
- C++
helpviewer_keywords:
- code pages, using for string comparisons
- _ftcsicoll function
- _mbsicoll_l function
- _mbsicoll function
- mbsicoll function
- stricoll function
- tcsicoll function
- string comparison [C++], culture-specific
- _tcsicoll function
- _stricoll function
- _stricoll_l function
- _wcsicoll function
- mbsicoll_l function
- stricoll_l function
- strings [C++], comparing by code page
- ftcsicoll function
ms.assetid: 8ec93016-5a49-49d2-930f-721566661d82
caps.latest.revision: 22
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 4291a8027dd01c705642af0d3651cc2fbf1277cb
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="stricoll-wcsicoll-mbsicoll-stricolll-wcsicolll-mbsicolll"></a>_stricoll、_wcsicoll、_mbsicoll、_stricoll_l、_wcsicoll_l、_mbsicoll_l
ロケール固有の情報を使用して文字列を比較します。  
  
> [!IMPORTANT]
>  `_mbsicoll` および `_mbsicoll_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _stricoll(  
   const char *string1,  
   const char *string2   
);  
int _wcsicoll(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbsicoll(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _stricoll_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale  
);  
int _wcsicoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale  
);  
int _mbsicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `string1, string2`  
 Null で終わる比較対象の文字列。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 これらの関数との関係を示す値を返します`string1`に`string2`、次のようにします。  
  
|戻り値|string1 と string2 との関係|  
|------------------|----------------------------------------|  
|< 0|`string1` が `string2` より小さい|  
|0|`string1` が `string2` と同じ|  
|> 0|`string1` が `string2` より大きい|  
|`_NLSCMPERROR`|エラーが発生しました。|  
  
 これらの各関数は、`_NLSCMPERROR` を返します。 `_NLSCMPERROR` を使用するには、`STRING.H` または `MBSTRING.H` をインクルードします。 `_wcsicoll` は、`string1` か `string2` に照合シーケンスのドメイン外のワイド文字コードが含まれている場合に失敗します。 エラーが発生した場合、`_wcsicoll` は `errno` に `EINVAL` を設定することがあります。 `_wcsicoll` の呼び出し時にエラーを確認するには、`errno` を 0 に設定し、`errno` を呼び出した後 `_wcsicoll` をチェックします。  
  
## <a name="remarks"></a>コメント  
 これらの各関数は、現在使用中のコード ページに基づき、大文字小文字を区別せずに `string1` および `string2` を比較します。 これらの関数は、現在のコード ページの文字セット順序と辞書式文字順序との間に相違点があり、この違いが文字列比較に関係がある場合にのみ使用します。  
  
 `_stricmp` と `_stricoll` では、`_stricmp` による比較は `LC_CTYPE` の影響を受けるのに対し、`_stricoll` による比較は、ロケールの `LC_CTYPE` カテゴリと `LC_COLLATE` カテゴリに基づくという点が異なります。 `LC_COLLATE`カテゴリの詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」および「[ロケールのカテゴリ](../../c-runtime-library/locale-categories.md)」をご覧ください。 `_l` サフィックスが付いていないこれらの関数のバージョンは、現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、代わりに渡されたロケールを使用する点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 これらのすべての関数では、パラメーターの検証が行われます。 `string1` か `string2` が `NULL` ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `_NLSCMPERROR` を返し、`errno` を `EINVAL` に設定します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsicoll`|`_stricoll`|`_mbsicoll`|`_wcsicoll`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_stricoll`, `_stricoll_l`|\<string.h>|  
|`_wcsicoll`, `_wcsicoll_l`|\<wchar.h>, \<string.h>|  
|`_mbsicoll`, `_mbsicoll_l`|\<mbstring.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [ロケール](../../c-runtime-library/locale.md)   
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll 系関数](../../c-runtime-library/strcoll-functions.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbsnbcoll、_mbsnbcoll_l、_mbsnbicoll、_mbsnbicoll_l](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcmp、wcscmp、_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)
