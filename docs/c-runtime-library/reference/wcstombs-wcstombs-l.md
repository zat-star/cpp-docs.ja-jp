---
title: "wcstombs、_wcstombs_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcstombs
- _wcstombs_l
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
- wcstombs
- _wcstombs_l
dev_langs:
- C++
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
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
ms.openlocfilehash: 200337a53155b27b76a944d025c8fb013c29c4e6
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="wcstombs-wcstombsl"></a>wcstombs、_wcstombs_l
ワイド文字のシーケンスを、対応するマルチバイト文字のシーケンスに変換します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[wcstombs_s、_wcstombs_s_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
size_t wcstombs(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count   
);  
size_t _wcstombs_l(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t wcstombs(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _wcstombs_l(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `mbstr`  
 マルチバイト文字のシーケンスのアドレス。  
  
 `wcstr`  
 ワイド文字のシーケンスのアドレス。  
  
 `count`  
 マルチバイト出力文字列に格納できる最大バイト数。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `wcstombs` によってマルチバイト文字列が正常に変換された場合は、マルチバイト出力文字列に書き込まれたバイト数を返します (終端の `NULL` がある場合でもバイト数に含まれません)。 `mbstr` 引数が `NULL` の場合、`wcstombs` は必要な対象文字列のサイズ (バイト数) を返します。 場合`wcstombs`、マルチバイト文字に変換できないワイド文字を検出した型にキャストする-1 を返します`size_t`設定と`errno`に`EILSEQ`です。  
  
## <a name="remarks"></a>コメント  
 `wcstombs` 関数は、`wcstr` が指すワイド文字列を対応するマルチバイト文字に変換し、`mbstr` 配列に結果を格納します。 `count` パラメーターはマルチバイト出力文字列に格納できる最大バイト数 (つまり、`mbstr` のサイズ) を示します。 通常、ワイド文字列を変換するときに必要になるバイト数は不明です。 出力文字列の 1 バイトだけを必要とするワイド文字もあれば、2 バイトを必要とする文字もあります。 入力文字列内のワイド文字 (ワイド文字の `NULL` を含む) 1 文字につき 2 バイトを持つマルチバイト出力文字列があれば、必ず収まります。  
  
 `wcstombs` は、`count` の発生前または発生時にワイド文字の null 文字 (L'\0') を検出すると、それを 8 ビットの 0 に変換して停止します。 このため、`mbstr` のマルチバイト文字の文字列が null 終了になるのは、`wcstombs` が変換中にワイド文字の null 文字を検出した場合だけです。 `wcstr` および `mbstr` が指すシーケンスが重なり合う場合、`wcstombs` の動作は未定義です。  
  
 `mbstr` 引数が `NULL` の場合、`wcstombs` は必要な対象文字列のサイズ (バイト数) を返します。  
  
 `wcstombs` はそのパラメーターを検証します。 場合`wcstr`は`NULL`、または`count`がより大きい`INT_MAX`、」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、-1 を返します。  
  
 `wcstombs` は、ロケールに依存するあらゆる動作に現在のロケールを使用します。`_wcstombs_l` は、渡されたロケールを代わりに使用することを除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
 C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`wcstombs`|\<stdlib.h>|  
|`_wcstombs_l`|\<stdlib.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 このプログラムは、`wcstombs` 関数の動作を示しています。  
  
```  
// crt_wcstombs.c  
// compile with: /W3  
// This example demonstrates the use  
// of wcstombs, which converts a string  
// of wide characters to a string of   
// multibyte characters.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t  count;  
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t *pWCBuffer = L"Hello, world.";  
  
    printf("Convert wide-character string:\n" );  
  
    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s instead  
    printf("   Characters converted: %u\n",  
            count );  
    printf("    Multibyte character: %s\n\n",  
           pMBBuffer );  
  
    free(pMBBuffer);  
}  
```  
  
```Output  
Convert wide-character string:  
   Characters converted: 13  
    Multibyte character: Hello, world.  
```  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs、_mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb、_wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)
