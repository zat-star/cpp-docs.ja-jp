---
title: "コンパイラの警告 (レベル 1) C4114 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4114"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4114"
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4114
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

同じ型の修飾子が 2 度以上使われています。  
  
 同じ型修飾子 \(**const**、`volatile`、**signed**、または `unsigned`\) が 1 つの型宣言または型定義で 2 回以上使用されています。  Microsoft 拡張機能オプション \/Ze では警告、ANSI 互換オプション \/Za ではエラーになります。  
  
 次の例では警告 C4114 が生成されます。  
  
```  
// C4114.cpp  
// compile with: /W1 /c  
volatile volatile int i;   // C4114  
```  
  
 次の例では警告 C4114 が生成されます。  
  
```  
// C4114_b.cpp  
// compile with: /W1 /c  
static const int const * ii;   // C4114  
static const int * const iii;   // OK  
```