---
title: "exp2、exp2f、exp2l | Microsoft ドキュメント"
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
- exp2
- exp2f
- exp2l
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
- exp2
- math/exp2
- exp2f
- math/exp2f
- exp2l
- math/exp2l
dev_langs:
- C++
helpviewer_keywords:
- exp2 function
- exp2f function
- exp2l function
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
caps.latest.revision: 13
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
ms.openlocfilehash: 4c3e31359c096dddfc7d71dcd7887c405b9aa0af
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="exp2-exp2f-exp2l"></a>exp2、exp2f、exp2l
2 の指定した値を計算します。  
  
## <a name="syntax"></a>構文  
  
```  
double exp2(  
   double x  
);  
  
float exp2(  
   float x  
);  // C++ only  
  
long double exp2(  
   long double x  
); // C++ only  
  
float exp2f(  
   float x  
);  
  
long double exp2l(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `x`  
 指数部の値です。  
  
## <a name="return-value"></a>戻り値  
 成功した場合の 2 を底と指数を返します`x`、つまり、2<sup>x</sup>です。 それ以外の場合、次の値のいずれかを返します。  
  
|懸案事項|リターン|  
|-----------|------------|  
|`x` = ±0|1|  
|`x` = -INFINITY|+0|  
|`x` = +INFINITY|+INFINITY|  
|`x` = NaN|NaN|  
|オーバーフロー範囲エラー|+HUGE_VAL、+HUGE_VALF、または +HUGE_VALL|  
|アンダーフロー範囲エラー|丸め処理の後に、正しい結果|  
  
 エラーは、[_matherr](../../c-runtime-library/reference/matherr.md) で指定されたとおりに報告されます。  
  
## <a name="remarks"></a>コメント  
 C++ では、オーバー ロードできるよう、ためのオーバー ロードを呼び出すことができます`exp2`を受け取り、返します**float**と**long double**型です。 C プログラムでは、`exp2`常に受け取りを返す、**二重**です。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|C ヘッダー|C++ ヘッダー|  
|-------------|--------------|------------------|  
|`exp`、`expf`、`expl`|\<math.h>|\<cmath>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp、expf、策の説明](../../c-runtime-library/reference/exp-expf.md)   
 [log2、log2f、log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)
