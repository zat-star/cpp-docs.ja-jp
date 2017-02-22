---
title: "コンパイラ エラー C2436 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2436"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2436"
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2436
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : メンバー関数または入れ子のクラスがコンストラクターの初期化リストにあります。  
  
 コンストラクターの初期化リストにあるメンバー関数またはローカル クラスは初期化できません。  
  
 次の例では警告 C2436 が生成されます。  
  
```  
// C2436.cpp  
struct S{  
   int f();  
   struct Inner{  
      int i;  
   };  
   S():f(10), Inner(0){}   // C2436  
};  
```