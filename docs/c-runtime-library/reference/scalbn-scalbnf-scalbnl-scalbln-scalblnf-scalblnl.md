---
title: "scalbn、scalbnf、scalbnl、scalbln、scalblnf、scalblnl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "scalblnl"
  - "scalbnl"
  - "scalbnf"
  - "scalblnf"
  - "scalbn"
  - "scalbln"
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
  - "scalblnf"
  - "scalbnl"
  - "scalblnl"
  - "scalbln"
  - "scalbn"
  - "scalbnf"
dev_langs: 
  - "C++"
ms.assetid: df2f1543-8e39-4af4-a5cf-29307e64807d
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# scalbn、scalbnf、scalbnl、scalbln、scalblnf、scalblnl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点数に整数である FLT\_RADIX の累乗を乗算します。  
  
## 構文  
  
```  
double scalbn(    double x,    int exp  ); float scalbn(    float x,    int exp );  // C++ only long double scalbn(    long double x,    int exp );  // C++ only  float scalbnf(    float x,    int exp );  long double scalbnl(    long double x,    int exp ); double scalbln(    double x,    long exp  ); float scalbln(    float x,    long exp );  // C++ only long double scalbln(    long double x,    long exp );  // C++ only  float scalblnf(    float x,    long exp );  long double scalblnl(    long double x,    long exp );  
```  
  
#### パラメーター  
 `x`  
 浮動小数点値。  
  
 `exp`  
 整数の指数。  
  
## 戻り値  
 `scalbn` 関数は、成功した場合、`x` \* `FLT_RADIX`<sup>exp</sup> の値を返します。  オーバーフローが発生すると \(`x` の符号に応じて\)、`scalbn` は \+\/\- `HUGE_VAL` を返します。`errno` の値は `ERANGE` に設定されます。  
  
 `errno` および可能なエラーの戻り値の詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `FLT_RADIX` は、\<float.h\> でネイティブ浮動小数点基数として定義されます。バイナリ システムでは、その値は 2 であり、`scalbn` は [ldexp](../../c-runtime-library/reference/ldexp.md) と等価です。  
  
 C\+\+ ではオーバーロードが可能であるため、`float` 型または `long double` 型を受け取って返す `scalbn` と `scalbln` のオーバーロードを呼び出すことができます。  C プログラムでは、`scalbn` は常に `double` および `int` を受け取って `double` を返し、`scalbln` は常に `double` および `long` を受け取って `double` を返します。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`scalbn`, `scalbnf`, `scalbnl`, `scalbln`, `scalblnf`, `scalblnl`|\<math.h\>|\<cmath\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_scalbn.c  
// Compile using: cl /W4 crt_scalbn.c  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 6.4, y;  
   int p = 3;  
  
   y = scalbn( x, p );  
   printf( "%2.1f times FLT_RADIX to the power of %d is %2.1f\n", x, p, y );  
}  
```  
  
## 出力  
  
```  
6.4 times FLT_RADIX to the power of 3 is 51.2  
```  
  
## 同等の .NET Framework 関数  
 [System::Math::Pow](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [modf、modff、modfl](../../c-runtime-library/reference/modf-modff-modfl.md)