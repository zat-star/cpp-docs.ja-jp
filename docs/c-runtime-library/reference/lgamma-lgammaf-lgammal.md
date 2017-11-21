---
title: "lgamma、lgammaf、lgammal | Microsoft Docs"
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
- lgamma
- lgammaf
- lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
dev_langs: C++
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: afc048d131bd75a9645c045b3bceae90344c07eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma、lgammaf、lgammal
指定した値のガンマ関数の絶対値の自然対数を決定します。  
  
## <a name="syntax"></a>構文  
  
```  
double lgamma(  
   double x  
);  
  
float lgamma(  
   float x  
); //C++ only  
  
long double lgamma(  
   long double x  
); //C++ only  
  
float lgammaf(  
   float x  
);  
  
long double lgammal(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `x`  
 計算される値です。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、`x.` のガンマ関数の絶対値の自然対数を返します。  
  
|問題点|リターン|  
|-----------|------------|  
|`x` = NaN|NaN|  
|`x` = ±0|+INFINITY|  
|`x`= 負の整数|+INFINITY|  
|±INFINITY|+INFINITY|  
|極エラー|+HUGE_VAL、+HUGE_VALF、または +HUGE_VALL|  
|オーバーフロー範囲エラー|±HUGE_VAL、±HUGE_VALF、または ±HUGE_VALL|  
  
 エラーは、[_matherr](../../c-runtime-library/reference/matherr.md) で指定されたとおりに報告されます。  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、float 型および long double 型を受け取って返す `lgamma` のオーバーロードを呼び出すことができます。 C プログラムでは、`lgamma` は常に double を受け取って返します。  
  
 x が有理数の場合、この関数は (`x`-1) の階乗の対数を返します。  
  
## <a name="requirements"></a>要件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`lgamma`、`lgammaf`、`lgammal`|\<math.h>|\<cmath>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [tgamma、tgammaf、tgammal](../../c-runtime-library/reference/tgamma-tgammaf-tgammal.md)