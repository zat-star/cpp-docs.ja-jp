---
title: "コンパイラの警告 (レベル 4) C4429 | Microsoft Docs"
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
  - "C4429"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4429"
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4429
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

不完全な、または正しい形式でないユニバーサル文字名です  
  
 コンパイラが、誤った形式のユニバーサル文字名の可能性がある文字シーケンスを検出しました。  ユニバーサル文字名は、`\u` に続く 4 桁の 16 進数、または `\U` に続く 8 桁の 16 進数です。  
  
 次の例では警告 C4429 が生成されます。  
  
```  
// C4429.cpp  
// compile with: /W4 /WX  
int \ug0e4 = 0;   // C4429  
// Try the following line instead:  
// int \u00e4 = 0;   // OK, a well-formed universal character name.  
```