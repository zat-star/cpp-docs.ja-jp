---
title: "コンパイラ エラー C2523 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2523"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2523"
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2523
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::~identifier' : 'destructor\/finalizer' が、別の名前で宣言されています。  
  
 デストラクターの名前はクラスと同じ名前にして、その前にティルダ \(`~`\) を付ける必要があります。  クラスと同じ名前を使用できるメンバーは、コンストラクターとデストラクターだけです。  
  
 次の例では警告 C2523 が生成されます。  
  
```  
// C2523.cpp  
// compile with: /c  
class A {  
   ~B();    // C2523  
   ~A();   // OK  
};  
```