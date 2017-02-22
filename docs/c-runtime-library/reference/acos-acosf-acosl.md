---
title: "acos、acosf、acosl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "acosf"
  - "acos"
  - "acosl"
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
  - "acos"
  - "acosl"
  - "acosf"
  - "math/acosf"
  - "math/acosl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "acos 関数"
  - "acosf 関数"
  - "acosl 関数"
  - "arccosine 関数"
  - "三角関数"
ms.assetid: 00b89c48-8faf-4824-aa95-fa4349a4975d
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# acos、acosf、acosl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アークコサインを計算します。  
  
## 構文  
  
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
  
#### パラメーター  
 `x`  
 アークコサイン \(逆コサイン\) を計算する –1 ～ 1 の間の値。  
  
## 戻り値  
 `acos` 関数は、0 ～ π ラジアンの範囲で `x` のアークコサインを返します。  
  
 既定では、`x` が –1 未満または 1 よりも大きい場合、`acos` は不定値を返します。  
  
|入力|SEH 例外|Matherr 例外|  
|--------|------------|----------------|  
|± ∞|`INVALID`|`_DOMAIN`|  
|± QNAN、IND|なし|`_DOMAIN`|  
|&#124;x&#124; \> 1|`INVALID`|`_DOMAIN`|  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`float` 型および `long double` 型を受け取って返す `acos` のオーバーロードを呼び出すことができます。  C プログラムでは、`acos` は常に `double` を受け取って返します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|----------|------------|---------------|  
|`acos`, `acosf`, `acosl`|\<math.h\>|\<errno.h\>|  
  
## 使用例  
 このプログラムは、\-1 ～ 1 の範囲の値の入力を求めます。  入力値がこの範囲外の場合、`_DOMAIN` エラー メッセージを生成します。  有効な値が入力された場合、プログラムはその値のアークサインとアークコサインを出力します。  
  
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
  
  **0.000000 のアークサイン \= 0.000000**  
**0.000000 のアークコサイン \= 1.570796**   
## 同等の .NET Framework 関数  
 [System::Math::Acos](https://msdn.microsoft.com/en-us/library/system.math.acos.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [asin、asinf、asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan、atanf、atanl、atan2、atan2f、atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos、cosf、cosl、cosh、coshf、coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin、sinf、sinl、sinh、sinhf、sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan、tanf、tanl、tanh、tanhf、tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)