---
title: "コンパイラの警告 (レベル 1) C4804 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4804"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4804"
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4804
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operation' : 演算中の 'bool' 型の使用方法が安全ではありません。  
  
 `bool` 変数または `bool` 値の使い方が不正であると、この警告が生成されます。  たとえば、負の単項演算子 \(**\-**\) や補数演算子 \(`~`\) などを使用すると、C4804 警告が生成されます。  コンパイラによって式が評価されます。  
  
## 使用例  
 次の例では警告 C4804 が生成されます。  
  
```  
// C4804.cpp  
// compile with: /W1  
  
int main()  
{  
   bool i = true;  
   if (-i)   // C4804, remove the '-' to resolve  
   {  
      i = false;  
   }  
}  
```