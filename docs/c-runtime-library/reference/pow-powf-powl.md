---
title: "pow、powf、powl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- powl
- pow
- powf
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
- powl
- pow
- _powl
- powf
dev_langs: C++
helpviewer_keywords:
- exponential calculations
- powl function
- _powl function
- exponentiation
- powers, calculating
- calculating exponentials
- powf function
- pow function
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 16a0d7beefff97eca04e5f94ab720cda4728935f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="pow-powf-powl"></a>pow、powf、powl
`x` の `y` 乗を計算します。  
  
## <a name="syntax"></a>構文  
  
```  
double pow(  
   double x,  
   double y   
);  
double pow(  
   double x,  
   int y  
);  // C++ only  
float pow(  
   float x,  
   float y   
);  // C++ only  
float pow(  
   float x,  
   int y  
);  // C++ only  
long double pow(  
   long double x,  
   long double y  
);  // C++ only  
long double pow(  
   long double x,  
   int y  
);  // C++ only  
float powf(  
   float x,  
   float y   
);  
long double powl(  
   long double x,  
   long double y  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 底。  
  
 `y`  
 指数。  
  
## <a name="return-value"></a>戻り値  
 `x`<sup>y</sup> の値を返します。 オーバーフローまたはアンダーフロー時に、エラー メッセージは印刷されません。  
  
|x の値と y の値|pow の値を返す|  
|-----------------------|-------------------------|  
|`x` \< > 0 かつ `y` = 0.0|1|  
|`x` = 0.0 かつ `y` = 0.0|1|  
|`x` = 0.0 かつ `y` < 0|INF|  
  
## <a name="remarks"></a>コメント  
 `pow` では、2<sup>64</sup> を超える整数の浮動小数点値 (`1.0E100` など) は認識されません。  
  
 `pow` には、ストリーミング SIMD 拡張機能 (SSE2) を使用して実装されています。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md)」をご覧ください。  
  
 C++ ではオーバーロードが可能であるため、`pow` のさまざまなオーバーロードを呼び出すことができます。 C プログラムでは、`pow` は常に 2 個の double 値を受け取って、double 値を返します。  
  
 `pow(int, int)` オーバーロードは使用できなくなりました。 このオーバーロードを使用すると、コンパイラは C2668 を生じる場合があります。 この問題を回避するには、最初のパラメーターを `double`、`float`、または `long double` にキャストします。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`pow`、`powf`、`powl`|\<math.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_pow.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.0, y = 3.0, z;  
  
   z = pow( x, y );  
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );  
}  
```  
  
## <a name="output"></a>出力  
  
```  
2.0 to the power of 3.0 is 8.0  
```  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [exp、expf、策の説明](../../c-runtime-library/reference/exp-expf.md)   
 [log、logf、log10、log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [sqrt、sqrtf、sqrtl](../../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)   
 [_CIpow](../../c-runtime-library/cipow.md)