---
title: "間接演算子: * | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "* 演算子"
  - "間接演算子"
  - "間接演算子, 構文"
  - "演算子 [C++], 間接"
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 間接演算子: *
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
* cast-expression  
```  
  
## 解説  
 単項間接演算子 \(**\***\) はポインターを逆参照します。つまり、ポインター値を左辺値に変換します。  間接演算子のオペランドを型へのポインターにすることはできません。  間接式の結果は、ポインター型の派生元の型です。  このコンテキストでの **\*** 演算子の使用は、乗算の二項演算子としての意味とは異なります。  
  
 オペランドが関数を指している場合、結果は関数指定子になります。  格納場所を指している場合、結果は格納場所を指定する左辺値になります。  
  
 間接演算子は、ポインターへのポインターを逆参照するために累積的に使用される場合があります。  次に例を示します。  
  
```  
// expre_Indirection_Operator.cpp  
// compile with: /EHsc  
// Demonstrate indirection operator  
#include <iostream>  
using namespace std;  
int main() {  
   int n = 5;  
   int *pn = &n;  
   int **ppn = &pn;  
  
   cout  << "Value of n:\n"  
         << "direct value: " << n << endl  
         << "indirect value: " << *pn << endl  
         << "doubly indirect value: " << **ppn << endl  
         << "address of n: " << pn << endl  
         << "address of n via indirection: " << *ppn << endl;  
}  
```  
  
 ポインターの値が無効な場合、結果は未定義になります。  次の一覧に、ポインター値が無効になる一般的な条件をいくつか示します。  
  
-   ポインターが null ポインターです。  
  
-   ポインターが、参照時に見えないローカル項目のアドレスを指定しています。  
  
-   ポインターが、指されているオブジェクトの型ではアラインメントが不適切なアドレスを指定しています。  
  
-   ポインターが、実行プログラムで使用されていないアドレスを指定しています。  
  
## 参照  
 [単項演算子を含む式](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [address\-of 演算子: &](../cpp/address-of-operator-amp.md)   
 [間接演算子とアドレス演算子](../c-language/indirection-and-address-of-operators.md)