---
title: "コンパイラの警告 (レベル 1) C4547 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4547"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4547"
ms.assetid: 3edf1c2e-c0d5-444d-ae83-44a7cce24bb2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4547
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : コンマの前の演算子は無効です。有効な演算子を指定してください。  
  
 不正な形式のコンマ式が検出されました。  
  
 既定では、この警告はオフに設定されています。  詳細については、「[Compiler Warnings That Are Off by Default](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
 次の例では警告 C4547 が生成されます。  
  
```  
// C4547.cpp  
// compile with: /W1  
#pragma warning (default : 4547)  
int i = 0;  
int j = 1;  
int main() {  
   int l = (i != i,0);   // C4547  
   // try the following line instead  
   // int l = (i != i);  
   // or  
   // int l = ((void)(i != i),0);  
}  
```