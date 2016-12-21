---
title: "コンパイラの警告 (レベル 1) C4558 | Microsoft Docs"
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
  - "C4558"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4558"
ms.assetid: 52bb0324-7bec-468c-b35b-13a08d38e578
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4558
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

オペランド 'value' の値が 'lowerbound upperbound\- ' の範囲を超えています。  
  
 アセンブリ言語命令に渡された値が、パラメーターに指定された範囲を超えています。  値は切り捨てられます。  
  
 次の例では警告 C4558 が生成されます。  
  
```  
// C4558.cpp  
// compile with: /W1  
// processor: x86  
void asm_test() {  
   __asm pinsrw   mm1, eax, 8;   // C4558  
}  
  
int main() {  
}  
```