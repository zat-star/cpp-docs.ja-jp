---
title: "mbstowcs、_mbstowcs_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- mbstowcs
- _mbstowcs_l
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbstowcs
dev_langs:
- C++
helpviewer_keywords:
- _mbstowcs_l function
- mbstowcs_l function
- mbstowcs function
ms.assetid: 96696b27-e068-4eeb-8006-3f7a0546ae6d
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 436e581907e3b651716e819a9c82a24eed2e4b8e
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="mbstowcs-mbstowcsl"></a>mbstowcs、_mbstowcs_l
マルチバイト文字のシーケンスを、対応するワイド文字のシーケンスに変換します。 これらの関数のセキュリティを強化したバージョンについては、「[mbstowcs_s、_mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
size_t mbstowcs(  
   wchar_t *wcstr,  
   const char *mbstr,  
   size_t count   
);  
size_t _mbstowcs_l(  
   wchar_t *wcstr,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t mbstowcs(  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _mbstowcs_l(  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `wcstr`  
 ワイド文字のシーケンスのアドレス。  
  
 [入力] `mbstr`  
 null で終了するマルチバイト文字のシーケンスのアドレス。  
  
 [入力] `count`  
 変換するマルチバイト文字の最大数。  
  
 [入力] `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 ソース文字列を正常に変換した場合、`mbstowcs` は変換されたマルチバイト文字数を返します。 `wcstr` 引数が `NULL` の場合、この関数は対象文字列の必要なサイズを (ワイド文字数で) 返します。 場合`mbstowcs`に無効なマルチバイト文字を検出した-1 を返します。 戻り値が `count` の場合、ワイド文字列の終端には null 文字が追加されません。  
  
> [!IMPORTANT]
>  `wcstr` と `mbstr` が重なり合わず、変換するマルチバイト文字の数が `count` に適切に反映されていることを確認します。  
  
## <a name="remarks"></a>コメント  
 `mbstowcs` 関数は、`mbstr` が指す `count` 数までのマルチバイト文字を、現在のロケールに基づいて対応するワイド文字の文字列に変換します。 によって表されるアドレスで作成されたワイド文字列を格納`wcstr`です。 結果は、`mbtowc` を複数回呼び出した場合と類似しています。 `count` の前かその中に 1 バイトの null 文字 ('\0') が検出されると、`mbstowcs` は null 文字をワイド文字の null 文字 (L'\0') に変換して停止します。 このため、`wcstr` のワイド文字の文字列が null 終了になるのは、変換中にマルチバイト null 文字が検出された場合だけです。 `wcstr` および `mbstr` が指すシーケンスが重なり合う場合、動作は未定義です。  
  
 `wcstr` 引数が `NULL` の場合、`mbstowcs` は変換によって得られるワイド文字数を返します。終端の null は含まれません。 正しい値を返すには、ソース文字列が null で終わっている必要があります。 結果のワイド文字列を null で終了する必要がある場合は、戻り値に 1 を追加します。  
  
 `mbstr` 引数が `NULL` の場合、または `count` が `INT_MAX` を超える場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、errno が `EINVAL` に設定され、関数から -1 が返されます。  
  
 `mbstowcs` は、ロケールに依存するあらゆる動作に現在のロケールを使用します。`_mbstowcs_l` は、渡されたロケールを代わりに使用することを除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
 C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`mbstowcs`|\<stdlib.h>|  
|`_mbstowcs_l`|\<stdlib.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_mbstowcs.c  
// compile with: /W3  
// illustrates the behavior of the mbstowcs function  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <locale.h>  
  
int main( void )  
{  
    size_t size;  
    int nChar = 2; // number of characters to convert  
    int requiredSize;  
  
    unsigned char    *pmbnull  = NULL;  
    unsigned char    *pmbhello = NULL;  
    char* localeInfo;  
  
    wchar_t *pwchello = L"\x3042\x3043"; // 2 Hiragana characters  
    wchar_t *pwc;  
  
    /* Enable the Japanese locale and codepage */  
    localeInfo = setlocale(LC_ALL, "Japanese_Japan.932");  
    printf("Locale information set to %s\n", localeInfo);  
  
    printf( "Convert to multibyte string:\n" );  
  
    requiredSize = wcstombs( NULL, pwchello, 0); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s  
    printf("  Required Size: %d\n", requiredSize);  
  
    /* Add one to leave room for the null terminator. */  
    pmbhello = (unsigned char *)malloc( requiredSize + 1);  
    if (! pmbhello)  
    {  
        printf("Memory allocation failure.\n");  
        return 1;  
    }  
    size = wcstombs( pmbhello, pwchello, requiredSize + 1); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s  
    if (size == (size_t) (-1))  
    {  
        printf("Couldn't convert string. Code page 932 may"  
                " not be available.\n");  
        return 1;  
    }  
    printf( "  Number of bytes written to multibyte string: %u\n",  
            (unsigned int) size );  
    printf( "  Hex values of the " );  
    printf( " multibyte characters: %#.2x %#.2x %#.2x %#.2x\n",  
            pmbhello[0], pmbhello[1], pmbhello[2], pmbhello[3] );  
    printf( "  Codepage 932 uses 0x81 to 0x9f as lead bytes.\n\n");  
  
    printf( "Convert back to wide-character string:\n" );  
  
    /* Assume we don't know the length of the multibyte string.  
     Get the required size in characters, and allocate enough space. */  
  
    requiredSize = mbstowcs(NULL, pmbhello, 0); // C4996  
    /* Add one to leave room for the NULL terminator */  
    pwc = (wchar_t *)malloc( (requiredSize + 1) * sizeof( wchar_t ));  
    if (! pwc)  
    {  
        printf("Memory allocation failure.\n");  
        return 1;  
    }  
    size = mbstowcs( pwc, pmbhello, requiredSize + 1); // C4996  
    if (size == (size_t) (-1))  
    {  
       printf("Couldn't convert string--invalid multibyte character.\n");  
    }  
    printf( "  Characters converted: %u\n", (unsigned int)size );  
    printf( "  Hex value of first 2" );  
    printf( " wide characters: %#.4x %#.4x\n\n", pwc[0], pwc[1] );  
    free(pwc);  
    free(pmbhello);  
}  
```  
  
```Output  
Locale information set to Japanese_Japan.932  
Convert to multibyte string:  
  Required Size: 4  
  Number of bytes written to multibyte string: 4  
  Hex values of the  multibyte characters: 0x82 0xa0 0x82 0xa1  
  Codepage 932 uses 0x81 to 0x9f as lead bytes.  
  
Convert back to wide-character string:  
  Characters converted: 2  
  Hex value of first 2 wide characters: 0x3042 0x3043  
```  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs、_wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb、_wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)
