---
title: _strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wcsnicmp
- _strnicmp_l
- _wcsnicmp_l
- _strnicmp
- _mbsnicmp
- _mbsnicmp_l
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wcsnicmp_l
- _strnicmp
- _ftcsnicmp
- mbsnicmp_l
- _ftcsncicmp
- mbsnicmp
- _tcsncicmp
- _mbsnicmp
- _tcsnicmp
- strnicmp_l
- _wcsnicmp
- _wcsnicmp_l
- CORECRT_WSTRING/_wcsnicmp
- CORECRT_WSTRING/_wcsnicmp_l
- string/_strnicmp
- string/_strnicmp_l
dev_langs:
- C++
helpviewer_keywords:
- tcsnicmp function
- _tcsncicmp function
- _mbsnicmp_l function
- mbsnicmp_l function
- wcsnicmp_l function
- wcsnicmp function
- string comparison [C++], lowercase
- ftcsnicmp function
- strnicmp_l function
- strncmp function
- _strnicmp function
- strings [C++], comparing characters of
- _wcsnicmp_l function
- tcsncicmp function
- string comparison [C++], strncmp function
- _mbsnicmp function
- ftcsncicmp function
- _tcsnicmp function
- _ftcsncicmp function
- _strnicmp_l function
- _ftcsnicmp function
- characters [C++], comparing
- mbsnicmp function
- _wcsnicmp function
ms.assetid: df6e5037-4039-4c85-a0a6-21d4ef513966
caps.latest.revision: ''
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5bfee9f8799a4d7d1f55b85c2c12c77286ea4dac
ms.sourcegitcommit: 604907f77eb6c5b1899194a9877726f3e8c2dabc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="strnicmp-wcsnicmp-mbsnicmp-strnicmpl-wcsnicmpl-mbsnicmpl"></a>_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l
大文字小文字に関係なく、2 つの文字列の指定された数の文字を比較します。  
  
> [!IMPORTANT]
>  `_mbsnicmp` および `_mbsnicmp_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
int _strnicmp(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsnicmp(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsnicmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strnicmp_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsnicmp_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnicmp_l(  
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
 比較する文字数  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 次のように、部分文字列間の関係を示します。  
  
|戻り値|説明|  
|------------------|-----------------|  
|< 0|`string1` の部分文字列が `string2` の部分文字列より小さい。|  
|0|`string1` の部分文字列が `string2` の部分文字列と同じ。|  
|> 0|`string1` の部分文字列が `string2` の部分文字列より大きい。|  
  
 パラメーター検証エラーが発生した場合、これらの関数は `_NLSCMPERROR` を返します。これは、\<string.h> および \<mbstring.h> で定義されています。  
  
## <a name="remarks"></a>コメント  
 `_strnicmp` 関数は、`count` と `string1` の先頭の最大 `string2` 文字で序数に基づく比較を実行します。 比較は、各文字を小文字に変換することで、大文字小文字に関係なく行われます。 `_strnicmp` は `strncmp` の大文字と小文字を区別しないバージョンです。 `count` 文字を比較する前に、どちらかの文字列で終端の NULL 文字に到達すると比較は終了します。 `count` 文字を比較する前に、どちらかの文字列で終端の NULL 文字に到達したときに、文字列が等しい場合は短いほうの文字列が小さくなります。  
  
 ASCII 表の 91 から 96 の文字 ('['、'\\'、']'、'^'、'_'、および '\`') は、アルファベット文字より小さいものとして評価されます。 この順序付けは `stricmp` と同じです。  
  
 `_wcsnicmp` 関数と `_mbsnicmp` 関数は、`_strnicmp` 関数のワイド文字バージョンとマルチバイト文字バージョンです。 `_wcsnicmp` 関数の引数はワイド文字列で、`_mbsnicmp` 関数の引数はマルチバイト文字列です。 `_mbsnicmp` は現在のマルチバイト コード ページに基づいてマルチバイト文字のシーケンスを認識し、エラーが発生した場合は `_NLSCMPERROR` を返します 詳細については、「[コード ページ](../../c-runtime-library/code-pages.md)」を参照してください。 それ以外では、これらの関数の動作は同じです。 これらの関数はロケールの設定の影響を受けます。`_l` サフィックスが付いていないバージョンは、ロケールに依存する動作で現在のロケールを使用し、`_l` サフィックスが付いているバージョンは、渡される `locale` を代わりに使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
 これらのすべての関数では、パラメーターの検証が行われます。 `string1` または `string2` が null ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `_NLSCMPERROR` を返し、 `errno` を `EINVAL`に設定します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsncicmp`|`_strnicmp`|`_mbsnicmp`|`_wcsnicmp`|  
|`_tcsnicmp`|`_strnicmp`|`_mbsnbicmp`|`_wcsnicmp`|  
|`_tcsncicmp_l`|`_strnicmp_l`|`_mbsnicmp_l`|`_wcsnicmp_l`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_strnicmp`, `_strnicmp_l`|<string.h>|  
|`_wcsnicmp`, `_wcsnicmp_l`|<string.h> または <wchar.h>|  
|`_mbsnicmp`, `_mbsnicmp_l`|\<mbstring.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 [strncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md) の例を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [strcat、wcscat、_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp、wcscmp、_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy、wcscpy、_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn、wcsspn、_mbsspn、_mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)