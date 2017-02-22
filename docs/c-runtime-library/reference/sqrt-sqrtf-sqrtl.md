---
title: "sqrt、sqrtf、sqrtl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "sqrtl"
  - "sqrtf"
  - "sqrt"
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
  - "sqrt"
  - "sqrtf"
  - "_sqrtl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_sqrtl 関数"
  - "計算 (平方根を)"
  - "sqrt 関数"
  - "sqrtf 関数"
  - "sqrtl 関数"
  - "平方根, 計算"
ms.assetid: 2ba9467b-f172-41dc-8f10-b86f68fa813c
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# sqrt、sqrtf、sqrtl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

平方根を計算します。  
  
## 構文  
  
```  
double sqrt(    double x  ); float sqrt(    float x  );  // C++ only long double sqrt(    long double x );  // C++ only float sqrtf(    float x  ); long double sqrtl(    long double x  );  
```  
  
#### パラメーター  
 `x`  
 負でない浮動小数点値  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`float` または `long double` 型を受け取る `sqrt` のオーバーロードを呼び出すことができます。  C プログラムでは、`sqrt` は常に `double` を受け取って返します。  
  
## 戻り値  
 `sqrt` 関数は、`x` の平方根を返します。  既定では、`x` が負の場合、`sqrt` は不定値 NaN を返します。  
  
|入力|SEH 例外|`_matherr` 例外|  
|--------|------------|-------------------|  
|± QNAN、IND|none|\_DOMAIN|  
|\- ∞|none|\_DOMAIN|  
|x\<0|none|\_DOMAIN|  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`sqrt`, `sqrtf`, `sqrtl`|\<math.h\>|\<cmath\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_sqrt.c  
// This program calculates a square root.  
  
#include <math.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   double question = 45.35, answer;  
   answer = sqrt( question );  
   if( question < 0 )  
      printf( "Error: sqrt returns %f\n", answer );  
   else  
      printf( "The square root of %.2f is %.2f\n", question, answer );  
}  
```  
  
  **45.35 の平方根は 6.73 です**   
## 同等の .NET Framework 関数  
 [System::Math::Sqrt](https://msdn.microsoft.com/en-us/library/system.math.sqrt.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [exp、expf](../../c-runtime-library/reference/exp-expf.md)   
 [log、logf、log10、log10f](../Topic/log,%20logf,%20log10,%20log10f.md)   
 [pow、powf、powl](../Topic/pow,%20powf,%20powl.md)   
 [\_CIsqrt](../../c-runtime-library/cisqrt.md)