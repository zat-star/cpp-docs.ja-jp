---
title: "strcspn、wcscspn、_mbscspn、_mbscspn_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbscspn_l
- wcscspn
- _mbscspn
- strcspn
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
- strcspn
- _mbscspn
- wcscspn
- _ftcscspn
- _tcscspn
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], searching
- ftcscspn function
- strcspn function
- _mbscspn function
- mbscspn_l function
- wcscspn function
- tcscspn function
- _ftcscspn function
- _mbscspn_l function
- mbscspn function
- _tcscspn function
ms.assetid: f73f51dd-b533-4e46-ba29-d05c553708a6
caps.latest.revision: 24
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
ms.openlocfilehash: ace0d86645c213c37c76b93227557a38af6eb321
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="strcspn-wcscspn-mbscspn-mbscspnl"></a>strcspn、wcscspn、_mbscspn、_mbscspn_l
文字列の中で、文字セットに含まれる文字が最初に見つかった位置のインデックスを返します。  
  
> [!IMPORTANT]
>  `_mbschr` および `_mbschr_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
size_t strcspn(  
   const char *str,  
   const char *strCharSet   
);  
size_t wcscspn(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
);  
size_t _mbscspn(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
);  
size_t _mbscspn_l(  
   const unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `str`  
 NULL で終わる検索対象の文字列。  
  
 `strCharSet`  
 NULL で終わる文字セット。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 これらの関数は `str` にある文字の内の `strCharSet` の先頭文字のインデックスを返します。 `str` の文字のいずれも `strCharSet` にない場合、戻り値は `str` の長さです。  
  
 エラーを示す戻り値は予約されていません。  
  
## <a name="remarks"></a>コメント  
 `wcscspn` 関数と `_mbscspn` 関数は、`strcspn` 関数のワイド文字バージョンとマルチバイト文字バージョンです。 `wcscspn` 関数の引数はワイド文字列で、`_mbscspn` 関数の引数はマルチバイト文字列です。  
  
 `_mbscspn` はそのパラメーターを検証します。 `str` または `strCharSet` のいずれかが null ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は 0 を返し、`errno` を `EINVAL` に設定します。 `strcspn` および `wcscspn` は、パラメーターを検証しません。 それ以外では、これらの関数の動作は同じです。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定に影響されます。詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。 `_l` サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcscspn`|`strcspn`|`_mbscspn`|`wcscspn`|  
|`n/a`|`n/a`|`_mbscspn_l`|`n/a`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`strcspn`|\<string.h>|  
|`wcscspn`|\<string.h> または \<wchar.h>|  
|`_mbscspn`, `_mbscspn_l`|\<mbstring.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_strcspn.c  
  
#include <string.h>  
#include <stdio.h>  
  
void test( const char * str, const char * strCharSet )  
{  
   int pos = strcspn( str, strCharSet );  
   printf( "strcspn( \"%s\", \"%s\" ) = %d\n", str, strCharSet, pos );      
}  
  
int main( void )  
{  
   test( "xyzbxz", "abc" );  
   test( "xyzbxz", "xyz" );  
   test( "xyzbxz", "no match" );  
   test( "xyzbxz", "" );  
   test( "", "abc" );  
   test( "", "" );  
}  
```  
  
```Output  
strcspn( "xyzbxz", "abc" ) = 3  
strcspn( "xyzbxz", "xyz" ) = 0  
strcspn( "xyzbxz", "no match" ) = 6  
strcspn( "xyzbxz", "" ) = 6  
strcspn( "", "abc" ) = 0  
strcspn( "", "" ) = 0  
```  
  
## <a name="see-also"></a>関連項目  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn、wcsspn、_mbsspn、_mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
