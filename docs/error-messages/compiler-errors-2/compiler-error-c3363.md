---
title: "コンパイラ エラー C3363 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3363"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3363"
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C3363
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 'typeid' のみを型に適用できます  
  
 [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) 演算子が正しく使用されていません。  
  
## 使用例  
 次の例では C3363 が生成されます。  
  
```  
// C3363.cpp // compile with: /clr int main() { System::typeid;   // C3363 }  
```