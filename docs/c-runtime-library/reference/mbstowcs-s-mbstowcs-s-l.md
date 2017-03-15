---
title: "mbstowcs_s、_mbstowcs_s_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbstowcs_s_l
- mbstowcs_s
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
- _mbstowcs_s_l
- mbstowcs_s
dev_langs:
- C++
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 3a5c84be1336d762289705102c1f2213f04642ea
ms.lasthandoff: 02/24/2017

---
# <a name="mbstowcss-mbstowcssl"></a>mbstowcs_s、_mbstowcs_s_l
マルチバイト文字のシーケンスを、対応するワイド文字のシーケンスに変換します。 「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) で説明されているように、セキュリティが強化されたバージョンの [mbstowcs、_mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count   
);  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `pReturnValue`  
 変換された文字数。  
  
 [出力] `wcstr`  
 結果として変換されたワイド文字の文字列のバッファーのアドレス。  
  
 [入力] `sizeInWords`  
 `wcstr` バッファーのサイズ (単語単位)。  
  
 [入力]`mbstr`  
 NULL で終了するマルチバイト文字のシーケンスのアドレス。  
  
 [入力] `count`  
 `wcstr` バッファーに格納するワイド文字の最大数 (終端の null を含みません) か、[_TRUNCATE](../../c-runtime-library/truncate.md)。  
  
 [入力] `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は&0; を返します。失敗した場合はエラー コードを返します。  
  
|エラー条件|戻り値および `errno`|  
|---------------------|------------------------------|  
|`wcstr` が `NULL` で `sizeInWords` > 0|`EINVAL`|  
|`mbstr` は `NULL` です|`EINVAL`|  
|変換先バッファーが小さすぎて変換後の文字列が収まらない (`count` が `_TRUNCATE` の場合は例外。下記の「解説」を参照)|`ERANGE`|  
|`wcstr` が `NULL` ではなく、 `sizeInWords` == 0|`EINVAL`|  
  
 これらのいずれかの条件が発生すると、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター例外が呼び出されます。 実行の続行が許可された場合、関数はエラー コードを返し、表に示すように `errno` を設定します。  
  
## <a name="remarks"></a>コメント  
 `mbstowcs_s` 関数は、`mbstr` が指すマルチバイト文字列を、`wcstr` が指すバッファーに格納されるワイド文字に変換します。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。  
  
-   マルチバイトの null 文字が検出されました。  
  
-   無効なマルチバイト文字が検出されました。  
  
-   `wcstr` バッファーに格納されているワイド文字の数が `count` と同じです。  
  
 変換後の文字列は、常に null で終わります (エラーの場合も同様)。  
  
 `count` が特殊値 [_TRUNCATE](../../c-runtime-library/truncate.md) の場合、`mbstowcs_s` は null 終端文字&1; つ分を残して、変換先バッファーに収まる限りの文字列を変換します。  
  
 `mbstowcs_s` は、元の文字列を正常に変換すると、変換後の文字列のワイド文字と null 終端文字のサイズを `*``pReturnValue` に書き込みます (`pReturnValue` が `NULL`でない場合に限ります)。 これは、`wcstr` 引数が `NULL`である場合でも発生し、必要なバッファー サイズを決定する方法を提供します。 `wcstr` が `NULL` の場合は、`count` は無視され、`sizeInWords` は 0 でなければいけないことに注意してください。  
  
 `mbstowcs_s` は、無効なマルチバイト文字が検出された場合、`*``pReturnValue` に 0 を入れ、変換先バッファーを空の文字列に設定し、`errno` を `EILSEQ` に設定して、`EILSEQ` を返します。  
  
 `mbstr` および `wcstr` が指すシーケンスが重なり合う場合、`mbstowcs_s` の動作は未定義です。  
  
> [!IMPORTANT]
>  `wcstr` と `mbstr` が重なり合わず、変換するマルチバイト文字の数が `count` に適切に反映されていることを確認します。  
  
 `mbstowcs_s` は、ロケールに依存するあらゆる動作に現在のロケールを使用します。`_mbstowcs_s_l` は、渡されたロケールを代わりに使用することを除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
 C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`mbstowcs_s`|\<stdlib.h>|  
|`_mbstowcs_s_l`|\<stdlib.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs、_wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb、_wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)
