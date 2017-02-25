---
title: "frexp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "frexp"
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
  - "frexp"
  - "_frexpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_frexpl 関数"
  - "指数, 浮動小数点数"
  - "浮動小数点関数, 仮数と指数"
  - "frexp 関数"
  - "frexpl 関数"
  - "仮数部, 浮動小数点変数"
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# frexp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点数の仮数と指数を取得します。  
  
## 構文  
  
```  
double frexp(  
   double x,  
   int *expptr   
);  
float frexp(  
   float x,  
   int * expptr  
);  // C++ only  
long double frexp(  
   long double x,  
   int * expptr  
);  // C++ only  
```  
  
#### パラメーター  
 `x`  
 浮動小数点値。  
  
 `expptr`  
 格納された指数の整数へのポインター。  
  
## 戻り値  
 `frexp` は 仮数を返します。  `x` が 0 の場合、仮数と指数部の両方の関数の戻り値 0。  `expptr` が `NULL`の場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)で呼び出されます。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、0 を返します。  
  
## 解説  
 `frexp` 関数は仮数 \(`m`\) に `m` の絶対値が 0.5 以上のおよび 1.0 未満、`x` \= `m`\*2.破棄します。浮動小数点値 \(`x`\) と指数 \(`n`\) が。<sup>n</sup> `n` 整数の指数は `expptr`が指す位置に格納します。  
  
 C\+\+ ではオーバーロードが可能であるため、`frexp` のオーバーロードを呼び出すことができます。  C プログラムでは、`frexp` .は Double と整数を受け取り、常に Double を返します。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`frexp`|\<math.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_frexp.c  
// This program calculates frexp( 16.4, &n )  
// then displays y and n.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y;  
   int n;  
  
   x = 16.4;  
   y = frexp( x, &n );  
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );  
}  
```  
  
  **frexp \(16.400000\)、&n \= 0.512500、n \= 5**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [modf、modff、modfl](../../c-runtime-library/reference/modf-modff-modfl.md)