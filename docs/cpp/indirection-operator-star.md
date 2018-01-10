---
title: "間接演算子: * |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- '* operator'
- indirection operator
- operators [C++], indirection
- indirection operator [C++], syntax
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2c87c279ae1f45899dfa4525c3bdc65bfa5acc2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="indirection-operator-"></a>間接演算子: *
## <a name="syntax"></a>構文  
  
```  
  
* cast-expression  
```  
  
## <a name="remarks"></a>コメント  
 単項間接演算子 (**\***)、ポインターを逆参照、ポインター値を左辺値に変換します。 間接演算子のオペランドを型へのポインターにすることはできません。 間接式の結果は、ポインター型の派生元の型です。 使用、  **\*** このコンテキストでは演算子とは異なる乗算は、バイナリ演算子とその意味します。  
  
 オペランドが関数を指している場合、結果は関数指定子になります。 格納場所を指している場合、結果は格納場所を指定する左辺値になります。  
  
 間接演算子は、ポインターへのポインターを逆参照するために累積的に使用される場合があります。 例:  
  
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
  
 ポインターの値が無効な場合、結果は未定義になります。 次の一覧に、ポインター値が無効になる一般的な条件をいくつか示します。  
  
-   ポインターが null ポインターです。  
  
-   ポインターが、参照時に見えないローカル項目のアドレスを指定しています。  
  
-   ポインターが、指されているオブジェクトの型ではアラインメントが不適切なアドレスを指定しています。  
  
-   ポインターが、実行プログラムで使用されていないアドレスを指定しています。  
  
## <a name="see-also"></a>参照  
 [単項演算子を含む式](../cpp/expressions-with-unary-operators.md)   
 [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Address-of 演算子: (& a)](../cpp/address-of-operator-amp.md)   
 [間接演算子とアドレス演算子](../c-language/indirection-and-address-of-operators.md)