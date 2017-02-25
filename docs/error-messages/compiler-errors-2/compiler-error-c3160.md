---
title: "コンパイラ エラー C3160 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3160"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3160"
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C3160
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'pointer': マネージ クラスまたは WinRT クラスのデータ メンバーにはこの型を指定できません。  
  
 内部のガベージ コレクション ポインターは、マネージ クラスまたは WinRT クラスの内部を指す場合があります。  オブジェクト全体のポインターよりも遅く、ガベージ コレクターによる特別な処理を必要とするため、クラスのメンバーとして内部のマネージ ポインターを宣言することはできません。  
  
 次の例では C3160 が生成されます。  
  
```  
// C3160.cpp  
// compile with: /clr  
ref struct A {  
   // cannot create interior pointers inside a class  
   interior_ptr<int> pg;   // C3160  
   int g;   // OK  
   int* pg2;   // OK  
};  
  
int main() {  
   interior_ptr<int> pg2;   // OK  
}  
```  
  
 **C\+\+ マネージ拡張**  
  
 次の例では C3160 が生成されます。  
  
```  
// C3160b.cpp  
// compile with: /clr:oldSyntax  
  
__gc struct A {  
   // cannot create interior pointers inside a class  
   int __gc* pg; // C3160  
   int g;   // OK  
   int __nogc *pg2;   // OK  
};  
  
int main() {  
   int __gc* pg2;   // OK  
}  
```