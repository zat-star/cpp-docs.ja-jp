---
title: "コンパイラの警告 (レベル 1) C4584 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4584"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4584"
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4584
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class1' : 基本クラス 'class2' は既に 'class3' の基本クラスです。  
  
 定義したクラスは 2 つのクラスを継承していますが、一方のクラスが他方のクラスを継承しています。  たとえば、次のようになります。  
  
```  
// C4584.cpp  
// compile with: /W1 /LD  
class A {  
};  
  
class B : public A {  
};  
  
class C : public A, public B { // C4584  
};  
```  
  
 この場合クラス C に関する警告が表示されます。クラス C はクラス A およびクラス B の両方を継承し、クラス B もクラス A を継承するためです。  この警告は、これらの基本クラスからのメンバーの使用を完全限定しないと、参照クラスのメンバーがあいまいになるため、コンパイラ エラーが生成されることを示しています。