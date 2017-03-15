---
title: "コンパイラの警告 (レベル 1) C4548 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4548"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4548"
ms.assetid: 2cee817e-e463-4d90-bbd2-de120d48c101
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4548
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンマ前の式は無効です。有効な式を指定してください。  
  
 不正な形式のコンマ式が検出されました。  
  
 既定では、この警告はオフに設定されています。  詳細については、「[Compiler Warnings That Are Off by Default](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
 次の例では警告 C4548 が生成されます。  
  
```  
// C4548.cpp  
// compile with: /W1  
#pragma warning (default : 4548)  
int main()  
{  
   int i = 0, k = 0;  
  
   if ( i, k )   // C4548  
   // try the following line instead  
   // if ( i = 0, k )  
      i++;  
}  
```