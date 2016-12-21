---
title: "コンパイラ エラー C2041 | Microsoft Docs"
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
  - "C2041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2041"
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定された文字 'character' は、基数 'number' に適切な数字ではありません。  
  
 指定された文字は、基数 \(8 進数や 16 進数など\) として有効な数字ではありません。  
  
 次の例では警告 C2041 が生成されます。  
  
```  
// C2041.cpp  
int i = 081;   // C2041  8 is not a base 8 digit  
```  
  
 解決方法 :  
  
```  
// C2041b.cpp  
// compile with: /c  
int j = 071;  
```