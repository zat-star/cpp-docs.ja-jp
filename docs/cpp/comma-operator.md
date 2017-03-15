---
title: "コンマ演算子: , | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "%2C"
  - ","
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コンマ演算子"
ms.assetid: 38e0238e-19da-42ba-ae62-277bfdab6090
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# コンマ演算子: ,
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

1 つのステートメントが期待される場所で 2 つのステートメントをグループ化します。  
  
## 構文  
  
```  
  
expression , expression  
```  
  
## 解説  
 コンマ演算子の結合規則は、左から右方向です。  コンマで区切られた 2 つの式は左から右に評価されます。  左オペランドは常に評価され、右オペランドが評価される前にすべての副作用が完了します。  
  
 コンマは、関数の引数リストなどの一部のコンテキストで、区切り記号として使用できます。  区切り記号としてのコンマの使用と演算子としての使用を混同しないでください。この 2 つの用途は、まったく別のものです。  
  
 次の式を考えます。  
  
 *e1* , *e2*  
  
 この式の型と値は、*e2* の型と値です。*e1* を評価した結果は破棄されます。  結果は、右オペランドが左辺値の場合は左辺値です。  
  
 通常、コンマが区切り記号として使用される場所 \(たとえば、関数の実引数や集約の初期化子\) では、コンマ演算子とそのオペランドをかっこで囲む必要があります。  次に例を示します。  
  
```  
func_one( x, y + 2, z );  
func_two( (x--, y + 2), z );  
```  
  
 前の `func_one` の関数呼び出しでは、`x`、`y + 2`、`z` という 3 つの引数がコンマで区切られて渡されます。  `func_two` の関数呼び出しでは、かっこにより、コンパイラは順次評価演算子として最初のコンマを解釈します。  この関数呼び出しは、`func_two` に 2 つの引数を渡します。  最初の引数は、順次評価演算 `(x--, y + 2)` の結果です。この演算は、式 `y + 2` の値と型を持ち、第 2 の引数は `z` です。  
  
## 使用例  
  
```  
// cpp_comma_operator.cpp  
#include <stdio.h>  
int main () {  
   int i = 10, b = 20, c= 30;  
   i = b, c;  
   printf("%i\n", i);  
  
   i = (b, c);  
   printf("%i\n", i);  
}  
```  
  
  **20**  
**30**   
## 参照  
 [二項演算子を含む式](../cpp/expressions-with-binary-operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [順次評価演算子](../c-language/sequential-evaluation-operator.md)