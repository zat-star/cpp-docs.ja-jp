---
title: "論理否定演算子: ! | Microsoft Docs"
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
  - "!"
  - "Not"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "! 演算子"
  - "論理否定"
  - "NOT 演算子"
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 論理否定演算子: !
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
! cast-expression  
```  
  
## 解説  
 論理否定演算子 \(**\!**\) は、オペランドの意味を反転させます。  オペランドは、数値型またはポインター型 \(または、数値型またはポインター型に評価される式\) である必要があります。  オペランドは `bool` 型に暗黙的に変換されます。  変換されたオペランドが **false** の場合、結果は **true** となり、変換されたオペランドが **true** の場合は、結果が **false** になります。  結果は `bool` 型です。  
  
 式 *e* について、単項式 **\!***e* は、オーバーロードされた演算子が関係する点を除いて、式 **\(***e* `==` 0\) と等価です。  
  
## \! の演算子キーワード  
 **not** 演算子は **\!** の代替表現です。  プログラムで **not** 演算子にアクセスするには、2 つの方法があります。1 つはヘッダー ファイル `iso646.h` を含める方法で、もう 1 つは [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(言語拡張機能を無効にする\) コンパイラ オプションを使用してコンパイルする方法です。  
  
## 使用例  
  
```  
// expre_Logical_NOT_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 0;  
   if (!i)  
      cout << "i is zero" << endl;  
}  
```  
  
## 参照  
 [単項演算子を含む式](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [単項算術演算子](../c-language/unary-arithmetic-operators.md)