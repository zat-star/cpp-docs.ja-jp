---
title: "exp、expf | Microsoft Docs"
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
  - "expf"
  - "exp"
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
  - "_expl"
  - "expf"
  - "exp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "指数演算"
  - "expf 関数"
  - "計算 (指数を)"
  - "exp 関数"
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# exp、expf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指数部を計算します。  
  
## 構文  
  
```  
double exp(   
   double x  
);  
float exp(  
   float x  
);  // C++ only  
long double exp(  
   long double x  
);  // C++ only  
float expf(   
   float x  
);  
```  
  
#### パラメーター  
 `x`  
 浮動小数点値。  
  
## 戻り値  
 正常終了した場合 `exp` 関数の戻り値は浮動小数点パラメーター、`x`指数の値。  つまり、結果、e を自然対数の底 `x`へ e の累乗です。  のオーバーフロー、関数の戻り値 \(INF 無限\) と、`exp` アンダーフローの場合は 0 を返します。  
  
|入力|SEH 例外|Matherr 例外|  
|--------|------------|----------------|  
|± QNAN、IND|なし。|\_DOMAIN|  
|± ∞|INVALID|\_DOMAIN|  
|X ≥ 7.097827e\+002|INEXACT\+OVERFLOW|OVERFLOW|  
|X ≤ \-7.083964e\+002|INEXACT\+UNDERFLOW|アンダーフロー|  
  
 `exp` に ストリーミング SIMD 拡張機能 2 \(SSE2\) を使用して実装できます。  SSE2 実装を情報と使用条件の [\_set\_SSE2\_enable](../Topic/_set_SSE2_enable.md) を参照してください。  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`exp` のオーバーロードを呼び出すことができます。  C プログラムでは、`exp` は常に double を受け取って返します。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`exp`, `expf`|\<math.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_exp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.302585093, y;  
  
   y = exp( x );  
   printf( "exp( %f ) = %f\n", x, y );  
}  
```  
  
  **exp. \(2.302585\) \= 10.000000**   
## 同等の .NET Framework 関数  
 [System::Math::Exp](https://msdn.microsoft.com/en-us/library/system.math.exp.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [log、logf、log10、log10f](../Topic/log,%20logf,%20log10,%20log10f.md)   
 [\_CIexp](../Topic/_CIexp.md)