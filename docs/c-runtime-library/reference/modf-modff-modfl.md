---
title: "modf、modff、modfl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- modff
- modf
- modfl
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
- modff
- _modfl
- modf
- modfl
- math/modf
- math/modff
- math/modfl
dev_langs: C++
helpviewer_keywords:
- modf function
- modff function
- modfl function
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a75cc474d66a42f3faeb7444f3168c7cc3283514
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="modf-modff-modfl"></a>modf、modff、modfl
浮動小数点値を小数部と整数部に分割します。  
  
## <a name="syntax"></a>構文  
  
```  
double modf(  
   double x,  
   double * intptr   
);  
float modf(  
   float x,  
   float * intptr  
);  // C++ only  
long double modf(  
   long double x,  
   long double * intptr  
);  // C++ only  
float modff(  
   float x,  
   float * intptr   
);  
long double modfl(  
   long double x,  
   long double * intptr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *x*  
 浮動小数点値。  
  
 `intptr`  
 格納された整数部分へのポインター。  
  
## <a name="return-value"></a>戻り値  
 この関数は *x* の符号付き小数部を返します。 エラーの戻り値はありません。  
  
## <a name="remarks"></a>コメント  
 `modf` 関数は、浮動小数点値 `x` を小数部と整数部に分割します。それぞれの符号は `x` と同じです。 `x` の符号付き小数部分を返します。 整数部分は浮動小数点値として `intptr.` に格納されます。  
  
 `modf` には、ストリーミング SIMD 拡張機能 (SSE2) を使用して実装されています。 SSE2 実装の使い方の詳細および制約については、[_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md) を参照してください。  
  
 C++ ではオーバーロードができるため、`float` または `long double` のパラメーターを受け取って返す `modf` のオーバーロードを呼び出すことができます。 C プログラムでは、`modf` は常に 2 個の double 値を受け取って、double 値を返します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`modf`、`modff`、`modfl`|C: \<math.h><br /><br /> C++: \<cmath> または \<math.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_modf.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y, n;  
  
   x = -14.87654321;      /* Divide x into its fractional */  
   y = modf( x, &n );     /* and integer parts            */  
  
   printf( "For %f, the fraction is %f and the integer is %.f\n",   
           x, y, n );  
}  
```  
  
## <a name="output"></a>出力  
  
```  
For -14.876543, the fraction is -0.876543 and the integer is -14  
```  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)