---
title: "論理 OR 演算子: || | Microsoft Docs"
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
  - "||"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "|| 演算子"
  - "論理 OR 演算子"
  - "OR 演算子"
  - "OR 演算子, 論理"
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 論理 OR 演算子: ||
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
logical-or-expression   
||  
 logical-and-expression  
  
```  
  
## 解説  
 論理 OR 演算子 \(`||`\) は、どちらかのオペランドまたは両方のオペランドが **true** の場合はブール値 **true** を返し、それ以外の場合は **false** を返します。  オペランドは、評価前に `bool` 型に暗黙的に変換され、結果は `bool` 型です。  論理 OR の結合規則は左から右です。  
  
 論理 OR 演算子のオペランドが同じ型である必要はありませんが、整数型またはポインター型である必要があります。  オペランドは一般に関係式または等価式です。  
  
 最初のオペランドが完全に評価され、すべての副作用が完了した後で、論理 OR 式の評価が続行されます。  
  
 2 番目のオペランドは、最初のオペランドが false \(0\) と評価された場合にのみ、評価されます。  これにより、論理 OR 式が true の場合に 2 番目のオペランドの無駄な評価が行われないようになっています。  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 上の例では、`x` が `w`、`y`、または `z` と等しい場合、`printf` 関数の 2 番目の引数が true に評価され、値 1 が出力されます。  それ以外の場合は、false と評価され、値 0 が出力されます。  条件の 1 つが true と評価されると、直ちに評価が終了します。  
  
## &#124;&#124; の演算子キーワード  
 **or** 演算子は `||` の代替表現です。  プログラムで **or** 演算子にアクセスするには、2 つの方法があります。1 つはヘッダー ファイル `iso646.h` を含める方法で、もう 1 つは [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(言語拡張機能を無効にする\) コンパイラ オプションを使用してコンパイルする方法です。  
  
## 使用例  
  
```  
// expre_Logical_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical OR  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b || b > c yields "  
         << (a < b || b > c) << endl  
         << "The false expression "  
         << "a > b || b > c yields "  
         << (a > b || b > c) << endl;  
}  
```  
  
## 参照  
 [論理演算子](../misc/logical-operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 論理演算子](../c-language/c-logical-operators.md)