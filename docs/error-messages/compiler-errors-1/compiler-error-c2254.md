---
title: "コンパイラ エラー C2254 | Microsoft Docs"
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
  - "C2254"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2254"
ms.assetid: 49bb3d7e-3bdf-4af6-937c-fa627be412a9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2254
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : フレンド関数が、純粋関数または抽象オーバーライド関数であると指定されています  
  
 `friend` 関数が、純粋な `virtual` 関数として指定されています。  
  
 次の例では警告 C2254 が生成されます。  
  
```  
// C2254.cpp  
// compile with: /c  
class A {  
public:  
   friend void func1() = 0;   // C2254, func1 is friend  
   void virtual func2() = 0;   // OK, pure virtual  
   friend void func3();   // OK, friend not virtual nor pure  
};  
  
void func1() {};  
void func3() {};  
```