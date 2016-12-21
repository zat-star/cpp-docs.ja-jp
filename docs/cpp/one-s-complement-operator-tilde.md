---
title: "1 の補数演算子: ~ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "~"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~ 演算子, 構文"
  - "ビットごとの補数演算子"
  - "compl 演算子"
  - "1 の補数演算子"
  - "ティルダ (~) 1 の補数演算子"
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1 の補数演算子: ~
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
~ cast-expression  
```  
  
## 解説  
 1 の補数演算子 \(`~`\) は、"ビット補数" 演算子とも呼ばれ、オペランドのビットごとの 1 の補数を生成します。  つまり、オペランドの各ビットが 1 である場合の結果は、0 になります。  逆に、オペランドの各ビットが 0 である場合の結果は、1 になります。  1 の補数演算子のオペランドは、整数型である必要があります。  
  
## ~ の演算子キーワード  
 `compl` 演算子は `~` の代替表現です。  プログラムで `compl` 演算子にアクセスするには、2 つの方法があります。1 つはヘッダー ファイル `iso646.h` を含める方法で、もう 1 つは [\/Za](../build/reference/za-ze-disable-language-extensions.md) を使用してコンパイルする方法です。  
  
## 使用例  
  
```  
// expre_One_Complement_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main () {  
   unsigned short y = 0xFFFF;  
   cout << hex << y << endl;  
   y = ~y;   // Take one's complement  
   cout << hex << y << endl;  
}  
```  
  
 この例では、`y` に割り当てられた新しい値は、符号なしの値 0xFFFF の 1 の補数、つまり 0x0000 です。  
  
 整数の上位変換は、整数オペランドに対して実行され、結果の型は、そのオペランドが昇格される型になります。  上位変換のしくみの詳細については、「[整数の上位変換](../misc/integral-promotions.md)」を参照してください。  
  
## 参照  
 [単項演算子を含む式](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [単項算術演算子](../c-language/unary-arithmetic-operators.md)