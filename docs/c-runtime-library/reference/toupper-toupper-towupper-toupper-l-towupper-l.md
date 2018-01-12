---
title: "toupper、_toupper、towupper、_toupper_l、_towupper_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- towupper
- _toupper
- _totupper
- toupper
dev_langs: C++
helpviewer_keywords:
- _toupper function
- towupper function
- uppercase, converting strings to
- totupper function
- string conversion, to different characters
- towupper_l function
- toupper_l function
- string conversion, case
- _toupper_l function
- _towupper_l function
- _totupper function
- case, converting
- characters, converting
- toupper function
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0414cd211cb9b833f24d2aac9ad9a82758c4efcf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="toupper-toupper-towupper-toupperl-towupperl"></a>toupper、_toupper、towupper、_toupper_l、_towupper_l
文字を大文字に変換します。  
  
## <a name="syntax"></a>構文  
  
```  
int toupper(  
   int c   
);  
int _toupper(  
   int c   
);  
int towupper(  
   wint_t c   
);  
int _toupper_l(  
   int c ,  
   _locale_t locale  
);  
int _towupper_l(  
   wint_t c ,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 変換する文字。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 これらの各ルーチンは、可能な場合は `c` のコピーを変換し、結果を返します。  
  
 `c` が、`iswlower` が 0 以外のワイド文字であり、`iswupper` が 0 以外の対応するワイド文字がある場合、`towupper` は対応するワイド文字を返します。そうでない場合は、`towupper` は変更されないままの `c` を返します。  
  
 エラーを示す戻り値は予約されていません。  
  
 `toupper` が予想どおりの結果を返すためには、[__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) と [islower](../../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md) がどちらも 0 以外を返す必要があります。  
  
## <a name="remarks"></a>コメント  
 これらの各ルーチンは、変換が可能で適切な場合に、指定した小文字を適宜大文字に変換します。 `towupper` の大文字/小文字の変換は、ロケール固有です。 現在のロケールに関連する文字の大文字/小文字のみが変換されます。 `_l` サフィックスが付いていない関数では、現在設定されているロケールを使用します。 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在設定されているロケールの代わりに、パラメーターとして渡されたロケールを使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
 `toupper` が予想どおりの結果を返すためには、[__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) と [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) がどちらも 0 以外を返す必要があります。  
  
 [データ変換ルーチン](../../c-runtime-library/data-conversion.md)  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_totupper`|`toupper`|`_mbctoupper`|`towupper`|  
|`_totupper_l`|`_toupper_l`|`_mbctoupper_l`|`_towupper_l`|  
  
> [!NOTE]
>  `_toupper_l` および `_towupper_l` はロケールに依存せず、直接呼び出すためのものではありません。 これらは、`_totupper_l` による内部使用のために用意されています。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`toupper`|\<ctype.h>|  
|`_toupper`|\<ctype.h>|  
|`towupper`|\<ctype.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 「[to 系関数](../../c-runtime-library/to-functions.md)」の例をご覧ください。  
  
## <a name="see-also"></a>参照  
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)   
 [to 系関数](../../c-runtime-library/to-functions.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)