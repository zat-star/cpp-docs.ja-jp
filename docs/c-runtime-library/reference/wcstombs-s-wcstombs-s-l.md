---
title: "wcstombs_s、_wcstombs_s_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcstombs_s_l
- wcstombs_s
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
- wcstombs_s
- _wcstombs_s_l
dev_langs:
- C++
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 41775d158213a79debbdb4245fc468694df8646e
ms.lasthandoff: 02/24/2017

---
# <a name="wcstombss-wcstombssl"></a>wcstombs_s、_wcstombs_s_l
ワイド文字のシーケンスを、対応するマルチバイト文字のシーケンスに変換します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおりセキュリティが強化されたバージョンの [wcstombs、_wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count   
);  
errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `pReturnValue`  
 変換された文字数。  
  
 [出力] `mbstr`  
 結果として変換されたマルチバイト文字の文字列のバッファーのアドレス。  
  
 [入力] `sizeInBytes`  
 `mbstr` バッファーのサイズ (バイト数)。  
  
 [入力] `wcstr`  
 変換するワイド文字の文字列を指します。  
  
 [入力] `count`  
 `mbstr` バッファーに格納する最大バイト数 (終端の null を含みません) か、[_TRUNCATE](../../c-runtime-library/truncate.md)。  
  
 [入力] `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は&0; を返します。失敗した場合はエラー コードを返します。  
  
|エラー条件|戻り値および `errno`|  
|---------------------|------------------------------|  
|`mbstr` が `NULL` で `sizeInBytes` > 0|`EINVAL`|  
|`wcstr` は `NULL` です|`EINVAL`|  
|コピー先のバッファーが小さすぎて変換後の文字列を含めることができません (`count` が `_TRUNCATE` の場合を除きます。下記の「解説」を参照してください)|`ERANGE`|  
  
 これらのいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター例外が呼び出されます。 実行の続行が許可された場合、関数はエラー コードを返し、表に示すように `errno` を設定します。  
  
## <a name="remarks"></a>コメント  
 `wcstombs_s` 関数は、`wcstr` が指すワイド文字の文字列を、`mbstr` が指すバッファーに格納されるマルチバイト文字に変換します。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。  
  
-   ワイド文字の null が検出されました。  
  
-   変換できないワイド文字が検出されました。  
  
-   `mbstr` バッファーに格納されているバイト数が `count` と同じです。  
  
 変換先の文字列は、エラーの場合を含め、常に null で終わります。  
  
 `count` が特殊値 [_TRUNCATE](../../c-runtime-library/truncate.md) の場合、`wcstombs_s` は null 終端文字用の空きを残して、コピー先のバッファーに収まる限りの文字列を変換します。  
  
 `wcstombs_s` は、元の文字列を正常に変換すると、null 終端文字を含む変換後の文字列のサイズ (バイト数) を `*``pReturnValue` に書き込みます (`pReturnValue` が `NULL`でない場合に限ります)。 これは、`mbstr` 引数が `NULL` である場合でも発生し、必要なバッファー サイズを決定する方法を提供します。 `mbstr` が `NULL` の場合は、`count` は無視されることに注意してください。  
  
 マルチバイト文字に変換できないワイド文字が検出された場合、`wcstombs_s` は `*``pReturnValue` に 0 を入れ、コピー先バッファーを空文字列に設定し、`errno` を `EILSEQ` に設定して、`EILSEQ` を返します。  
  
 `wcstr` および `mbstr` が指すシーケンスが重なり合う場合、`wcstombs_s` の動作は未定義です。  
  
> [!IMPORTANT]
>  `wcstr` と `mbstr` が重なり合わず、変換するワイド文字の数が `count` に適切に反映されていることを確認します。  
  
 `wcstombs_s` は、ロケールに依存するあらゆる動作に現在のロケールを使用します。`_wcstombs_s_l` は、渡されたロケールを代わりに使用することを除いて `wcstombs` と同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
 C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`wcstombs_s`|\<stdlib.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 このプログラムは、`wcstombs_s` 関数の動作を示しています。  
  
```  
// crt_wcstombs_s.c  
// This example converts a wide character  
// string to a multibyte character string.  
#include <stdio.h>  
#include <stdlib.h>  
#include <assert.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t   i;  
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t*pWCBuffer = L"Hello, world.";  
  
    printf( "Convert wide-character string:\n" );  
  
    // Conversion  
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,   
               pWCBuffer, (size_t)BUFFER_SIZE );  
  
    // Output  
    printf("   Characters converted: %u\n", i);  
    printf("    Multibyte character: %s\n\n",  
     pMBBuffer );  
  
    // Free multibyte character buffer  
    if (pMBBuffer)  
    {  
    free(pMBBuffer);  
    }  
}  
```  
  
```Output  
Convert wide-character string:  
   Characters converted: 14  
    Multibyte character: Hello, world.  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs、_mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb_s、_wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)
