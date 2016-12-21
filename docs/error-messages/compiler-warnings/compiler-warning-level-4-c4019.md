---
title: "コンパイラの警告 (レベル 4) C4019 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4019"
ms.assetid: 4ecfe85d-673f-4334-8154-36fe7f0b3444
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

グローバル スコープで空行があります。  
  
 グローバル スコープのセミコロンの前にステートメントがありません。  
  
 この警告は、余分なセミコロンを削除すると解決される場合があります。  
  
## 使用例  
  
```  
// C4019.c // compile with: /Za /W4 #define declint( varname ) int varname; declint( a );   // C4019, int a;; declint( b )   // OK, int b; int main() { }  
```