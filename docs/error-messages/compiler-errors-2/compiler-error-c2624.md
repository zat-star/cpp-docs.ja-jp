---
title: "コンパイラ エラー C2624 | Microsoft Docs"
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
  - "C2624"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2624"
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2624
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ローカル クラスは 'extern' 変数の宣言に使用できません。  
  
 ローカル クラスや構造体は、`extern` 変数の宣言には使用できません。  
  
 次の例では警告 C2624 が生成されます。  
  
```  
// C2624.cpp  
int main() {  
   struct C {};  
   extern C ac;   // C2624  
}  
```