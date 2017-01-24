---
title: "コンパイラ エラー C2490 | Microsoft Docs"
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
  - "C2490"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2490"
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2490
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'naked' 属性の関数内で 'keyword' は許されません。  
  
 [naked](../Topic/naked%20\(C++\).md) として定義された関数では、構造化例外処理を使用できません。  
  
 次の例では警告 C2490 が生成されます。  
  
```  
// C2490.cpp  
// processor: x86  
__declspec( naked ) int func() {  
   __try{}   // C2490, structured exception handling  
}  
```