---
title: "cos、cosf、cosl、cosh、coshf、coshl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- coshl
- cosh
- cos
- cosl
- cosf
- coshf
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
- coshl
- cos
- cosf
- cosh
- cosl
- coshf
dev_langs:
- C++
helpviewer_keywords:
- cosines
- cosl function
- calculating cosine
- cosf function
- cos function
- cosh function
- coshf function
- trigonometric functions
- cosines, calculating
- coshl function
- hyperbolic functions
ms.assetid: ae90435e-6b68-4a47-a81f-be87d5c08f16
caps.latest.revision: 17
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
ms.openlocfilehash: f1fb949ba33299a8d18c41341b5fd76a776ee387
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="cos-cosf-cosl-cosh-coshf-coshl"></a>cos、cosf、cosl、cosh、coshf、coshl
コサイン (`cos`、`cosf`、または `cosl`)、またはハイパーボリック コサイン (`cosh`、`coshf`、または `coshl`) を計算します。  
  
## <a name="syntax"></a>構文  
  
```  
double cos(   
   double x   
);  
float cos(  
   float x   
);  // C++ only  
long double cos(  
   long double x  
);  // C++ only  
float cosf(   
   float x   
);  
long double cosl(  
   long double x  
);  
double cosh(   
   double x   
);  
float cosh(  
   float x   
);  // C++ only  
long double cosh(  
   long double x  
);  // C++ only  
float coshf(  
   float x   
);  
long double coshl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 角度 (ラジアン)。  
  
## <a name="return-value"></a>戻り値  
 `x` のコサインまたはハイパーボリック コサイン。 場合`x`263 以上-263 への呼び出しの結果から有意性損失以下`cos`、 `cosf`、または`cosl`に発生します。  
  
 既定では、`cosh`、`coshf`、または `coshl` の呼び出しで結果が大きすぎる場合、関数は `HUGE_VAL` を返し、`errno` に `ERANGE` を設定します。  
  
|入力|SEH 例外|Matherr 例外|  
|-----------|-------------------|-----------------------|  
|± `QNAN`,`IND`|none|`_DOMAIN`|  
|± ∞  (`cosf`, `cos`, `cosl`)|`INVALID`|`_DOMAIN`|  
|x ≥ 7.104760e+002  (`cosh`、`coshf`、`coshl`)|`INEXACT`+`OVERFLOW`|`OVERFLOW`|  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、`cos` または `cosh` の値を受け取って返す `float` および `long double` のオーバーロードを呼び出すことができます。 C プログラムでは、`cos` および `cosh` は常に `double` を受け取って返します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`cos`, `cosh`, `cosf`, `coshf`, `cosl`, `coshl`|\<math.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 「[sin、sinf、sinl、sinh、sinhf、sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)」の例をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [acos、acosf、acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin、asinf、asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan、atanf、atanl、atan2、atan2f、atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin、sinf、sinl、sinh、sinhf、sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan、tanf、tanl、tanh、tanhf、tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [_CIcos](../../c-runtime-library/cicos.md)
