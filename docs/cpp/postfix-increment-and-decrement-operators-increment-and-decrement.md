---
title: "後置インクリメント演算子と後置デクリメント演算子: ++ および -- | Microsoft Docs"
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
  - "--"
  - "++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-- 演算子, 後置デクリメント演算子"
  - "++ 演算子, 後置インクリメント演算子"
  - "デクリメント演算子"
  - "デクリメント演算子, 構文"
  - "インクリメント演算子, 構文"
  - "メンバー選択演算子"
  - "演算子 [C++], 後置"
  - "後置演算子"
ms.assetid: 0204d5c8-51b0-4108-b8a1-074c5754d89c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 後置インクリメント演算子と後置デクリメント演算子: ++ および --
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
      postfix-expression   
      ++  
postfix-expression ––  
```  
  
## 解説  
 C\+\+ には、前置および後置のインクリメント演算子およびデクリメント演算子が用意されています。このセクションでは、後置インクリメント演算子および後置デクリメント演算子についてのみ説明します  \(詳細については、「[前置インクリメント演算子と前置デクリメント演算子](../Topic/Prefix%20Increment%20and%20Decrement%20Operators:%20++%20and%20--.md)」を参照してください\)。 2 つの間の違いは、後置表記法では演算子が *postfix\-expression* の後に置かれるのに対し、前置表記法では演算子が *expression* の前に置かれます。 次の例は、後置インクリメント演算子を示しています。  
  
```  
i++;  
```  
  
 後置インクリメント演算子 \(`++`\) を適用する効果は、オペランドの値が適切な型の 1 単位分、増加することです。  同様に、後置デクリメント演算子 \(**––**\) を適用する効果は、オペランドの値が適切な型の 1 単位分、減少することです。  
  
 後置のインクリメント式またはデクリメント式は、各演算子が適用される "前" に式の値が評価されることに注意してください。  インクリメントまたはデクリメント演算子は、オペランドが評価された "後" に適用されます。  この問題は、後置インクリメントまたはデクリメント演算が、より大きな式のコンテキストで行われる場合にのみ発生します。  
  
 後置演算子を関数の引数に適用した場合、引数の値が関数に渡される前にインクリメントまたはデクリメントされる保証はありません。  詳細については、C\+\+ 標準のセクション 1.9.17 を参照してください。  
  
 **long** 型のオブジェクトの配列へのポインターに後置インクリメント演算子を適用すると、実際にはポインターの内部表現に 4 が加算されます。  この動作により、以前は配列の *n* 番目の要素を参照したポインターが今度は *n* \+ 1 番目の要素を参照するようになります。  
  
 後置インクリメント演算子と後置デクリメント演算子のオペランドは、演算型またはポインター型の変更可能な \(**const** ではない\) 左辺値である必要があります。  結果の型は *postfix\-expression* の型と同じですが、左辺値ではなくなります。  
  
 後置インクリメント演算子のオペランドは、`bool` 型である場合もあります。この場合、オペランドが評価された後、**true** に設定されます。  後置デクリメント演算子のオペランドを `bool` 型にすることはできません。  
  
 次のコードは、後置インクリメント演算子を示しています。  
  
```  
// expre_Postfix_Increment_and_Decrement_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 10;  
   cout << i++ << endl;  
   cout << i << endl;  
}  
```  
  
 列挙型に対する後置インクリメント演算および後置デクリメント演算はサポートされていません。  
  
```  
enum Compass { North, South, East, West );  
Compass myCompass;  
for( myCompass = North; myCompass != West; myCompass++ ) // Error  
```  
  
## 参照  
 [後置式](../cpp/postfix-expressions.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 後置インクリメント演算子と後置デクリメント演算子](../c-language/c-postfix-increment-and-decrement-operators.md)