---
title: "コンパイラ エラー C2819 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2819"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2819"
ms.assetid: fcc7762d-cb82-4bb1-a715-0d82da832edf
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2819
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

型" type "にはオーバーロードされたメンバー演算子が「\-\>」  
  
 このポインター演算子を使用するには、`operator->()` を定義する必要があります。  
  
 次の例では警告 C2819 が生成されます。  
  
```  
// C2819.cpp  
// compile with: /c  
class A {  
   public:  
      int i;  
};  
  
class B {};  
  
void C(B j) {  
   j->i;   // C2819  
}  
  
class D {  
   A* pA;  
  
   public:  
      A* operator->() {  
         return pA;  
      }  
};  
  
void F(D j) {  
   j->i;  
}  
```  
  
 C2819 は、[参照型の C\+\+ スタック セマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md) を使用しているときも発生します。  次の例では警告 C2819 が生成されます。  
  
```  
// C2819_b.cpp  
// compile with: /clr  
ref struct R {  
   void Test() {}  
};  
  
int main() {  
   R r;  
   r->Test();   // C2819  
   r.Test();   // OK  
}  
```