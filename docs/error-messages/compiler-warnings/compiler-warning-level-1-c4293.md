---
title: "コンパイラの警告 (レベル 1) C4293 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4293"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4293"
ms.assetid: babecd96-eb51-41a5-9835-462c7a46dbad
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4293
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'演算子' : シフト数が負の値であるか、大きすぎます。定義されていない動作です  
  
 シフト数が負の値であるか大きすぎる場合は、生成されるイメージの動作が未定義です。  
  
## 使用例  
 次の例では警告 C4293 が生成されます。  
  
```  
// C4293.cpp  
// compile with: /c /W1  
unsigned __int64 combine (unsigned lo, unsigned hi) {  
  
   return (hi << 32) | lo;   // C4293  
  
   // try the following line instead  
   // return ( (unsigned __int64)hi << 32) | lo;  
}  
```