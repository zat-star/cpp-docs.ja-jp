---
title: "cbrt、cbrtf、cbrtl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "cbrt"
  - "cbrtf"
  - "cbrtl"
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
  - "cbrtl"
  - "cbrt"
  - "cbrtf"
dev_langs: 
  - "C++"
ms.assetid: ab51d916-3db2-4beb-b46a-28b4062cd33f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# cbrt、cbrtf、cbrtl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

立方根を計算します。  
  
## 構文  
  
```  
double cbrt(    double x  ); float cbrt(    float x  );  // C++ only long double cbrt(    long double x );  // C++ only float cbrtf(    float x  ); long double cbrtl(    long double x );  
```  
  
#### パラメーター  
 `x`  
 浮動小数点値  
  
## 戻り値  
 `cbrt` 関数は、`x` の立方根を返します。  
  
|入力|SEH 例外|`_matherr` 例外|  
|--------|------------|-------------------|  
|± ∞、QNAN、IND|none|none|  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`float` または `long double` 型を受け取る `cbrt` のオーバーロードを呼び出すことができます。  C プログラムでは、`cbrt` は常に `double` を受け取って返します。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`cbrt`, `cbrtf`, `cbrtl`|\<math.h\>|\<cmath\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```c  
// crt_cbrt.c  
// Compile using: cl /W4 crt_cbrt.c  
// This program calculates a cube root.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double question = -64.64;  
   double answer;  
  
   answer = cbrt(question);  
   printf("The cube root of %.2f is %.6f\n", question, answer);  
}  
```  
  
  **\-64.64 の立方根は \-4.013289 です。**   
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [exp、expf](../../c-runtime-library/reference/exp-expf.md)   
 [log、logf、log10、log10f](../Topic/log,%20logf,%20log10,%20log10f.md)   
 [pow、powf、powl](../Topic/pow,%20powf,%20powl.md)