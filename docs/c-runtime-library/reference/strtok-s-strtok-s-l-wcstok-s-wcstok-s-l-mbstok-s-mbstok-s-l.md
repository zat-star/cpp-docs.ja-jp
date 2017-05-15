---
title: "strtok_s、_strtok_s_l、wcstok_s、_wcstok_s_l、_mbstok_s、_mbstok_s_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcstok_s_l
- _mbstok_s_l
- _mbstok_s
- strtok_s
- wcstok_s
- _strtok_s_l
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
- _tcstok_s_l
- _wcstok_s_l
- _tcstok_s
- _mbstok_s_l
- strtok_s
- wcstok_s
- _mbstok_s
- _strtok_s_l
dev_langs:
- C++
helpviewer_keywords:
- _strtok_s_l function
- _mbstok_s_l function
- strings [C++], searching
- mbstok_s_l function
- wcstok_s_l function
- _wcstok_s_l function
- _tcstok_s function
- _tcstok_s_l function
- strtok_s_l function
- wcstok_s function
- tokens, finding in strings
- mbstok_s function
- _mbstok_s function
- strtok_s function
ms.assetid: 7696c972-f83b-4617-8c82-95973e9fdb46
caps.latest.revision: 28
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
ms.openlocfilehash: 4313f785ba5197c3659e74384b7d6ecda8e8c7be
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="strtoks-strtoksl-wcstoks-wcstoksl-mbstoks-mbstoksl"></a>strtok_s、_strtok_s_l、wcstok_s、_wcstok_s_l、_mbstok_s、_mbstok_s_l
現在のロケールまたは渡されたロケールを使用して、文字列内の次のトークンを検索します。 これらのバージョンの [strtok、_strtok_l、wcstok、_wcstok_l、_mbstok、_mbstok_l](../../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」にあるとおり、セキュリティが強化されています。  
  
> [!IMPORTANT]
>  `_mbstok_s` および `_mbstok_s_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
  
      char *strtok_s(  
char *strToken,  
const char *strDelimit,  
   char **context  
);  
char *_strtok_s_l(  
char *strToken,  
const char *strDelimit,  
   char **context,  
_locale_tlocale  
);  
wchar_t *wcstok_s(  
wchar_t *strToken,  
const wchar_t *strDelimit,   
   wchar_t**context  
);  
wchar_t *_wcstok_s_l(  
wchar_t *strToken,  
const wchar_t *strDelimit,   
   wchar_t**context,  
_locale_tlocale  
);  
unsigned char *_mbstok_s(  
unsigned char*strToken,  
const unsigned char *strDelimit,   
   char **context  
);  
unsigned char *_mbstok_s(  
unsigned char*strToken,  
const unsigned char *strDelimit,   
   char **context,  
_locale_tlocale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `strToken`  
 トークンを含む文字列。  
  
 `strDelimit`  
 区切り記号文字のセット。  
  
 `context`  
 `strtok_s` の呼び出しと呼び出しの間の位置情報の格納に使用されます。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `strToken` で見つかった次のトークンへのポインターを返します。 これ以上トークンがない場合、これらは `NULL` を返します。 各呼び出しは、返されたトークンの後に発生する最初の区切り記号を `strToken` 文字に置き換えることで `NULL` を変更します。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`strToken`|`strDelimit`|`context`|戻り値|`errno`|  
|----------------|------------------|---------------|------------------|-------------|  
|`NULL`|任意|null ポインターへのポインター|`NULL`|`EINVAL`|  
|任意|`NULL`|任意|`NULL`|`EINVAL`|  
|任意|任意|`NULL`|`NULL`|`EINVAL`|  
  
 `strToken` が `NULL` ですが、コンテキストが有効なコンテキストのポインターへのポインターの場合は、エラーは発生しません。  
  
## <a name="remarks"></a>コメント  
 `strtok_s` 関数は `strToken` の次のトークンを検索します。 `strDelimit` の文字セットは、現在の呼び出しの `strToken` で検索されたトークンの使用可能な区切り記号を指定します。 `wcstok_s` 関数と `_mbstok_s` 関数は、`strtok_s` 関数のワイド文字バージョンとマルチバイト文字バージョンです。 `wcstok_s` および `_wcstok_s_l` 関数の引数と戻り値はワイド文字列で、`_mbstok_s` および `_mbstok_s_l` 関数の引数と戻り値はマルチバイト文字列です。 それ以外では、これらの関数の動作は同じです。  
  
 この関数は、パラメーターを検証します。 表「エラー条件」に示すようなエラー条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`NULL` を返します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstok_s`|`strtok_s`|`_mbstok_s`|`wcstok_s`|  
|`_tcstok_s_l`|`_strtok_s_l`|`_mbstok_s_l`|`_wcstok_s_l`|  
  
 `strtok_s` への最初の呼び出しで、関数は先行する区切り記号をスキップし、`strToken` の最初のトークンへのポインターを返して null 文字を含むトークンを終了します。 `strToken` への一連の呼び出しにより、より多くのトークンを `strtok_s` の残りから作成できます。 `strtok_s` への各呼び出しは、その呼び出しによって返されるトークンの後に null 文字を挿入することで `strToken` を変更します。 `context` ポインターは、読み込まれる文字列、および次のトークンが読み込まれる文字列内の位置を追跡し続けます。 `strToken` から次のトークンを読み込むには、`strtok_s` を `NULL` 引数に `strToken` 値を使用して呼び出し、同じ `context` パラメーターを渡します。 `NULL` `strToken` 引数により、`strtok_s` は変更された `strToken` で次のトークンを検索します。 `strDelimit` 引数は、ある呼び出しから次の呼び出しへ任意の値を取ることができるため、区切り記号のセットが異なる場合があります。  
  
 `context` パラメーターは `strtok` と `_strtok_l` で使用される静的バッファーよりも優先されるため、同じスレッドで 2 つの文字列を同時に分析できます。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定に影響されます。詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。 `_l` サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`strtok_s`|\<string.h>|  
|`_strtok_s_l`|\<string.h>|  
|`wcstok_s`、<br /><br /> `_wcstok_s_l`|\<string.h> または \<wchar.h>|  
|`_mbstok_s`、<br /><br /> `_mbstok_s_l`|\<mbstring.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_strtok_s.c  
// In this program, a loop uses strtok_s  
// to print all the tokens (separated by commas  
// or blanks) in two strings at the same time.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
char string1[] =  
    "A string\tof ,,tokens\nand some  more tokens";  
char string2[] =  
    "Another string\n\tparsed at the same time.";  
char seps[]   = " ,\t\n";  
char *token1 = NULL;  
char *token2 = NULL;  
char *next_token1 = NULL;  
char *next_token2 = NULL;  
  
int main( void )  
{  
    printf( "Tokens:\n" );  
  
    // Establish string and get the first token:  
    token1 = strtok_s( string1, seps, &next_token1);  
    token2 = strtok_s ( string2, seps, &next_token2);  
  
    // While there are tokens in "string1" or "string2"  
    while ((token1 != NULL) || (token2 != NULL))  
    {  
        // Get next token:  
        if (token1 != NULL)  
        {  
            printf( " %s\n", token1 );  
            token1 = strtok_s( NULL, seps, &next_token1);  
        }  
        if (token2 != NULL)  
        {  
            printf("        %s\n", token2 );  
            token2 = strtok_s (NULL, seps, &next_token2);  
        }  
    }  
}  
```  
  
```Output  
Tokens:  
 A  
        Another  
 string  
        string  
 of  
        parsed  
 tokens  
        at  
 and  
        the  
 some  
        same  
 more  
        time.  
 tokens  
```  
  
## <a name="see-also"></a>関連項目  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn、wcscspn、_mbscspn、_mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strspn、wcsspn、_mbsspn、_mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
