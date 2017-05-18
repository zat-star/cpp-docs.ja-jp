---
title: "acos、acosf、acosl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- acosf
- acos
- acosl
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
- acos
- acosl
- acosf
- math/acosf
- math/acosl
dev_langs:
- C++
helpviewer_keywords:
- acos function
- acosl function
- acosf function
- trigonometric functions
- arccosine function
ms.assetid: 00b89c48-8faf-4824-aa95-fa4349a4975d
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
ms.openlocfilehash: 5b5b2e5bca54f65a6fa54d43f92f60a704135110
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="acos-acosf-acosl"></a>acos、acosf、acosl
アークコサインを計算します。  
  
## <a name="syntax"></a>構文  
  
```  
double acos(   
   double x   
);  
float acos(  
   float x   
);   // C++ only  
long double acos(  
   long double x  
);   // C++ only  
float acosf(  
   float x   
);  
long double acosl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 値-1 ~ 1 のアーク コサイン (逆余弦) を計算するため、範囲です。  
  
## <a name="return-value"></a>戻り値  
 `acos` 関数は、0 ～ π ラジアンの範囲で `x` のアークコサインを返します。  
  
 既定では場合、`x`が-1 未満か、1 より大きい`acos`は不定値を返します。  
  
|入力|SEH 例外|Matherr 例外|  
|-----------|-------------------|-----------------------|  
|± ∞|`INVALID`|`_DOMAIN`|  
|± QNAN、IND|none|`_DOMAIN`|  
|&#124;x&#124;>1|`INVALID`|`_DOMAIN`|  
  
## <a name="remarks"></a>コメント  
 C++ ではオーバーロードが可能であるため、`acos` 型および `float` 型を受け取って返す `long double` のオーバーロードを呼び出すことができます。 C プログラムでは、`acos` は常に `double` を受け取って返します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|-------------|---------------------|----------------------|  
|`acos`、`acosf`、`acosl`|\<math.h>|\<errno.h>|  
  
## <a name="example"></a>例  
 このプログラムは、-1 ～ 1 の範囲の値の入力を求めます。 入力値がこの範囲外の場合、`_DOMAIN` エラー メッセージを生成します。 有効な値が入力された場合、プログラムはその値のアークサインとアークコサインを出力します。  
  
```  
// crt_asincos.c  
// arguments: 0  
  
#include <math.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( int ac, char* av[] )  
{  
    double  x,  
            y;  
    errno_t err;   
  
    // argument checking  
    if (ac != 2)  
    {  
        fprintf_s( stderr, "Usage: %s <number between -1 and 1>\n",  
                   av[0]);  
        return 1;  
    }  
  
    // Convert argument into a double value  
    if ((err = sscanf_s( av[1], "%lf", &x )) != 1)  
    {  
        fprintf_s( stderr, "Error converting argument into ",  
                   "double value.\n");  
        return 1;  
    }  
  
    // Arcsine of X  
    y = asin( x );  
    printf_s( "Arcsine of %f = %f\n", x, y );  
  
    // Arccosine of X  
    y = acos( x );  
    printf_s( "Arccosine of %f = %f\n", x, y );  
}  
```  
  
```Output  
Arcsine of 0.000000 = 0.000000  
Arccosine of 0.000000 = 1.570796  
```  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [asin、asinf、asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan、atanf、atanl、atan2、atan2f、atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos、cosf、cosl、cosh、coshf、coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin、sinf、sinl、sinh、sinhf、sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan、tanf、tanl、tanh、tanhf、tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)
