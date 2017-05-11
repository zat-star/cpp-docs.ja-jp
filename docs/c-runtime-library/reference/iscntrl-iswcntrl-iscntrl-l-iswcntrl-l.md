---
title: "iscntrl、iswcntrl、_iscntrl_l、_iswcntrl_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- iscntrl
- _iswcntrl_l
- _iscntrl_l
- iswcntrl
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
- _istcntrl_l
- _iswcntrl_l
- iswcntrl
- _iscntrl_l
- iscntrl
- _istcntrl
dev_langs:
- C++
helpviewer_keywords:
- iscntrl function
- _iscntrl_l function
- _iswcntrl_l function
- _istcntrl function
- istcntrl function
- iswcntrl function
- _istcntrl_l function
ms.assetid: 616eebf9-aed4-49ba-ba2c-8677c8fe6fb5
caps.latest.revision: 19
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
ms.openlocfilehash: def32829b1be9e5b4076905cd80a475cf589a646
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="iscntrl-iswcntrl-iscntrll-iswcntrll"></a>iscntrl、iswcntrl、_iscntrl_l、_iswcntrl_l
整数が制御文字を表すかどうかを判定します。  
  
## <a name="syntax"></a>構文  
  
```  
int iscntrl(   
   int c   
);  
int iswcntrl(   
   wint_t c   
);  
int _iscntrl_l(   
   int c,  
   _locale_t locale  
);  
int _iswcntrl_l(   
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 テストする整数  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 これらの各ルーチンでは、`c` が制御文字の特殊表現の場合は 0 以外の値を返します。 `iscntrl`場合は 0 以外の値を返します`c`制御文字 (0x00-0x1F または 0x7F)。 `iswcntrl` が制御ワイド文字の場合、`c` は 0 以外の値を返します。 これらの各ルーチンは、`c` がテスト条件を満たしていない場合は 0 を返します。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のロケールの代わりに渡されたロケール パラメーターを使用します。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
 `iscntrl` と `_iscntrl_l` の動作は、`c` が EOF ではなく、かつ、0 ～ 0xFF の範囲でない場合は未定義です。 CRT デバッグ ライブラリを使用し、`c` がこれらの値のうちのいずれかの値でない場合は、アサーションが発生します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istcntrl`|`iscntrl`|`iscntrl`|`iswcntrl`|  
|`_istcntrl_l`|`_iscntrl_l`|`_iscntrl_l`|`_iswcntrl_l`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`iscntrl`|\<ctype.h>|  
|`iswcntrl`|\<ctype.h> または \<wchar.h>|  
|`_iscntrl_l`|\<ctype.h>|  
|`_iswcntrl_l`|\<ctype.h> または \<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)
