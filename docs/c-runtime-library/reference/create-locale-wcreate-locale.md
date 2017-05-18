---
title: "_create_locale、_wcreate_locale | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _create_locale
- __create_locale
- _wcreate_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- create_locale
- _create_locale
- __create_locale
dev_langs:
- C++
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
caps.latest.revision: 23
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
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: 5068d509e335fd99246d5dff5fd51f2b0b1493b6
ms.contentlocale: ja-jp
ms.lasthandoff: 02/28/2017

---
# <a name="createlocale-wcreatelocale"></a>_create_locale、_wcreate_locale
ロケール オブジェクトを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
_locale_t _create_locale(  
   int category,  
   const char *locale   
);  
_locale_t _wcreate_locale(  
   int category,  
   const wchar_t *locale   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `category`  
 カテゴリ。  
  
 `locale`  
 ロケールの指定子。  
  
## <a name="return-value"></a>戻り値  
 有効な `locale` と `category` が指定された場合、`_locale_t` オブジェクトとして指定のロケール設定を返します。 プログラムの現在のロケール設定は変更されません。  
  
## <a name="remarks"></a>コメント  
 `_create_locale` 関数は、多くの CRT 関数のロケール固有のバージョン (`_l` のサフィックスを持つ関数) で使用するために、特定の地域固有の設定を表すオブジェクトを作成できます。 動作は `setlocale` に似ていますが、指定したロケール設定を現在の環境に適用する代わりに、返される `_locale_t` 構造体に設定が保存される点が異なります。 `_locale_t` 構造体は、不要になったときに [_free_locale](../../c-runtime-library/reference/free-locale.md) を使用して解放する必要があります。  
  
 `_wcreate_locale` 関数は、`_create_locale` 関数のワイド文字バージョンです。`locale` 関数の引数 `_wcreate_locale` は、ワイド文字列です。 それ以外では、`_wcreate_locale` と `_create_locale` の動作は同じです。  
  
 `category` 引数は、影響を受けるロケール固有の動作の一部を指定します。 `category` に使用するフラグ、および影響されるプログラムの一部を次の表に示します。  
  
 `LC_ALL`  
 次に示すように、すべてのカテゴリです。  
  
 `LC_COLLATE`  
 `strcoll`、`_stricoll`、`wcscoll`、`_wcsicoll`、`strxfrm`、`_strncoll`、`_strnicoll`、`_wcsncoll`、`_wcsnicoll`、および `wcsxfrm` の各関数。  
  
 `LC_CTYPE`  
 文字処理関数の (影響を受けない `isdigit`、`isxdigit`、`mbstowcs`、および `mbtowc` を除く)。  
  
 `LC_MONETARY`  
 `localeconv` 関数が返す通貨形式情報。  
  
 `LC_NUMERIC`  
 `printf` などの書式化出力ルーチン、データ変換ルーチン、および `localeconv` が返す通貨形式以外の形式情報で使用される小数点文字。 小数点文字に加え、`LC_NUMERIC` は桁区切り記号、および [localeconv](../../c-runtime-library/reference/localeconv.md) によって返されるグループ化コントロールの文字列を設定します。  
  
 `LC_TIME`  
 `strftime` および `wcsftime` 関数。  
  
 この関数は、`category`、および `locale` パラメーターを検証します。 カテゴリのパラメーターが前の表で指定された値ではない場合、または、`locale` が `NULL` の場合、関数は `NULL` を返します。  
  
 The `locale` 引数は、ロケールを指定する文字列へのポインターです。 `locale` 引数の形式については、「[ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)」を参照してください。  
  
 `locale` 引数には、ロケール名、言語識別文字列、言語識別文字列と国/地域コード、コード ページ、または言語識別文字列、国/地域コード、コード ページを指定できます。 使用できるロケール名、言語、国/地域コード、およびコード ページのセットには、1 文字に 2 バイトを超えるデータを必要とする (UTF-7、UTF-8 など) コード ページを除き、Windows の NLS API でサポートされるすべてが含まれています。 UTF-7、UTF-8 などのコード ページを指定すると、`_create_locale` は失敗し、NULL を返します。 `_create_locale` でサポートされているロケール名のセットについては、「[ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)」に記載されています。 `_create_locale` でサポートされる言語識別文字列と国/地域識別文字列は、「[言語識別文字列](../../c-runtime-library/language-strings.md)」および「[国/地域識別文字列](../../c-runtime-library/country-region-strings.md)」に記載されています。  
  
 ロケール設定の詳細については、「[setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。  
  
 この関数の以前の名前 `__create_locale` (先頭に 2 個のアンダースコア) は、使用されなくなりました。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_create_locale`|\<locale.h>|  
|`_wcreate_locale`|\<locale.h> または \<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```C  
// crt_create_locale.c  
// Sets the current locale to "de-CH" using the  
// setlocale function and demonstrates its effect on the strftime  
// function.  
  
#include <stdio.h>  
#include <locale.h>  
#include <time.h>  
  
int main(void)  
{  
    time_t ltime;  
    struct tm thetime;  
    unsigned char str[100];  
    _locale_t locale;  
  
    // Create a locale object representing the German (Switzerland) locale  
    locale = _create_locale(LC_ALL, "de-CH");  
    time (&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    // %#x is the long date representation, appropriate to  
    // the current locale  
    if (!_strftime_l((char *)str, 100, "%#x",   
                     (const struct tm *)&thetime, locale))  
    {
        printf("_strftime_l failed!\n");  
    }
    else  
    {
        printf("In de-CH locale, _strftime_l returns '%s'\n", str);  
    }
  
    _free_locale(locale);  
  
    // Create a locale object representing the default C locale  
    locale = _create_locale(LC_ALL, "C");  
    time(&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    if (!_strftime_l((char *)str, 100, "%#x",   
                     (const struct tm *)&thetime, locale))  
    {
        printf("_strftime_l failed!\n");  
    }
    else  
    {
        printf("In 'C' locale, _strftime_l returns '%s'\n", str);  
    }
  
    _free_locale(locale);  
}  
```  
  
```Output  
In de-CH locale, _strftime_l returns 'Samstag, 9. Februar 2002'  
In 'C' locale, _strftime_l returns 'Saturday, February 09, 2002'  
```  
  
## <a name="see-also"></a>関連項目  
 [ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [言語識別文字列](../../c-runtime-library/language-strings.md)   
 [国/地域別文字列](../../c-runtime-library/country-region-strings.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)   
 [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [strlen、wcslen、_mbslen、_mbslen_l、_mbstrlen、_mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)   
 [mbstowcs、_mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll 関数](../../c-runtime-library/strcoll-functions.md)   
 [strftime、wcsftime、_strftime_l、_wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [wcstombs、_wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb、_wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)
