---
title: btowc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- btowc
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
- btowc
dev_langs:
- C++
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
caps.latest.revision: 10
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 3b6655ba240d306d2f919a844c08b310b291d859
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="btowc"></a>btowc
初回のシフト状態で整数が有効なシングルバイト文字を表すかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```  
wint_t btowc(  
   int c  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 テストする整数。  
  
## <a name="return-value"></a>戻り値  
 初回のシフト状態で整数が有効なシングルバイト文字を表す場合、文字のワイド文字表現を返します。 初回のシフト状態で整数が EOF の場合、あるいは有効なシングルバイト文字ではない場合、WEOF を返します。 この関数の出力は、現在の `LC_TYPE` ロケールによって変わります。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`btowc`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)
