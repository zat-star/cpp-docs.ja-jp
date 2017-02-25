---
title: "コンパイラの警告 (レベル 4) C4389 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "c4389"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4389"
ms.assetid: fc0e3a8e-f766-437c-b7f1-e61abb2a8765
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 4) C4389
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : signed と unsigned の数値を比較しようとしました。  
  
 演算で符号付きの変数と符号なしの変数が使用されました。  このため、データが失われている可能性があります。  
  
 次の例では警告 C4389 が生成されます。  
  
```  
// C4389.cpp  
// compile with: /W4  
#pragma warning(default: 4389)  
  
int main()  
{  
   int a = 9;  
   unsigned int b = 10;  
   if (a == b)   // C4389  
      return 0;  
   else  
      return 0;  
};  
```