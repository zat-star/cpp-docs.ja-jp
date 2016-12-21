---
title: "acosh、acoshf、acoshl | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "acoshf"
  - "acosh"
  - "acoshl"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "acosh"
  - "acoshf"
  - "acoshl"
  - "math/acosh"
  - "math/acoshf"
  - "math/acoshl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "acoshf 関数"
  - "acosh 関数"
  - "acoshl 関数"
ms.assetid: 6985c4d7-9e2a-44ce-9a9b-5a43015f15f7
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# acosh、acoshf、acoshl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

逆ハイパーボリック コサインを計算します。  
  
## 構文  
  
```  
double acosh(  
   double x   
);  
float acosh(  
   float x   
);  // C++ only  
long double acosh(  
   long double x  
);  // C++ only  
float acoshf(  
   float x   
);  
long double acoshl(  
   long double x  
);  
```  
  
#### パラメーター  
 `x`  
 浮動小数点値。  
  
## 戻り値  
 `acosh` 関数は `x` の逆ハイパーボリック コサイン \(アーク ハイパーボリック コサイン\) を返します。 これらの関数はドメイン `x` ≥ 1 で有効です。`x` が 1 未満の場合、`errno` が `EDOM` に設定され、結果は簡易な NaN です。`x` が簡易な NaN、不定値、または無限大の場合は、同じ値が返されます。  
  
|入力|SEH 例外|`_matherr` 例外|  
|--------|------------|-------------------|  
|± QNAN、IND、INF|none|none|  
|x \< 1|none|none|  
  
## 解説  
 C\+\+ を使用する場合、`float` または `long double` の値を受け取って返す `acosh` のオーバーロードを呼び出すことができます。 C プログラムでは、`acosh` は常に `double` を受け取って返します。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`acosh`、`acoshf`、`acoshl`|\<math.h\>|\<cmath\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 使用例  
  
```c  
// crt_acosh.c  
// Compile by using: cl /W4 crt_acosh.c  
// This program displays the hyperbolic cosine of pi / 4  
// and the arc hyperbolic cosine of the result.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double pi = 3.1415926535;  
   double x, y;  
  
   x = cosh( pi / 4 );  
   y = acosh( x );  
   printf( "cosh( %f ) = %f\n", pi/4, x );  
   printf( "acosh( %f ) = %f\n", x, y );  
}  
```  
  
```Output  
cosh (0.785398) = 1.324609 acosh (1.324609) = 0.785398  
```  
  
## 同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [Long Double 型](../../misc/long-double.md)   
 [cos、cosf、cosl、cosh、coshf、coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [sin、sinf、sinl、sinh、sinhf、sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [asinh、asinhf、asinhl](../../c-runtime-library/reference/asinh-asinhf-asinhl.md)   
 [tan、tanf、tanl、tanh、tanhf、tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [atanh、atanhf、atanhl](../Topic/atanh,%20atanhf,%20atanhl.md)   
 [\_CItan](../../c-runtime-library/citan.md)