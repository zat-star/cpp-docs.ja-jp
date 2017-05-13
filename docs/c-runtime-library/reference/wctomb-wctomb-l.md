---
title: "wctomb、_wctomb_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wctomb_l
- wctomb
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
- wctomb
dev_langs:
- C++
helpviewer_keywords:
- string conversion, wide characters
- wide characters, converting
- _wctomb_l function
- wctomb function
- wctomb_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 3d199cba90dd2440a7a467c95d32e2a5a75f8cbf
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="wctomb-wctombl"></a>wctomb、_wctomb_l
ワイド文字を対応するマルチバイト文字に変換します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[wctomb_s、_wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
int wctomb(  
   char *mbchar,  
   wchar_t wchar   
);  
int _wctomb_l(  
   char *mbchar,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `mbchar`  
 マルチバイト文字のアドレス。  
  
 `wchar`  
 ワイド文字。  
  
## <a name="return-value"></a>戻り値  
 `wctomb` がワイド文字をマルチバイト文字に変換する場合、ワイド文字のバイト数 (常に `MB_CUR_MAX` 以内) を返します。 `wchar` がワイド文字の null 文字 (L'\0') の場合、`wctomb` 1 を返します。 ターゲット ポインター `mbchar` が NULL の場合、`wctomb` は 0 を返します。 現在のロケールで変換が不可能な場合`wctomb`-1 を返しますと`errno`に設定されている`EILSEQ`です。  
  
## <a name="remarks"></a>コメント  
 `wctomb` 関数はその `wchar` 引数を対応するマルチバイト文字に変換し、結果を `mbchar` に格納します。 任意のプログラムの任意のポイントからこの関数を呼び出すことができます。 `wctomb` は、ロケールに依存するあらゆる動作に現在のロケールを使用します。`_wctomb_l` は、渡されたロケールを代わりに使用することを除いて `wctomb` と同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `wctomb` はそのパラメーターを検証します。 `mbchar` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、 `errno` が `EINVAL` に設定され、関数から -1 が返されます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`wctomb`|\<stdlib.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 このプログラムは、wctomb 関数の動作を示しています。  
  
```  
// crt_wctomb.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int i;  
   wchar_t wc = L'a';  
   char *pmb = (char *)malloc( MB_CUR_MAX );  
  
   printf( "Convert a wide character:\n" );  
   i = wctomb( pmb, wc ); // C4996  
   // Note: wctomb is deprecated; consider using wctomb_s  
   printf( "   Characters converted: %u\n", i );  
   printf( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
```Output  
Convert a wide character:  
   Characters converted: 1  
   Multibyte character: a  
```  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs、_mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs、_wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)
