---
title: "コンパイラ エラー C2092 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2092"
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'array name' 配列の要素の型は関数にできません。  
  
 関数の配列は使用できません。  関数へのポインターの配列を使用してください。  
  
## 使用例  
 次の例では警告 C2092 が生成されます。  
  
```  
// C2092.cpp  
typedef void (F) ();  
typedef F AT[10];   // C2092  
```  
  
## 使用例  
 解決方法 :  
  
```  
// C2092b.cpp  
// compile with: /c  
typedef void (F) ();  
typedef F * AT[10];  
```