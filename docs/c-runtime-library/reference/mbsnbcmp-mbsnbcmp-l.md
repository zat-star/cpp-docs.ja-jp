---
title: "_mbsnbcmp、_mbsnbcmp_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbcmp
- _mbsnbcmp_l
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
apitype: DLLExport
f1_keywords:
- mbsnbcmp
- tcsnbmp
- _mbsnbcmp_l
- mbsnbcmp_l
- _mbsnbcmp
dev_langs:
- C++
helpviewer_keywords:
- mbsnbcmp_l function
- mbsnbcmp function
- tcsncmp function
- _mbsnbcmp_l function
- _tcsncmp function
- _mbsnbcmp function
ms.assetid: dbc99e50-cf85-4e57-a13f-067591f18ac8
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 9fdaa428d5772c0622ca4c2f08c64fb376173240
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="mbsnbcmp-mbsnbcmpl"></a>_mbsnbcmp、_mbsnbcmp_l
2 つのマルチバイト文字の文字列の先頭の `n` バイトを比較します。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _mbsnbcmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbcmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `string1, string2`  
 比較対象の文字列。  
  
 `count`  
 比較するバイト数。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 戻り値は、`string1` と `string` の部分文字列間の序数に基づく関係を示しています。  
  
|戻り値|説明|  
|------------------|-----------------|  
|< 0|`string1` の部分文字列が `string2` の部分文字列より小さい。|  
|0|`string1` の部分文字列が `string2` の部分文字列と同じ。|  
|> 0|`string1` の部分文字列が `string2` の部分文字列より大きい。|  
  
 パラメーター検証エラーが発生した場合、`_mbsnbcmp` および `_mbsnbcmp_l` は `_NLSCMPERROR` を返します。これは、\<string.h> および \<mbstring.h> で定義されています。  
  
## <a name="remarks"></a>コメント  
 `_mbsnbcmp` 関数は、`count` と `string1` の先頭の最大 `string2` バイトを比較し、部分文字列の間の関係を示す値を返します。 `_mbsnbcmp` は `_mbsnbicmp` の大文字と小文字を区別するバージョンです。 `_mbsnbcoll` とは異なり、`_mbsnbcmp` はロケールの照合順序の影響を受けません。 `_mbsnbcmp` は、現在のマルチバイト [コード ページ](../../c-runtime-library/code-pages.md)に基づいて、マルチバイト文字のシーケンスを認識します。  
  
 `_mbsnbcmp` は `_mbsncmp` と類似していますが、`_mbsncmp` はバイトではなく文字で文字列を比較する点が異なります。  
  
 出力値はロケールの `LC_CTYPE` カテゴリの設定に影響を受けます。この設定は、マルチバイト文字の先頭および末尾のバイトを指定します。 詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」をご覧ください。 `_mbsnbcmp` は、ロケールに依存するこの動作に現在のロケールを使用します。 `_mbsnbcmp_l` 関数は、代わりに `locale` パラメーターを使用することを除けば、同一です。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
 `string1` または `string2` のどちらかが null ポインターの場合、これらの関数は、「[Parameter Validation](../../c-runtime-library/parameter-validation.md)」(パラメーターの検証) で説明されているように無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、関数は `_NLSCMPERROR` を返し、`errno` が `EINVAL` に設定されます。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|---------------------------------------|--------------------|-----------------------|  
|`_tcsncmp`|[strncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|`_mbsnbcmp`|[wcsncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|  
|`_tcsncmp_l`|[strncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|`_mbsnbcml`|[wcsncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_mbsnbcmp`|\<mbstring.h>|  
|`_mbsnbcmp_l`|\<mbstring.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_mbsnbcmp.c  
#include <mbstring.h>  
#include <stdio.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown fox jumps over the lazy dog";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
   printf( "Compare strings:\n          %s\n", string1 );  
   printf( "          %s\n\n", string2 );  
   printf( "Function: _mbsnbcmp (first 10 characters only)\n" );  
   result = _mbsncmp( string1, string2 , 10 );  
   if( result > 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:   String 1 is %s string 2\n\n", tmp );  
   printf( "Function: _mbsnicmp _mbsnicmp (first 10 characters only)\n" );  
   result = _mbsnicmp( string1, string2, 10 );  
   if( result > 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:   String 1 is %s string 2\n\n", tmp );  
}  
```  
  
## <a name="output"></a>出力  
  
```  
Compare strings:  
          The quick brown dog jumps over the lazy fox  
          The QUICK brown fox jumps over the lazy dog  
  
Function: _mbsnbcmp (first 10 characters only)  
Result:   String 1 is greater than string 2  
  
Function: _mbsnicmp _mbsnicmp (first 10 characters only)  
Result:   String 1 is equal to string 2  
```  
  
## <a name="see-also"></a>関連項目  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcat、_mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [_mbsnbicmp、_mbsnbicmp_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)
