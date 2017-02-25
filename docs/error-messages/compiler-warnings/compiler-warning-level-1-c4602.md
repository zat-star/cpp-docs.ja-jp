---
title: "コンパイラの警告 (レベル 1) C4602 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4602"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4602"
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1) C4602
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma pop\_macro : 'macro name' この識別子に対する前の \#pragma push\_macro がありません  
  
 特定のマクロに [pop\_macro](../Topic/pop_macro.md) を使用する場合は、そのマクロ名を [push\_macro](../../preprocessor/push-macro.md) にまず渡す必要があります。 たとえば、次の例では C4602 が生成されます。  
  
```  
// C4602.cpp // compile with: /W1 int main() { #pragma pop_macro("x")   // C4602 x is not on the stack }  
```