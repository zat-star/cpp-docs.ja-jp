---
title: "atan、atanf、atanl、atan2、atan2f、atan2l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- atan2f
- atan2l
- atan2
- atanf
- atan
- atanl
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
- atan
- atan2l
- atan2
- atanl
- atanf
- atan2f
dev_langs: C++
helpviewer_keywords:
- atan function
- atanf function
- atanl function
- atan2 function
- atan2l function
- arctangent function
- trigonometric functions
- atan2f function
ms.assetid: 7a87a18e-c94d-4727-9cb1-1bb5c2725ae4
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36e90d781c4cc4512f4869247c296b69b19c1f9b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>atan、atanf、atanl、atan2、atan2f、atan2l
`x` (`atan`、`atanf`、および `atanl`) のアークタンジェントまたは `y`/`x` (`atan2`、`atan2f`、および `atan2l`) のアークタンジェントを計算します。  
  
## <a name="syntax"></a>構文  
  
```  
double atan(   
   double x   
);  
float atan(  
   float x   
);  // C++ only  
long double atan(  
   long double x  
);  // C++ only  
double atan2(   
   double y,   
   double x   
);  
float atan2(  
   float y,  
   float x  
);  // C++ only  
long double atan2(  
   long double y,  
   long double x  
);  // C++ only  
float atanf(   
   float x   
);  
long double atanl(  
   long double x  
);  
float atan2f(  
   float y,  
   float x  
);  
long double atan2l(  
   long double y,  
   long double x  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`, `y`  
 任意の数値。  
  
## <a name="return-value"></a>戻り値  
 `atan`タンジェントを返します`x`範囲 - π/2 ~ π/2 ラジアンにします。 `atan2`タンジェントを返します`y/x`範囲 π ~ π ラジアンにします。 `x` が 0 の場合、`atan` は 0 を返します。 `atan2` のパラメーターが両方とも 0 の場合、関数は 0 を返します。 すべての結果はラジアンにあります。  
  
 `atan2` は、両方のパラメーターの符号を使用して、戻り値のクアドラントを判断します。  
  
|入力|SEH 例外|Matherr 例外|  
|-----------|-------------------|-----------------------|  
|± `QNAN`,`IND`|none|`_DOMAIN`|  
  
## <a name="remarks"></a>コメント  
 `atan` 関数は、`x` のアークタンジェント (逆タンジェント関数) を計算します。 `atan2` は `y`/`x` のアークタンジェントを計算します (`x` が 0 と等しい場合、`atan2` は π/2 (`y` が正の場合)、-π/2 (`y` が負の場合)、または 0 (`y` が 0 の場合) をそれぞれ返します)。  
  
 `atan` には、ストリーミング SIMD 拡張機能 (SSE2) を使用して実装されています。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md)」を参照してください。  
  
 C++ ではオーバーロードが可能であるため、`atan` および `atan2` のオーバーロードを呼び出すことができます。 C プログラムでは、`atan` および `atan2` は、常に double を受け取って返します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`atan`, `atan2`, `atanf`, `atan2f`, `atanl`, `atan2l`|\<math.h>|  
  
## <a name="example"></a>例  
  
```  
// crt_atan.c  
// arguments: 5 0.5  
#include <math.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( int ac, char* av[] )   
{  
   double x, y, theta;  
   if( ac != 3 ){  
      fprintf( stderr, "Usage: %s <x> <y>\n", av[0] );  
      return 1;  
   }  
   x = atof( av[1] );  
   theta = atan( x );  
   printf( "Arctangent of %f: %f\n", x, theta );  
   y = atof( av[2] );  
   theta = atan2( y, x );  
   printf( "Arctangent of %f / %f: %f\n", y, x, theta );   
   return 0;  
}  
```  
  
```Output  
Arctangent of 5.000000: 1.373401  
Arctangent of 0.500000 / 5.000000: 0.099669  
```  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [acos、acosf、acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin、asinf、asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [cos、cosf、cosl、cosh、coshf、coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin、sinf、sinl、sinh、sinhf、sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan、tanf、tanl、tanh、tanhf、tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [_CIatan](../../c-runtime-library/ciatan.md)   
 [_CIatan2](../../c-runtime-library/ciatan2.md)