---
title: "コンパイラ エラー C2052 | Microsoft Docs"
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
  - "C2052"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2052"
ms.assetid: 922ca43b-b64b-4ef7-9611-c7313be3fd79
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2052
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 条件式に対する無効な型です。  
  
 **case** の式は整数定数にする必要があります。  
  
 次の例では警告 C2052 が生成されます。  
  
```  
// C2052.cpp  
int main() {  
   int index = 0;  
   switch (index) {  
      case 1:  
         return 24;  
      case 1.0:   // C2052  
      // try the following line instead  
      // case 2:  
         return 23;  
   }  
}  
```