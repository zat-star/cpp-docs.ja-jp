---
title: "exp、expf、策の説明 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- expf
- expl
- exp
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
- _expl
- expf
- expl
- exp
dev_langs: C++
helpviewer_keywords:
- exponential calculations
- expf function
- expl function
- calculating exponentials
- exp function
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0702b99990728bdb732654fdd1eacbefa373dda6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exp-expf-expl"></a>exp、expf、策の説明
指数を計算します。  
  
## <a name="syntax"></a>構文  
  
```  
double exp(   
   double x  
);  
float exp(  
   float x  
);  // C++ only  
long double exp(  
   long double x  
);  // C++ only  
float expf(   
   float x  
);  
long double expl(  
   long double x  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `x`  
 浮動小数点値を exponentiate 自然対数の底*e*でします。  
  
## <a name="return-value"></a>戻り値  
 `exp`関数は、浮動小数点パラメーターの指数値を返す*x*正常終了した場合、します。 その結果は*e*<sup>*x*</sup>ここで、 *e*自然対数の底です。 INF (無限) 関数の戻り値のオーバーフローおよびアンダー フロー、 `exp` 0 を返します。  
  
|入力|SEH 例外|Matherr 例外|  
|-----------|-------------------|-----------------------|  
|± 簡易な NaN、不定|なし|_DOMAIN|  
|± 無限大|INVALID|_DOMAIN|  
|x ≥ 7.097827e+002|INEXACT+OVERFLOW|OVERFLOW|  
|X ≤ -7.083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|  
  
 `exp`関数には、ストリーミング SIMD 拡張命令 2 (SSE2) を使用する実装。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 C++ では、オーバー ロードのオーバー ロードを呼び出すことができますので`exp`を受け取る、 **float**または**long double**引数。 C プログラムでは、`exp`常に受け取りを返す、**二重**です。  
  
## <a name="requirements"></a>必要条件  
  
|関数|必須の C ヘッダー|必須の C++ ヘッダー|  
|--------------|---------------------|---|  
|`exp`, `expf`|\<math.h>|\<cmath> または \<math.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_exp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.302585093, y;  
  
   y = exp( x );  
   printf( "exp( %f ) = %f\n", x, y );  
}  
```  
  
```Output  
exp( 2.302585 ) = 10.000000  
```  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [log、logf、log10、log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [_CIexp](../../c-runtime-library/ciexp.md)