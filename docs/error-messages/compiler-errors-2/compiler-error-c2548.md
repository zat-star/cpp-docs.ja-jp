---
title: "コンパイラ エラー C2548 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2548"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2548"
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2548
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::member' : parameter 番目の引数に対して既定の引数がありません。  
  
 既定のパラメーター リストのパラメーターが 1 つ足りません。  既定のパラメーターをパラメーター リストのどこかに指定する場合は、後続のすべてのパラメーターに対して既定のパラメーターを定義する必要があります。  
  
## 使用例  
 次の例では警告 C2548 が生成されます。  
  
```  
// C2548.cpp  
// compile with: /c  
void func( int = 1, int, int = 3);  // C2548  
  
// OK  
void func2( int, int, int = 3);  
void func3( int, int = 2, int = 3);  
```