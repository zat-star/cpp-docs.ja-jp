---
title: "コンパイラ エラー C2682 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2682
dev_langs:
- C++
helpviewer_keywords:
- C2682
ms.assetid: 30c6a7c4-f5f7-4fe8-81a8-c48938521ab4
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 5b44d0cd891737f5fbd7a2870a6707568a729946
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2682"></a>コンパイラ エラー C2682
'type1' から 'type2' に変換する casting_operator を使用することはできません。  
  
 キャスト演算子は、互換性のない型の間で変換しようとしました。 たとえば、使用することはできません、 [dynamic_cast](../../cpp/dynamic-cast-operator.md)参照へのポインターを変換する演算子です。 `dynamic_cast`キャスト修飾子に演算子は使用できません。 型のすべての修飾子が一致する必要があります。  
  
 使用することができます、`const_cast`などの属性を削除するオペレーター `const`、 `volatile`、または`__unaligned`です。  
  
 次の例では、c2682 エラーが生成されます。  
  
```  
// C2682.cpp  
class A { virtual void f(); };  
class B: public A {};  
  
void g(A* pa) {  
    B& rb = dynamic_cast<B&>(pa); // C2682  
}  
```  
  
 次の例では、c2682 エラーが生成されます。  
  
```  
// C2682b.cpp  
// compile with: /clr  
ref struct R{};  
ref struct RR : public R{};  
ref struct H {  
   RR^ r ;  
   short s;  
   int i;  
};  
  
int main() {  
   H^ h = gcnew H();    
   interior_ptr<int>lr = &(h->i);  
   interior_ptr<short>ssr = safe_cast<interior_ptr<short> >(lr);   // C2682  
   interior_ptr<short>ssr = reinterpret_cast<interior_ptr<short> >(lr);   // OK  
}  
```
