---
title: "floor、floorf、floorl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "floorf"
  - "floorl"
  - "floor"
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
  - "floor"
  - "floorl"
  - "_floorl"
  - "floorf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "計算 (値の床値を)"
  - "floor 関数"
  - "floorf 関数"
  - "floorl 関数"
ms.assetid: e9955f70-d659-414f-8050-132e13c8ff36
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# floor、floorf、floorl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

値の切り下げを計算します。  
  
## 構文  
  
```  
double floor(  
   double x  
);  
float floor(  
   float x   
); // C++ only  
long double floor(  
   long double x  
); // C++ only  
float floorf(  
   float x  
);  
long double floorl(  
   long double x  
);  
```  
  
#### パラメーター  
 `x`  
 浮動小数点値。  
  
## 戻り値  
 `floor` 関数は `x` 以下の最も大きい整数を表す浮動小数点値を返します。  エラーの戻り値はありません。  
  
|入力|SEH 例外|Matherr 例外|  
|--------|------------|----------------|  
|± QNAN、IND|なし|\_DOMAIN|  
  
 `floor` には、ストリーミング SIMD 拡張機能 \(SSE2\) を使用して実装されています。  SSE2 実装の使い方の詳細および制約については、「[\_set\_SSE2\_enable](../Topic/_set_SSE2_enable.md)」を参照してください。  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`float` および `long double` の値を受け取って返す `floor` のオーバーロードを呼び出すことができます。  C プログラムでは、`floor` は常に `double` を受け取って返します。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`floor`, `floorf`, `floorl`|\<math.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_floor.c  
// This example displays the largest integers  
// less than or equal to the floating-point values 2.8  
// and -2.8. It then shows the smallest integers greater  
// than or equal to 2.8 and -2.8.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double y;  
  
   y = floor( 2.8 );  
   printf( "The floor of 2.8 is %f\n", y );  
   y = floor( -2.8 );  
   printf( "The floor of -2.8 is %f\n", y );  
  
   y = ceil( 2.8 );  
   printf( "The ceil of 2.8 is %f\n", y );  
   y = ceil( -2.8 );  
   printf( "The ceil of -2.8 is %f\n", y );  
}  
```  
  
  **2.8 の切り捨て値は 2.000000**  
**\-2.8 の切り捨て値は \-3.000000**  
**2.8 の切り上げ値は 3.000000**  
**\-2.8 の切り上げ値は \-2.000000**   
## 同等の .NET Framework 関数  
 [System::Math::Floor](https://msdn.microsoft.com/en-us/library/system.math.floor.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ceil、ceilf、ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [round、roundf、roundl](../../c-runtime-library/reference/round-roundf-roundl.md)   
 [fmod、fmodf](../Topic/fmod,%20fmodf.md)