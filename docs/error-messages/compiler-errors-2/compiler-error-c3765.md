---
title: "コンパイラ エラー C3765 | Microsoft Docs"
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
  - "C3765"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3765"
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3765
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event' : event\_receiver とマークされた class\/struct 'type' 内でイベントを定義できません。  
  
 クラスが [event\_receiver](../../windows/event-receiver.md) 属性でマークされている場合は、そのクラスに [\_\_event](../../cpp/event.md) 宣言を含めることはできません。  
  
 次の例では警告 C3765 が生成されます。  
  
```  
// C3765.cpp  
[event_receiver(native)]  
struct ER2 {  
   __event void f();   // C3765  
   __event void b(int);   // C3765  
};  
```