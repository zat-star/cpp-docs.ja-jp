---
title: "コンパイラ エラー C3071 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3071
dev_langs:
- C++
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
caps.latest.revision: 7
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
ms.openlocfilehash: 11abc98378bd77dafe4a741fb7f7d5ea83ba3d4c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3071"></a>コンパイラ エラー C3071
演算子 'operator' は、ref クラスまたは値型のインスタンスにのみ適用できます  
  
 CLR 演算子は、ネイティブ型で使用できません。 この演算子は、ref クラスや ref 構造体 (値型) で使用できますが、System::Int32 のようなネイティブ型の int やエイリアスなどのネイティブ型では使用できません。 これらの型は、ネイティブ変数を参照する方法で C++ コードからボックス化することはできません。したがって、この演算子は使用できません。  
  
 詳細については、次を参照してください。[参照演算子の追跡](../../windows/tracking-reference-operator-cpp-component-extensions.md)します。  
  
## <a name="example"></a>例  
 次の例では C3071 が生成されます。  
  
```  
// C3071.cpp  
// compile with: /clr  
class N {};  
ref struct R {};  
  
int main() {  
   N n;  
   %n;   // C3071  
  
   R r;  
   R ^ r2 = %r;   // OK  
}  
```
