---
title: "コンパイラの警告 (レベル 2) C4146 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4146"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4146"
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラの警告 (レベル 2) C4146
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

符号付きの値を代入する変数は、符号付き型にキャストしなければなりません。  
  
 符号なしの型が保持できるのは負でない値だけであるため、通常、単項マイナス \(否定\) は符号なしの型に使用しても意味をなしません。  オペランドと結果の両方が負でない値になります。  
  
 実際にこの警告が発生するのは、プログラマが最小整数値 \-2147483648 の記述を試みた場合です。  式は次の 2 段階で処理されるため、この値を \-2147483648 として記述することはできません。  
  
1.  数値 2147483648 が評価されます。  この数値は最大整数値 2147483647 より大きいため、2147483648 の型は [int](../../c-language/integer-types.md) ではなく `unsigned int` です。  
  
2.  単項マイナスが値に適用され、符号なしの結果となり、値は 2147483648 となります。  
  
 結果が符号なしの型の場合、予期しない動作が発生する可能性があります。  結果が比較に使用される場合は、符号なしの比較を使用できます。たとえば、他方のオペランドが `int` の場合です。  このため、次のサンプル プログラムでは 1 行だけが出力されます。  
  
 予期される 2 行目の `1 is greater than the most negative int` は、`((unsigned int)1) > 2147483648`  が false であるため出力されません。  
  
 C4146 は、limits.h から **signed int** 型を持つ INT\_MIN を使用すると回避できます。  
  
## 使用例  
 次の例では警告 C4146 が生成されます。  
  
```  
// C4146.cpp  
// compile with: /W2  
#include <stdio.h>  
  
void check(int i)   
{  
    if (i > -2147483648)   // C4146  
        printf_s("%d is greater than the most negative int\n", i);  
}  
  
int main()   
{  
    check(-100);  
    check(1);  
}  
```