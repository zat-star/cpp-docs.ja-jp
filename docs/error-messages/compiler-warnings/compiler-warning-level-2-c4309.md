---
title: "コンパイラの警告 (レベル 2) C4309 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4309"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4309"
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 2) C4309
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'conversion' : 定数値が切り捨てられました。  
  
 型変換によって、定数が確保された領域からあふれます。  定数に大きい型を使用することが必要な場合があります。  
  
 次の例では警告 C4309 が生成されます。  
  
```  
// C4309.cpp  
// compile with: /W2  
int main()  
{  
   char c = 128;   // C4309  
}  
```