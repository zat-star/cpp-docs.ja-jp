---
title: "asin、asinf、asinl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- asinf
- asinl
- asin
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
- asin
- asinl
- asinf
dev_langs: C++
helpviewer_keywords:
- asin function
- asinl function
- asinf function
- trigonometric functions
- arcsine function
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5cc24746771c4e494648796847afee58e0bdf09c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="asin-asinf-asinl"></a>asin、asinf、asinl
アークサインを計算します。  
  
## <a name="syntax"></a>構文  
  
```  
double asin(   
   double x   
);  
float asin(  
   float x  
);  // C++ only  
long double asin(  
   long double x  
);  // C++ only  
float asinf (   
   float x   
);  
long double asinl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 アークサインが計算される値。  
  
## <a name="return-value"></a>戻り値  
 `asin`のアークサイン (逆サ イン関数) を返します`x`範囲 - π/2 ~ π/2 ラジアンにします。  
  
 既定では場合、`x`が-1 未満か、1 より大きい`asin`は不定値を返します。  
  
|入力|SEH 例外|Matherr 例外|  
|-----------|-------------------|-----------------------|  
|± ∞|`INVALID`|`_DOMAIN`|  
|± `QNAN`,`IND`|none|`_DOMAIN`|  
|&#124;x&#124;>1|`INVALID`|`_DOMAIN`|  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、`asin` および `float` で `long double` のオーバーロードを呼び出すことができます。 C プログラムでは、`asin` は常に double を受け取って返します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`asin`、`asinf`、`asinl`|\<math.h>|  
  
## <a name="example"></a>例  
 詳細については、「[acos、acosf、acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [acos、acosf、acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [atan、atanf、atanl、atan2、atan2f、atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos、cosf、cosl、cosh、coshf、coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin、sinf、sinl、sinh、sinhf、sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan、tanf、tanl、tanh、tanhf、tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)