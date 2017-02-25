---
title: "コンパイラ エラー C2735 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2735"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2735"
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2735
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'keyword' キーワードは、仮パラメーターの型指定子で使用できません。  
  
 指定されたキーワードはこのコンテキストでは使用できません。  
  
 次の例では警告 C2735 が生成されます。  
  
```  
// C2735.cpp  
void f(inline int){}   // C2735  
```