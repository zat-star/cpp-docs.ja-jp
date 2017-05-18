---
title: "strstr、wcsstr、_mbsstr、_mbsstr_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsstr
- wcsstr
- _mbsstr_l
- strstr
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fstrstr
- _ftcsstr
- strstr
- wcsstr
- _mbsstr
- _tcsstr
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], searching
- mbsstr function
- _ftcsstr function
- ftcsstr function
- fstrstr function
- _tcsstr function
- substrings, finding
- mbsstr_l function
- tcsstr function
- _mbsstr function
- wcsstr function
- _fstrstr function
- _mbsstr_l function
- strstr function
ms.assetid: 03d70c3f-2473-45cb-a5f8-b35beeb2748a
caps.latest.revision: 32
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: dee742e53a8ac9243503011b827a008879af6428
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="strstr-wcsstr-mbsstr-mbsstrl"></a>strstr、wcsstr、_mbsstr、_mbsstr_l
文字列で最初に見つかった検索文字列へのポインターを返します。  
  
> [!IMPORTANT]
>  `_mbsstr` と `_mbsstr_l` は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] で実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
char *strstr(  
   const char *str,  
   const char *strSearch   
); // C only  
char *strstr(  
   char *str,  
   const char *strSearch   
); // C++ only  
const char *strstr(  
   const char *str,  
   const char *strSearch   
); // C++ only  
wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C only  
wchar_t *wcsstr(  
   wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
const wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C only  
unsigned char *_mbsstr(  
   unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
const unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C only  
unsigned char *_mbsstr_l(  
   unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `str`  
 NULL で終わる検索対象の文字列。  
  
 `strSearch`  
 NULL で終わる検索する文字列。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `strSearch` で最初に見つかった `str` へのポインター、または `NULL` が `strSearch` に見つからなかった場合は `str` を返します。 `strSearch` が長さ 0 の文字列を参照している場合、`str` を返します。  
  
## <a name="remarks"></a>コメント  
 `strstr` 関数は、`strSearch` で最初に見つかった `str` へのポインターを返します。 検索には、終端の NULL 文字は含まれません。 `wcsstr` は `strstr` のワイド文字バージョンであり、`_mbsstr` はマルチバイト文字バージョンです。 `wcsstr` 関数の引数と戻り値はワイド文字列で、`_mbsstr` 関数の引数と戻り値はマルチバイト文字列です。 `_mbsstr` はそのパラメーターを検証します。 `str` または `strSearch` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`_mbsstr` は `errno` を `EINVAL` に設定し、0 を返します。 `strstr` および `wcsstr` は、パラメーターを検証しません。 それ以外では、これらの関数の動作は同じです。  
  
> [!IMPORTANT]
>  これらの関数は、バッファー オーバーランの問題が原因で脅威を受ける可能性があります。 バッファー オーバーランにより、任意のコードが実行できるようになり、その結果認められていない特権の昇格が発生する可能性があるので、バッファー オーバーランの問題はシステムを攻撃するときに使用されることがあります。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
 C では、これらの関数は、最初の引数に `const` ポインターを受け取ります。 C++ では、2 つのオーバーロードを使用できます。 `const` へのポインターを受け取るオーバーロードでは、`const` へのポインターが返されます。非 `const` へのポインターを受け取るバージョンでは、非 `const` へのポインターが返されます。 この関数の `const` と非 `const` の両方のバージョンが使用できる場合、_CONST_CORRECT_OVERLOADS というマクロが定義されます。 C++ のいずれのオーバーロードでも、非 `const` の動作が求められる場合は、シンボル _CONST_RETURN を定義してください。  
  
 出力値は、`LC_CTYPE` のロケール カテゴリ設定で決まります。詳細については、「[setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」をご覧ください。 `_l` サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|  
|**該当なし**|**該当なし**|`_mbsstr_l`|**該当なし**|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`strstr`|\<string.h>|  
|`wcsstr`|\<string.h> または \<wchar.h>|  
|`_mbsstr`, `_mbsstr_l`|\<mbstring.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```C  
// crt_strstr.c  
  
#include <string.h>  
#include <stdio.h>  
  
char str[] =    "lazy";  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int  result;  
   printf( "String to be searched:\n   %s\n", string );  
   printf( "   %s\n   %s\n\n", fmt1, fmt2 );  
   pdest = strstr( string, str );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf( "%s found at position %d\n", str, result );  
   else  
      printf( "%s not found\n", str );  
}  
```  
  
```Output  
String to be searched:  
   The quick brown dog jumps over the lazy fox  
            1         2         3         4         5  
   12345678901234567890123456789012345678901234567890  
  
lazy found at position 36  
```  
  
## <a name="see-also"></a>関連項目  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn、wcscspn、_mbscspn、_mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strcmp、wcscmp、_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn、wcsspn、_mbsspn、_mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [basic_string::find](../../standard-library/basic-string-class.md#find)  

