---
title: "_strncoll、_wcsncoll、_mbsncoll、_strncoll_l、_wcsncoll_l、_mbsncoll_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strncoll
- _mbsncoll_l
- _wcsncoll
- _wcsncoll_l
- _mbsncoll
- _strncoll_l
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
- mbsncoll_l
- strncoll
- _wcsncoll
- _tcsnccoll
- _ftcsnccoll
- wcsncoll
- _mbsncoll
- wcsncoll_l
- strncoll_l
- _ftcsncoll
- _strncoll
- _tcsncoll
- mbsncoll
dev_langs: C++
helpviewer_keywords:
- _strncoll_l function
- code pages, using for string comparisons
- _strncoll function
- _mbsncoll function
- ftcsncoll function
- strncoll function
- _ftcsncoll function
- strncoll_l function
- wcsncoll function
- mbsncoll function
- _tcsncoll function
- _tcsnccoll function
- wcsncoll_l function
- tcsnccoll function
- mbsncoll_l function
- _mbsncoll_l function
- tcsncoll function
- _wcsncoll function
- strings [C++], comparing by code page
- _ftcsnccoll function
- ftcsnccoll function
- _wcsncoll_l function
ms.assetid: e659a5a4-8afe-4033-8e72-17ffd4bdd8e9
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 36c802c5406d4f142e4902ad75a7621f5a23ed70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="strncoll-wcsncoll-mbsncoll-strncolll-wcsncolll-mbsncolll"></a>_strncoll、_wcsncoll、_mbsncoll、_strncoll_l、_wcsncoll_l、_mbsncoll_l
ロケール固有の情報を使用して文字列を比較します。  
  
> [!IMPORTANT]
>  `_mbsncoll` および `_mbsncoll_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _strncoll(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsncoll(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsncoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strncoll_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsncoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsncoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `string1, string2`  
 Null で終わる比較対象の文字列。  
  
 `count`  
 比較する文字数。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 これらの関数は、以下のように、`string1` と `string2` の部分文字列の関係を示す値を返します。  
  
|戻り値|string1 と string2 との関係|  
|------------------|----------------------------------------|  
|< 0|`string1` は `string2` より小さい値です。|  
|0|`string1` は `string2` と同じです。|  
|> 0|`string1` が `string2` より大きくなっています。|  
  
 これらの各関数は、`_NLSCMPERROR` を返します。 `_NLSCMPERROR` を使用するには、STRING.h または MBSTRING.h をインクルードします。 `_wcsncoll` は、`string1` か `string2` に照合シーケンスのドメイン外のワイド文字コードが含まれている場合に失敗します。 エラーが発生した場合、`_wcsncoll` は `errno` に `EINVAL` を設定することがあります。 `_wcsncoll` の呼び出し時にエラーを確認するには、`errno` を 0 に設定し、`_wcsncoll` を呼び出した後 `errno` をチェックします。  
  
## <a name="remarks"></a>コメント  
 これらの関数は現在使用中のコード ページに従って `string1` と `string2` の最初の `count` 文字を大文字と小文字を区別せずに比較します。 これらの関数は、コード ページの文字セット順序と辞書式文字順序との間に相違点あり、この違いが文字列比較に関係がある場合にのみ使用します。 文字セット順序は、ロケールに依存します。 これらの関数のうち、`_l` サフィックスが付いていないバージョンは現在のロケールを使用しますが、`_l` サフィックスが付いているバージョンは渡されたロケールを使用します。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
 これらのすべての関数では、パラメーターの検証が行われます。 `string1` または `string2` が null ポインターの場合、または `count` が `INT_MAX` を超える場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `_NLSCMPERROR` を返し、`errno` を `EINVAL` に設定します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsnccoll`|`_strncoll`|`_mbsncoll`|`_wcsncoll`|  
|`_tcsncoll`|`_strncoll`|[_mbsnbcoll](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|`_wcsncoll`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_strncoll`, `_strncoll_l`|\<string.h>|  
|`_wcsncoll`, `_wcsncoll_l`|\<wchar.h> または \<string.h>|  
|`_mbsncoll`, `_mbsncoll_l`|\<mbstring.h>|  
  
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