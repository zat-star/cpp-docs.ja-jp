---
title: "rint、rintf、rintl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "rintf"
  - "rintl"
  - "rint"
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
  - "rintf"
  - "rintl"
  - "rint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rintf 関数"
  - "rint 関数"
  - "rintl 関数"
ms.assetid: 312ae3e6-278c-459a-9393-11b8f87d9184
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# rint、rintf、rintl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点値を浮動小数点形式で最も近い整数に丸めます。  
  
## 構文  
  
```  
double rint( double x ); float rint( float x );  // C++ only long double rint( long double x );  // C++ only float rintf( float x );  long double rintl( long double x );    
```  
  
#### パラメーター  
 `x`  
 丸める浮動小数点値。  
  
## 戻り値  
 `rint` 関数は `x` に最も近い整数を表す浮動小数点値を返します。  `nearbyint` 関数と同様に、中間の値は、浮動小数点丸めモードの現在の設定に従って丸められます。  `nearbyint` 関数と異なり、`rint` 関数では、結果の値が引数と異なる場合に `FE_INEXACT` 浮動小数点例外が発生する場合があります。  エラーの戻り値はありません。  
  
|入力|SEH 例外|`_matherr` 例外|  
|--------|------------|-------------------|  
|± ∞、QNAN、IND|none|none|  
|非正規化数|EXCEPTION\_FLT\_UNDERFLOW|none|  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`float` および `long double` の値を受け取って返す `rint` のオーバーロードを呼び出すことができます。  C プログラムでは、`rint` は常に `double` を受け取って返します。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`rint`, `rintf`, `rintl`|\<math.h\>|\<cmath\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_rint.c  
// Build with: cl /W3 /Tc crt_rint.c  
// This example displays the rounded results of  
// the floating-point values 2.499999, -2.499999,   
// 2.8, -2.8, 2.5 and -2.5.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.499999;  
   float y = 2.8f;  
   long double z = 2.5;  
  
   printf("rint(%f) is %.0f\n", x, rint (x));  
   printf("rint(%f) is %.0f\n", -x, rint (-x));  
   printf("rintf(%f) is %.0f\n", y, rintf(y));  
   printf("rintf(%f) is %.0f\n", -y, rintf(-y));  
   printf("rintl(%Lf) is %.0Lf\n", z, rintl(z));  
   printf("rintl(%Lf) is %.0Lf\n", -z, rintl(-z));  
}  
```  
  
  **rint\(2.499999\) is 2**  
**rint\(\-2.499999\) is \-2**  
**rintf\(2.800000\) is 3**  
**rintf\(\-2.800000\) is \-3**  
**rintl\(2.500000\) is 3**  
**rintl\(\-2.500000\) is \-3**   
## 同等の .NET Framework 関数  
 [System::Math::Round](https://msdn.microsoft.com/en-us/library/system.math.round.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ceil、ceilf、ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [floor、floorf、floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod、fmodf](../Topic/fmod,%20fmodf.md)   
 [lrint、lrintf、lrintl、llrint、llrintf、llrintl](http://msdn.microsoft.com/ja-jp/312fd869-a9c0-4107-bb23-ab8299d04385)   
 [lround、lroundf、lroundl、llround、llroundf、llroundl](../../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)   
 [nearbyint、nearbyintf、nearbyintl](http://msdn.microsoft.com/ja-jp/15111e73-331d-41d1-81b7-3e10df894848)   
 [rint](../../c-runtime-library/reference/rint-rintf-rintl.md)