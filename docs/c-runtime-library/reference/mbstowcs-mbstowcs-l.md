---
title: "mbstowcs、_mbstowcs_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "mbstowcs"
  - "_mbstowcs_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mbstowcs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbstowcs_l 関数"
  - "mbstowcs 関数"
  - "mbstowcs_l 関数"
ms.assetid: 96696b27-e068-4eeb-8006-3f7a0546ae6d
caps.latest.revision: 30
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mbstowcs、_mbstowcs_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ワイド文字の対応するシーケンスにマルチバイト文字のシーケンスを変換します。  これらの関数のセキュリティを強化したバージョンについては、「[mbstowcs\_s、\_mbstowcs\_s\_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)」を参照してください。  
  
## 構文  
  
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
  
#### パラメーター  
 \[出力\] `wcstr`  
 ワイド文字のシーケンスのアドレス。  
  
 \[\] `mbstr`  
 null で終わる文字列のマルチバイト文字のシーケンスのアドレス。  
  
 \[入力\] `count`  
 変換するマルチバイト文字の最大数。  
  
 \[入力\] `locale`  
 使用するロケール。  
  
## 戻り値  
 `mbstowcs` が正常にソース文字列を変換すると、変換されたマルチバイト文字数を返します。  `wcstr` の引数が `NULL`の場合、関数の戻り値のコピー先文字列の必須のサイズ \(ワイド文字単位\)。  `mbstowcs` に無効なマルチバイト文字があると、–1 を返します。  戻り値が `count`場合、ワイド文字列が null で終わるではありません。  
  
> [!IMPORTANT]
>  `wcstr` と `mbstr` が重複しないよう、`count` が変換に正しくマルチバイト文字数を反映していることを確認します。  
  
## 解説  
 `mbstowcs` 関数は現在のロケールで決められた対応するワイド文字列を `mbstr` が指す `count` のマルチバイト文字の最大数に達するまで、変換します。  これは `wcstr`で表されるアドレスで発生したワイド文字列を格納します*。*結果は `mbtowc`に一連の呼び出しと似ています。  `mbstowcs` が前の空白文字 `count` が発生したとき \(「\\0」\) により前にある場合、または stop ワイド文字の空白文字 \(L」\\0」\) に null 文字を変換できます。  したがって `wcstr` のワイド文字列には、null 文字が変換中に呼び出されたときにのみ null で終わるです。  `wcstr` と `mbstr` の重複が指すシーケンスの動作は未定義です。  
  
 `wcstr` の引数が `NULL`の場合、`mbstowcs` は変換に起因する null 終端文字などのワイド文字数を、返します。  元の文字列が返されます。正しい値に null で終わるである必要があります。  結果のワイド文字列が null で終わるであることが必要な場合は、戻り値に 1 を加算します。  
  
 `mbstr` の引数が `NULL`であるか、または `count` が `INT_MAX`の場合、\> 無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md) "に説明されているように、呼び出されます。  実行の継続が許可された場合、errno が `EINVAL` および関数の戻り値が \-1 に設定されます。  
  
 `mbstowcs` は、すべてのロケールに依存する動作に現在のロケールを使用して; `_mbstowcs_l`は同じですが、渡されたロケールを代わりに使用します。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 C\+\+ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`mbstowcs`|\<stdlib.h\>|  
|`_mbstowcs_l`|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
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
  
  **Japanese\_Japan.932 に設定されているロケール情報**  
**マルチバイト文字列に変換:**  
 **必要なサイズ: 4**  
 **マルチバイト文字列に書き込まれたバイト数: 4**  
 **マルチバイト文字の 16 進値:十六 0x82 0xa0 0x82 0xa1**  
 **コードページ 932 の使用 0x81 への先行バイトとして 0x9f。**  
**ワイド文字列に再変換:**  
 **変換された文字: 2**  
 **最初の 2 つがワイド文字の 16 進値:十六 0x3042 0x3043**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen、mblen、\_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc、\_mbtowc\_l](../Topic/mbtowc,%20_mbtowc_l.md)   
 [wcstombs、\_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md)   
 [wctomb、\_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)