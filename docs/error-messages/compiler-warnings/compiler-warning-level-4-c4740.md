---
title: "コンパイラの警告 (レベル 4) C4740 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4740"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4740"
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 4) C4740
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インライン asm コードの内部または外部のフローは、グローバルな最適化を抑制します  
  
 `asm` ブロックの内部または外部にジャンプする場合、その関数ではグローバル最適化が無効になります。  
  
 次の例では警告 C4740 が生成されます。  
  
```  
// C4740.cpp  
// compile with: /O2 /W4  
// processor: x86  
int main() {  
   __asm jmp tester  
   tester:;  
}  
```