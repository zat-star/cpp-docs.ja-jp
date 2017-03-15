---
title: "modf、modff、modfl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "modff"
  - "modf"
  - "modfl"
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
  - "modff"
  - "_modfl"
  - "modf"
  - "modfl"
  - "math/modf"
  - "math/modff"
  - "math/modfl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modf 関数"
  - "modff 関数"
  - "modfl 関数"
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# modf、modff、modfl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点値を小数部分と整数部に分割します。  
  
## 構文  
  
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
  
#### パラメーター  
 *x*  
 浮動小数点値。  
  
 `intptr`  
 格納された整数部分へのポインター。  
  
## 戻り値  
 この関数は、符号付き小数部を返します *x*します。 エラーの戻り値はありません。  
  
## 解説  
 `modf` 関数が浮動小数点値を分割 `x` に小数部と整数部と同じ符号を持つ `x`です。 符号付き小数部 `x` が返されます。 浮動小数点値として整数部分が格納されています。 `intptr.`  
  
 `modf` には、ストリーミング SIMD 拡張機能 \(SSE2\) を使用して実装されています。 参照してください [\_set\_SSE2\_enable](../Topic/_set_SSE2_enable.md) と SSE2 の実装の使用に関する制限についてです。  
  
 C\+\+ では、オーバー ロードのオーバー ロードを呼び出すことができますので `modf` を受け取り、返します `float` または `long double` パラメーター。 C プログラムでは、`modf` は常に 2 個の double 値を受け取って、double 値を返します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`modf`、`modff`、`modfl`|C: \< math.h \><br /><br /> C\+\+ の場合: \< cmath \> または \< math.h \>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
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
  
## 出力  
  
```  
For -14.876543, the fraction is -0.876543 and the integer is -14  
```  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)