---
title: "乗算演算子と剰余演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "%"
  - "/"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "% 演算子"
  - "* 演算子"
  - "算術演算子 [C++], 乗算演算子"
  - "除算演算子"
  - "除算演算子, 乗算演算子"
  - "剰余演算子, C+"
  - "乗算演算子 [C++], 乗算演算子"
  - "乗算演算子 [C++]"
  - "演算子 [C++], 乗法"
ms.assetid: b53ea5da-d0b4-40dc-98f3-0aa52d548293
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 乗算演算子と剰余演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
expression * expression   
expression / expression   
expression % expression  
```  
  
## 解説  
 乗算演算子は次のとおりです。  
  
-   乗算 \(**\***\)  
  
-   除算 \(**\/**\)  
  
-   剰余 \(除算の剰余\) \(`%`\)  
  
 これらの二項演算子の結合規則は、左から右方向です。  
  
 乗算演算子は、数値型のオペランドを受け取ります。  剰余演算子 \(`%`\) には、そのオペランドが整数型でなければならないという点で、より厳しい要件があります \(浮動小数点部分の剰余を取得するには、ランタイム関数、[fmod](../Topic/fmod,%20fmodf.md) を使用します\)。「[算術変換](../misc/arithmetic-conversions.md)」で説明されている変換がオペランドに適用され、結果は変換後の型になります。  
  
 乗算演算子は、最初のオペランドを 2 番目のオペランドで乗算した結果を生成します。  
  
 除算演算子は、最初のオペランドを 2 番目のオペランドで除算した結果を生成します。  
  
 剰余演算子は次の式が生成する剰余を提供します。ここで、*e1* は最初のオペランド、*e2* は 2 番目のオペランドです。両方のオペランドは整数型です。*e1* – \(*e1* \/ *e2*\) \* *e2*  
  
 除算または剰余式における 0 での除算は未定義になり、実行時エラーが発生します。  したがって、次の式は未定義の間違った結果を生成します。  
  
```  
i % 0  
f / 0.0  
```  
  
 乗算式、除算式、剰余式への両方のオペランドに同じ符号がある場合、結果は正の値になります。  それ以外の場合、結果は負になります。  剰余演算の符号の結果は実装定義されます。  
  
> [!NOTE]
>  乗算演算子によって実行される変換ではオーバーフロー条件やアンダーフロー条件が提供されないため、乗算演算の結果を変換後のオペランドの型で表すことができない場合、情報が失われる可能性があります。  
  
## Microsoft 固有の仕様 →  
 Microsoft C\+\+ では、剰余式の結果は常に最初のオペランドと同じ符号になります。  
  
## END Microsoft 固有の仕様  
 2 つの整数の計算された除算が正確ではなく、1 つのオペランドだけが負の値の場合、結果は、除算演算で算出された正確な値未満の最大の整数 \(大きさでは、符号を無視します\) になります。  たとえば、–11 \/ 3 の計算値は –3.666666666 です。  整数の除算の結果は \-3 です。  
  
 乗算演算子の間の関係は、識別子 \(*e1* \/ *e2*\) \* *e2* \+ *e1* % *e2* \=\= *e1* によって得られます。  
  
## 使用例  
 次のプログラムは乗算演算子を示します。  切り捨てを避けるため、両方のオペランドが分割の前に `float` 型になるように `10 / 3` のいずれかのオペランドを明示的に `float` 型にキャストする必要があることに注意してください。  
  
```  
// expre_Multiplicative_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   int x = 3, y = 6, z = 10;  
   cout  << "3 * 6 is " << x * y << endl  
         << "6 / 3 is " << y / x << endl  
         << "10 % 3 is " << z % x << endl  
         << "10 / 3 is " << (float) z / x << endl;  
}  
```  
  
## 参照  
 [二項演算子を含む式](../cpp/expressions-with-binary-operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 乗算演算子](../c-language/c-multiplicative-operators.md)