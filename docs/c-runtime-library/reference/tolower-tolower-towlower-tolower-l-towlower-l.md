---
title: "tolower、_tolower、towlower、_tolower_l、_towlower_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _tolower_l
- towlower
- tolower
- _tolower
- _towlower_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _totlower
- tolower
- _tolower
- towlower
dev_langs: C++
helpviewer_keywords:
- tolower_l function
- _tolower_l function
- totlower function
- string conversion, to different characters
- lowercase, converting to
- tolower function
- string conversion, case
- towlower function
- _tolower function
- _totlower function
- towlower_l function
- case, converting
- characters, converting
- _towlower_l function
ms.assetid: 86e0fc02-94ae-4472-9631-bf8e96f67b92
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7fe06748a6e349f612fdf564c9aed917e43f164b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tolower-tolower-towlower-tolowerl-towlowerl"></a>tolower、_tolower、towlower、_tolower_l、_towlower_l
文字を小文字に変換します。  
  
## <a name="syntax"></a>構文  
  
```  
int tolower(  
   int c   
);  
int _tolower(  
   int c   
);  
int towlower(  
   wint_t c   
);  
int _tolower_l(  
   int c,  
   _locale_t locale   
);  
int _towlower_l(  
   wint_t c,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `c`  
 変換する文字。  
  
 [入力] `locale`  
 ロケール固有の変換に使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 これらの各ルーチンは、変換が可能な場合に `c` のコピーを小文字に変換し、結果を返します。 エラーを示す戻り値は予約されていません。  
  
## <a name="remarks"></a>コメント  
 これらの各ルーチンは、変換が可能で適切な場合に、指定した大文字を適宜小文字に変換します。 `towlower` の大文字/小文字の変換は、ロケール固有です。 現在のロケールに関連する文字の大文字/小文字のみが変換されます。 `_l` サフィックスが付いていない関数では、現在設定されているロケールを使用します。 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在設定されているロケールの代わりに、パラメーターとして渡されたロケールを使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
 `_tolower` が予想どおりの結果を返すためには、[__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) と [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) がどちらも 0 以外を返す必要があります。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_totlower`|`tolower`|`_mbctolower`|`towlower`|  
|`_totlower_l`|`_tolower_l`|`_mbctolower_l`|`_towlower_l`|  
  
> [!NOTE]
>  `_tolower_l` および `_towlower_l` はロケールに依存せず、直接呼び出すためのものではありません。 これらは、`_totlower_l` による内部使用のために用意されています。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`tolower`|\<ctype.h>|  
|`_tolower`|\<ctype.h>|  
|`towlower`|\<ctype.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 「[to 系関数](../../c-runtime-library/to-functions.md)」の例をご覧ください。  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)   
 [to 系関数](../../c-runtime-library/to-functions.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)