---
title: "浮動小数点数の精度の低下 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DBL_EPSILON 定数"
  - "浮動小数点数, 精度"
  - "FLT_EPSILON 定数"
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 浮動小数点数の精度の低下
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

通常、浮動小数点 10 進値には正確な 2 進表現がありません。  これは、CPU による浮動小数点データの表現方法に起因するものです。  このため、精度が減少したり、浮動小数点演算で予期しない結果になることがあります。  
  
 この動作は、次のいずれかの原因によって生じます。  
  
-   10 進数の 2 進表現が正確ではない。  
  
-   使用した数値の型が一致しない \(たとえば、float 型と double 型の混在\)。  
  
 これを解決するために多くのプログラマは、必要な値より大きい、またはより小さい値を確保するか、精度を維持する 2 進化 10 進数 \(BCD: Binary Coded Decimal\) ライブラリを入手して使用します。  
  
 浮動小数点値の 2 進表現は、浮動小数点計算の有効桁数および精度に影響を与えます。  Microsoft Visual C\+\+ では、[IEEE 浮動小数点形式](../../build/reference/ieee-floating-point-representation.md)を使用しています。  
  
## 使用例  
  
```  
// Floating-point_number_precision.c  
// Compile options needed: none. Value of c is printed with a decimal   
// point precision of 10 and 6 (printf rounded value by default) to   
// show the difference  
#include <stdio.h>  
  
#define EPSILON 0.0001   // Define your own tolerance  
#define FLOAT_EQ(x,v) (((v - EPSILON) < x) && (x <( v + EPSILON)))  
  
int main() {  
   float a, b, c;  
  
   a = 1.345f;  
   b = 1.123f;  
   c = a + b;  
   // if (FLOAT_EQ(c, 2.468)) // Remove comment for correct result  
   if (c == 2.468)            // Comment this line for correct result  
      printf_s("They are equal.\n");  
   else  
      printf_s("They are not equal! The value of c is %13.10f "  
                "or %f",c,c);  
}  
```  
  
  **They are not equal\!  The value of c is  2.4679999352 or 2.468000**    
## コメント  
 EPSILON には、1.192092896e\-07F として定義された float 用の定数 FLT\_EPSILON か、または 2.2204460492503131e\-016 として定義された double 用の定数 DBL\_EPSILON を使用できます。  これらの定数を使用するには、float.h をインクルードする必要があります。  これらの定数は、x\+1.0 が 1.0 に等しくならないような正の最小の数値 x として定義されています。  これは極度に小さい数値なので、大きな数値を含む計算を行う場合は、ユーザー定義の許容値を使用する必要があります。  
  
## 参照  
 [コードの最適化](../../build/reference/optimizing-your-code.md)