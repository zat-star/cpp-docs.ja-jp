---
title: "等値演算子: == および != | Microsoft Docs"
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
  - "not_eq"
  - "!="
  - "=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!= 演算子"
  - "== 演算子"
  - "等しいことを示す演算子"
  - "等値演算子"
  - "等値演算子, 構文"
  - "等しくないことを示す演算子"
  - "not_eq 演算子"
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 等値演算子: == および !=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
      expression == expression  
expression != expression  
```  
  
## 解説  
 これらの二項等値演算子はそれぞれオペランドを比較し、等しいか、等しくないかを判別します。  
  
 "等しい" \(`==`\) および "等しくない" \(`!=`\) の等値演算子は関係演算子より優先順位が下ですが、動作は同じです。  これらの演算子の結果は `bool` 型です。  
  
 "等しい" \(`==`\) 演算子は、両方のオペランドの値が同じである場合に **true** \(1\) を返し、それ以外の場合は **false** \(0\) を返します。  "等しくない" \(`!=`\) 演算子は、オペランドの値が異なる場合に **true** を返し、それ以外の場合は **false** を返します。  
  
## \!\= の演算子キーワード  
 `not_eq` 演算子は `!=` の代替表現です。  プログラムで `not_eq` 演算子にアクセスするには、2 つの方法があります。1 つはヘッダー ファイル `iso646.h` を含める方法で、もう 1 つは [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(言語拡張機能を無効にする\) コンパイラ オプションを使用してコンパイルする方法です。  
  
## 使用例  
  
```  
// expre_Equality_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   cout  << boolalpha  
         << "The true expression 3 != 2 yields: "  
         << (3 != 2) << endl  
         << "The false expression 20 == 10 yields: "  
         << (20 == 10) << endl;  
}  
```  
  
 等値演算子は、同じ型のメンバーへのポインターを比較できます。  このような比較では、「[メンバーへのポインター変換](../misc/pointer-to-member-conversions.md)」で説明されているように、ポインターがメンバーに変換されます。  メンバーへのポインターは、0 として評価される定数式と比較することもできます。  
  
## 参照  
 [二項演算子を含む式](../cpp/expressions-with-binary-operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 関係演算子と等値演算子](../c-language/c-relational-and-equality-operators.md)