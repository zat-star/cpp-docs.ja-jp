---
title: "コンパイラ エラー C3769 | Microsoft Docs"
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
  - "C3769"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3769"
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3769
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' : 入れ子になっているクラスは、それを囲んでいるクラスと同じ名前を指定することはできません  
  
 入れ子にされたクラスには、外側のクラスと同じ名前を指定できません。  
  
## 使用例  
 次の例では C3769 エラーが生成されます。  
  
```  
// C3769.cpp  
// compile with: /c  
class x {  
   class x {};   // C3769  
   class y {  
      class x{};   // OK  
   };  
};  
```