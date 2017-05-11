---
title: "isascii、__isascii、iswascii | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- iswascii
- __isascii
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
- iswascii
- istascii
- __isascii
- _istascii
- isascii
- ctype/isascii
- ctype/__isascii
- corecrt_wctype/iswascii
dev_langs:
- C++
helpviewer_keywords:
- __isascii function
- _isascii function
- isascii function
- _istascii function
- istascii function
- iswascii function
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 401d8d05cc80ef1c72e7c72c06f94707b8c9848b
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="isascii-isascii-iswascii"></a>isascii、__isascii、iswascii
特定の文字が ASCII 文字かどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```  
int __isascii(   
   int c   
);  
int iswascii(   
   wint_t c   
);  
#define isascii __isascii  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 テストする整数。  
  
## <a name="return-value"></a>戻り値  
 これらのルーチンでは、`c` が ASCII 文字の特殊表現の場合は 0 以外の値を返します。 `__isascii`場合は 0 以外の値を返します`c`は、ASCII 文字 (0x00 0x7F の範囲で)。 `iswascii` は、`c` が ASCII 文字のワイド文字表現の場合は 0 以外の値を返します。 これらの各ルーチンは、`c` がテスト条件を満たしていない場合は 0 を返します。  
  
## <a name="remarks"></a>コメント  
 `__isascii` と `iswascii` は両方とも、プリプロセッサ マクロ _CTYPE_DISABLE_MACROS が定義されていない場合、マクロとして実装されます。  
  
 旧バージョンとの互換性のため、`isascii` は [__STDC\_\_](../../preprocessor/predefined-macros.md) が定義されていないか 0 として定義されている場合のみマクロとして実装されます。それ以外の場合は未定義です。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_istascii`|`__isascii`|`__isascii`|`iswascii`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`isascii`, `__isascii`|C: \<ctype.h><br /><br /> C++: \<cctype> または \<ctype.h>|  
|`iswascii`|C: \<wctype.h>、\<ctype.h>、または \<wchar.h><br /><br /> C++: \<cwctype>、\<cctype>、\<wctype.h>、\<ctype.h>、または \<wchar.h>|  
  
 `isascii`、`__isascii`、`iswascii` の各関数は、Microsoft 固有の関数です。 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)
