---
title: "コンパイラの警告 (レベル 1) C4230 | Microsoft Docs"
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
  - "C4230"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4230"
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4230
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

旧形式が使用されています : 修飾子\/限定名が混在している場合、限定名は無視されます。  
  
 `__cdecl` などの Microsoft の修飾子の前に修飾子を使用する方法は、現在ではあまり使われません。  
  
## 使用例  
  
```  
// C4230.cpp  
// compile with: /W1 /LD  
int __cdecl const function1();   // C4230 const ignored  
```