---
title: "コンパイラの警告 (レベル 3) C4310 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4310"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4310"
ms.assetid: cba3eca1-f1ed-499c-9243-337446bdbdd8
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 3) C4310
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

キャストによって定数値が切り捨てられました。  
  
 定数値が小さい型にキャストされています。  キャストが実行され、データが切り捨てられます。  次の例では警告 C4310 が生成されます。  
  
```  
// C4310.cpp  
// compile with: /W4  
int main() {  
   long int a;  
   a = (char) 128;   // C4310, use value 0-127 to resolve  
}  
```