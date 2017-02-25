---
title: "コンパイラ エラー C2486 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2486"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2486"
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2486
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\_\_LOCAL\_SIZE' の指定は 'naked' 属性の関数の中でのみ許されています。  
  
 インライン アセンブリ関数では、`__LOCAL_SIZE` という名前は [naked](../Topic/naked%20\(C++\).md) 属性を指定して宣言した関数に予約されています。  
  
 次の例では警告 C2486 が生成されます。  
  
```  
// C2486.cpp  
// processor: x86  
void __declspec(naked) f1() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE  
   }  
}  
void f2() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE   // C2486  
   }  
}  
```