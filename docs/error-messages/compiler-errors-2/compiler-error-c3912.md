---
title: "コンパイラ エラー C3912 | Microsoft Docs"
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
  - "C3912"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3912"
ms.assetid: 674e050c-11fb-4db1-8bdf-a3e95b41161d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3912
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'イベント': イベントの型はデリゲート型でなければなりません  
  
 イベントが宣言されましたが、適切な型ではありません。  
  
 詳細については、「[イベント](../../windows/event-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3912 が生成されます。  
  
```  
// C3912.cpp  
// compile with: /clr  
delegate void H();  
ref class X {  
   event int Ev;   // C3912  
   event H^ Ev2;   // OK  
};  
```