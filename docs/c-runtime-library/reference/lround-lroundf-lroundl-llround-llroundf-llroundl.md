---
title: "lround、lroundf、lroundl、llround、llroundf、llroundl | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "llround"
  - "llroundf"
  - "llroundl"
  - "lroundf"
  - "lround"
  - "lroundl"
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
  - "lround"
  - "lroundl"
  - "llroundl"
  - "llround"
  - "lroundf"
  - "llroundf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "llround 関数"
  - "llroundf 関数"
  - "llroundl 関数"
  - "lround 関数"
  - "lroundf 関数"
  - "lroundl 関数"
ms.assetid: cfb88a35-54c6-469f-85af-f7d695dcfdd8
caps.latest.revision: 6
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# lround、lroundf、lroundl、llround、llroundf、llroundl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点値を最も近い整数に丸めます。  
  
## 構文  
  
```  
long lround(   
   double x   
);  
long lround(  
   float x  
);  // C++ only  
long lround(  
   long double x  
);  // C++ only  
long lroundf(  
   float x  
);  
long lroundl(  
   long double x  
);  
long long llround(   
   double x   
);  
long long llround(  
   float x  
);  // C++ only  
long long llround(  
   long double x  
);  // C++ only  
long long llroundf(  
   float x  
);  
long long llroundl(  
   long double x  
);  
```  
  
#### パラメーター  
 `x`  
 丸める浮動小数点値。  
  
## 戻り値  
 `lround` 関数、および `llround` 関数は、`x` に最も近い `long` 整数、または `long long` 整数を返します。  中間の値は、浮動小数点丸めモードの設定にかかわらず、ゼロから離れる方向に丸められます。  エラーの戻り値はありません。  
  
|入力|SEH 例外|Matherr 例外|  
|--------|------------|----------------|  
|± `QNAN`, `IND`|なし|`_DOMAIN`|  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`float` や `long double` の値を受け取って返す、`lround` および `llround` のオーバーロードを呼び出すことができます。  C プログラムでは、`lround` および `llround` は常に `double` を受け取って返します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`lround`, `lroundf`, `lroundl`, `llround`, `llroundf`, `llroundl`|\<math.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_lround.c  
// Build with: cl /W3 /Tc crt_lround.c  
// This example displays the rounded results of  
// the floating-point values 2.499999, -2.499999,   
// 2.8, -2.8, 3.5 and -3.5.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.499999;  
   float y = 2.8f;  
   long double z = 3.5;  
  
   printf("lround(%f) is %d\n", x, lround(x));  
   printf("lround(%f) is %d\n", -x, lround(-x));  
   printf("lroundf(%f) is %d\n", y, lroundf(y));  
   printf("lroundf(%f) is %d\n", -y, lroundf(-y));  
   printf("lroundl(%Lf) is %d\n", z, lroundl(z));  
   printf("lroundl(%Lf) is %d\n", -z, lroundl(-z));  
}  
```  
  
  **lround\(2.499999\) は 2**  
**lround\(\-2.499999\) は \-2**  
**lroundf\(2.800000\) は 3**  
**lroundf\(\-2.800000\) は \-3**  
**lroundl\(2.500000\) は 4**  
**lroundl\(\-2.500000\) は \-4**   
## 同等の .NET Framework 関数  
 [System::Math::Round](https://msdn.microsoft.com/en-us/library/system.math.round.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ceil、ceilf、ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [floor、floorf、floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod、fmodf](../Topic/fmod,%20fmodf.md)   
 [lrint、lrintf、lrintl、llrint、llrintf、llrintl](http://msdn.microsoft.com/ja-jp/312fd869-a9c0-4107-bb23-ab8299d04385)   
 [round、roundf、roundl](../../c-runtime-library/reference/round-roundf-roundl.md)   
 [nearbyint、nearbyintf、nearbyintl](http://msdn.microsoft.com/ja-jp/15111e73-331d-41d1-81b7-3e10df894848)   
 [rint、rintf、rintl](../../c-runtime-library/reference/rint-rintf-rintl.md)