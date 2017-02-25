---
title: "hypot、hypotf、hypotl、_hypot、_hypotf、_hypotl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_hypotf"
  - "hypot"
  - "hypotf"
  - "_hypot"
  - "_hypotl"
  - "hypotl"
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
  - "hypotf"
  - "hypotl"
  - "_hypotl"
  - "hypot"
  - "_hypot"
  - "_hypotf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_hypot 関数"
  - "計算 (直角三角形の斜辺を)"
  - "hypot 関数"
  - "直角三角形の斜辺の計算"
  - "hypotf 関数"
  - "hypotl 関数"
  - "三角形, 計算 (直角三角形の斜辺を)"
ms.assetid: 6a13887f-bd53-43fc-9d77-5b42d6e49925
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# hypot、hypotf、hypotl、_hypot、_hypotf、_hypotl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

斜辺を計算します。  
  
## 構文  
  
```  
double hypot(   
   double x,  
   double y   
);  
float hypotf(   
   float x,  
   float y   
);  
long double hypotl(  
   long double x,  
   long double y  
);  
double _hypot(   
   double x,  
   double y   
);  
float _hypotf(   
   float x,  
   float y   
);  
long double _hypotl(  
   long double x,  
   long double y  
);  
```  
  
#### パラメーター  
 `x`, `y`  
 浮動小数点値。  
  
## 戻り値  
 成功した場合、`hypot` は斜辺の長さを返します。オーバーフローについては、`hypot` は INF \(無限\) を返し、`errno` 変数は `ERANGE` に設定されます。  `_matherr` を使用して、エラー処理を修正できます。  
  
 リターン コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `hypot` 関数は、`x` と `y` の 2 辺の長さが指定された直角三角形の斜辺の長さを計算します \(つまり、`x`<sup>2</sup> \+ `y`<sup>2</sup> の平方根\)。  
  
 以前の標準との互換性のために、先頭にアンダースコアがある関数のバージョンが用意されています。  これらの動作は、先頭にアンダースコアがないバージョンと同じです。  新しいコードには、先頭にアンダースコアがないバージョンを使用することをお勧めします。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`hypot`, `hypotf`, `hypotl`, `_hypot`, `_hypotf`, `_hypotl`|\<math.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_hypot.c  
// This program prints the hypotenuse of a right triangle.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 3.0, y = 4.0;  
  
   printf( "If a right triangle has sides %2.1f and %2.1f, "  
           "its hypotenuse is %2.1f\n", x, y, _hypot( x, y ) );  
}  
```  
  
  **直角三角形の二辺が 3.0 と 4.0 の場合、斜辺は 5.0 です**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [\_cabs](../Topic/_cabs.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)