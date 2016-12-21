---
title: "コンパイラの警告 (レベル 1) C4229 | Microsoft Docs"
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
  - "C4229"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4229"
ms.assetid: aadfc83b-1e5f-4229-bd0a-9c10a5d13182
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4229
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

旧形式が使用されています : データの修飾子は無視されます。  
  
 データ宣言に `__cdecl` などの Microsoft の修飾子を使用する方法は、現在ではあまり使われません。  
  
## 使用例  
  
```  
// C4229.cpp  
// compile with: /W1 /LD  
int __cdecl counter;   // C4229 cdecl ignored  
```