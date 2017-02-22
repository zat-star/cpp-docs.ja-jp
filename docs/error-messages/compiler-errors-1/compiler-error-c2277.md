---
title: "コンパイラ エラー C2277 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2277"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2277"
ms.assetid: 15a83b07-8731-4524-810b-267f65a7844f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2277
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : メンバー関数のアドレスは取得できません。  
  
 メンバー関数のアドレスを使うことはできません。  
  
 次の例では警告 C2277 が生成されます。  
  
```  
// C2277.cpp  
class A {  
public:  
   A();  
};  
(*pctor)() = &A::A;   // C2277   
```