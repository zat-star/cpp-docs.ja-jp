---
title: "コンパイラの警告 (レベル 3) C4281 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4281"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4281"
ms.assetid: a9771261-5725-4fc6-87b6-16cf92113a25
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 3) C4281
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

「演算子–\>' 再帰型"型"を通じて実行  
  
 コードは **operator–\>** が自身を呼び出すことができます。  
  
 次の例では警告 C4281 が生成されます。  
  
```  
// C4281.cpp  
// compile with: /W3 /WX  
struct A;  
struct B;  
struct C;  
  
struct A  
{  
   int z;  
   B& operator->();  
};  
  
struct B  
{  
   C& operator->();  
};  
  
struct C  
{  
   A& operator->();  
};  
  
void f(A p)  
{  
   int i = p->z; // C4281  
}  
```