---
title: "コンパイラ エラー C3298 | Microsoft Docs"
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
  - "C3298"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3298"
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3298
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'constraint\_1': 'constraint\_2' を制約として使用できません。'constraint\_2' は ref 制約を含んでおり、'constraint\_1' は値の制約を含んでいるためです  
  
 制約に相互に排他的な特性を指定することはできません。 たとえば、ジェネリック型パラメーターを、値型と参照型の両方に制限することはできません。  
  
 詳細については、「[Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../Topic/Constraints%20on%20Generic%20Type%20Parameters%20\(C++-CLI\).md)」を参照してください。  
  
## 使用例  
 次の例では C3298 が生成されます。  
  
```  
// C3298.cpp // compile with: /clr /c generic<class T, class U> where T : ref class where U : T, value class   // C3298 public ref struct R {};  
```