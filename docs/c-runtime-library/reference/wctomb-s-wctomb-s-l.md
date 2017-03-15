---
title: "wctomb_s、_wctomb_s_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wctomb_s_l
- wctomb_s
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
- wctomb_s
- _wctomb_s_l
dev_langs:
- C++
helpviewer_keywords:
- wctomb_s function
- wctomb_s_l function
- string conversion, wide characters
- wide characters, converting
- _wctomb_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
caps.latest.revision: 18
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 94973bf59580354aed75b8c7a3a154f415060163
ms.lasthandoff: 02/24/2017

---
# <a name="wctombs-wctombsl"></a>wctomb_s、_wctomb_s_l
ワイド文字を対応するマルチバイト文字に変換します。 「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [wctomb、_wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t wctomb_s(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar   
);  
errno_t _wctomb_s_l(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `pRetValue`  
 バイト数、または結果を示すコード。  
  
 [出力] `mbchar`  
 マルチバイト文字のアドレス。  
  
 [入力] `sizeInBytes`  
 バッファー `mbchar` のサイズ。  
  
 [入力] `wchar`  
 ワイド文字。  
  
 [入力] `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は&0; を返します。失敗した場合はエラー コードを返します。  
  
 エラー条件  
  
|`mbchar`|`sizeInBytes`|戻り値|`pRetValue`|  
|--------------|-------------------|------------------|-----------------|  
|`NULL`|>0|`EINVAL`|変更されない|  
|任意|>`INT_MAX`|`EINVAL`|変更されない|  
|任意|小さすぎる|`EINVAL`|変更されない|  
  
 上記のいずれかのエラー条件が発生すると、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラ―が呼び出されます。 実行の継続が許可された場合、`wctomb` は `EINVAL` を返し、`errno` を `EINVAL` に設定します。  
  
## <a name="remarks"></a>コメント  
 `wctomb_s` 関数はその `wchar` 引数を対応するマルチバイト文字に変換し、結果を `mbchar` に格納します。 任意のプログラムの任意のポイントからこの関数を呼び出すことができます。  
  
 `wctomb_s` がワイド文字をマルチバイト文字に変換する場合、ワイド文字のバイト数 (常に `MB_CUR_MAX` 以内) を `pRetValue` によって示される整数に与えます。 `wchar` がワイド文字の null 文字 (L'\0') である場合、`wctomb_s` は 1 で `pRetValue` を塗りつぶします。 ターゲット ポインター `mbchar` が NULL の場合、`wctomb_s` は `pRetValue` に 0 を格納します。 現在のロケールで変換が不可能な場合、`wctomb_s` は `pRetValue` に -1 を格納します。  
  
 `wctomb_s` は、ロケールに依存する情報に現在のロケールを使用します。`_wctomb_s_l` は、渡されたロケールを代わりに使用することを除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`wctomb_s`|\<stdlib.h>|  
|`_wctomb_s_l`|\<stdlib.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 このプログラムは、`wctomb` 関数の動作を示しています。  
  
```  
// crt_wctomb_s.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    int i;  
    wchar_t wc = L'a';  
    char *pmb = (char *)malloc( MB_CUR_MAX );  
  
    printf_s( "Convert a wide character:\n" );  
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );  
    printf_s( "   Characters converted: %u\n", i );  
    printf_s( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
```Output  
Convert a wide character:  
   Characters converted: 1  
   Multibyte character: a  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs、_mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs、_wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)
