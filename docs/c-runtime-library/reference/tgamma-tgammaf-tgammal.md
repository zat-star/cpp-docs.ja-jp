---
title: "tgamma、tgammaf、tgammal | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tgamma
- tgammaf
- tgammal
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
dev_langs: C++
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fefaaaf6dd6e660c4cda53d28194d6052d1d8bf4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma、tgammaf、tgammal
指定した値のガンマ関数を決定します。  
  
## <a name="syntax"></a>構文  
  
```  
double tgamma(  
   double x  
);  
  
float tgamma(  
   float x  
); //C++ only  
  
long double tgamma(  
   long double x  
); //C++ only  
  
float tgammaf(  
   float x  
);  
  
long double tgammal(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `x`  
 ガンマを検索する値。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は `x` のガンマを返します。  
  
 `x` の大きさがデータ型に対して大きすぎる場合や小さすぎる場合は、範囲エラーが発生することがあります。 `x` <=0 の場合は、ドメイン エラーまたは範囲エラーが発生することがあります。  
  
|懸案事項|Return|  
|-----------|------------|  
|x ±0 を =|±INFINITY|  
|x = 負の整数|NaN|  
|x =  -INFINITY|NaN|  
|x = +INFINITY|+INFINITY|  
|x = NaN|NaN|  
|ドメイン エラー|NaN|  
|極エラー|±HUGE_VAL、±HUGE_VALF、または ±HUGE_VALL|  
|オーバーフロー範囲エラー|±HUGE_VAL、±HUGE_VALF、または ±HUGE_VALL|  
|アンダーフロー範囲エラー|丸めた後の正確な値。|  
  
 エラーは、[_matherr](../../c-runtime-library/reference/matherr.md) で指定されたとおりに報告されます。  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、float 型および long double 型を受け取って返す tgamma のオーバーロードを呼び出すことができます。 C プログラムでは、tgamma は常に double を受け取って返します。  
  
 x が自然数の場合、この関数は (x-1) の階乗を返します。  
  
## <a name="requirements"></a>必要条件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`tgamma`、`tgammaf`、`tgammal`|\<math.h>|\<cmath>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [lgamma、lgammaf、lgammal](../../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)