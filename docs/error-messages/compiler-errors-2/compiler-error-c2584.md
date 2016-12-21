---
title: "コンパイラ エラー C2584 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2584"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2584"
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2584
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Class' : 直接クラス 'Base2' は派生クラス 'Base1' の基本クラスとして使われています。  
  
 `Class` が既に `Base1` から直接派生しています。  `Base2` も `Base1` から派生しています。  `Class` は `Base2` から派生できません。この派生は、再び `Base1` から間接的に継承することを意味しますが、`Base1` は既に直接基本クラスであるため無効だからです。  
  
## 使用例  
 次の例では C2584 エラーが生成されます。  
  
```  
// C2584.cpp  
// compile with: /c  
struct A1 {  
   virtual int MyFunction();  
};  
  
struct A2 {  
    virtual int MyFunction();  
};  
  
struct B1: public virtual A1, virtual A2 {  
    virtual int MyFunction();  
};  
  
struct B2: public virtual A2, virtual A1 {  
    virtual int MyFunction();  
};  
  
struct C: virtual B1, B2 {  
    virtual int MyFunction();  
};  
  
struct Z : virtual B2, virtual C {   // C2584  
// try the following line insted  
// struct Z : virtual C {  
    virtual int MyFunction();  
};  
```