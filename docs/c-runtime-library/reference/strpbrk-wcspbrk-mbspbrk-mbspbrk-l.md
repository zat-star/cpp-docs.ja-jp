---
title: "strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbspbrk
- wcspbrk
- _mbspbrk_l
- strpbrk
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
- _fstrpbrk
- _mbspbrk
- strpbrk
- _tcspbrk
- _ftcspbrk
- wcspbrk
dev_langs: C++
helpviewer_keywords:
- fstrpbrk function
- _ftcspbrk function
- _mbspbrk_l function
- strpbrk function
- _fstrpbrk function
- mbspbrk function
- characters [C++], scanning strings
- _tcspbrk function
- wcspbrk function
- ftcspbrk function
- character sets [C++], scanning strings for characters
- strings [C++], scanning
- tcspbrk function
- _mbspbrk function
- mbspbrk_l function
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
caps.latest.revision: "30"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 323ee2842799cdfe948bdf0a8af7ec2bfad92439
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="strpbrk-wcspbrk-mbspbrk-mbspbrkl"></a>strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l
文字列をスキャンして、指定された文字セットの文字を検索します。  
  
> [!IMPORTANT]
>  `_mbspbrk` および `_mbspbrk_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
char *strpbrk(  
   const char *str,  
   const char *strCharSet   
); // C only  
char *strpbrk(  
   char *str,  
   const char *strCharSet   
); // C++ only  
const char *strpbrk(  
   const char *str,  
   const char *strCharSet   
); // C++ only  
wchar_t *wcspbrk(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
); // C only  
wchar_t *wcspbrk(  
   wchar_t *str,  
   const wchar_t *strCharSet   
); // C++ only  
const wchar_t *wcspbrk(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
); // C++ only  
unsigned char *_mbspbrk(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
); // C only  
unsigned char *_mbspbrk(  
   unsigned char *str,  
   const unsigned char *strCharSet   
); // C++ only  
const unsigned char *_mbspbrk(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
); // C++ only  
unsigned char *_mbspbrk_l(  
   const unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
); // C only  
unsigned char *_mbspbrk_l(  
   unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbspbrk_l(  
   const unsigned char *str,  
   const unsigned char* strCharSet,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `str`  
 NULL で終わる検索対象の文字列。  
  
 `strCharSet`  
 NULL で終わる文字セット。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `strCharSet` の `str` から最初に出現する文字へのポインター、または 2 つの文字列引数に共通の文字がない場合は `NULL` ポインターを返します。  
  
## <a name="remarks"></a>コメント  
 `strpbrk` 関数は、`str` の文字セットに属する `strCharSet` で最初に出現する文字へのポインターを返します。 検索には、終端の NULL 文字は含まれません。  
  
 `wcspbrk` 関数と `_mbspbrk` 関数は、`strpbrk` 関数のワイド文字バージョンとマルチバイト文字バージョンです。 `wcspbrk` 関数の引数と戻り値はワイド文字列で、`_mbspbrk` 関数の引数と戻り値はマルチバイト文字列です。  
  
 `_mbspbrk` はそのパラメーターを検証します。 `str` または `strCharSet` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`_mbspbrk` は `NULL` を返し、`errno` を `EINVAL` に設定します。 `strpbrk` および `wcspbrk` は、パラメーターを検証しません。 それ以外では、これらの関数の動作は同じです。  
  
 `_mbspbrk` と `_mbscspn` は似ていますが、`_mbspbrk` は [size_t](../../c-runtime-library/standard-types.md) 型の値ではなくポインターを返す点が異なります。  
  
 C では、これらの関数は、最初の引数に `const` ポインターを受け取ります。 C++ では、2 つのオーバーロードを使用できます。 `const` へのポインターを受け取るオーバーロードでは、`const` へのポインターが返されます。非 `const` へのポインターを受け取るバージョンでは、非 `const` へのポインターが返されます。 マクロ`_CRT_CONST_CORRECT_OVERLOADS`場合は、両方が定義されている、`const`と非-`const`これらの関数のバージョンを利用できます。 必要な以外の場合`const`シンボルを定義する両方の C++ オーバー ロードの動作`_CONST_RETURN`です。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定に影響されます。詳細については、[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) に関する記事をご覧ください。 `_l` サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcspbrk`|`strpbrk`|`_mbspbrk`|`wcspbrk`|  
|**該当なし**|**該当なし**|`_mbspbrk_l`|**該当なし**|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`strpbrk`|\<string.h>|  
|`wcspbrk`|\<string.h> または \<wchar.h>|  
|`_mbspbrk`, `_mbspbrk_l`|\<mbstring.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_strpbrk.c  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[100] = "The 3 men and 2 boys ate 5 pigs\n";  
   char *result = NULL;  
  
   // Return pointer to first digit in "string".  
   printf( "1: %s\n", string );  
   result = strpbrk( string, "0123456789" );  
   printf( "2: %s\n", result++ );  
   result = strpbrk( result, "0123456789" );  
   printf( "3: %s\n", result++ );  
   result = strpbrk( result, "0123456789" );  
   printf( "4: %s\n", result );  
}  
```  
  
```Output  
1: The 3 men and 2 boys ate 5 pigs  
  
2: 3 men and 2 boys ate 5 pigs  
  
3: 2 boys ate 5 pigs  
  
4: 5 pigs  
```  
  
## <a name="see-also"></a>参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn、wcscspn、_mbscspn、_mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strchr、wcschr、_mbschr、_mbschr_l](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)   
 [strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)