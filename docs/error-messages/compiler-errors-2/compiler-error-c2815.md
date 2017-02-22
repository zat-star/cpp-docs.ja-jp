---
title: "コンパイラ エラー C2815 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2815"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2815"
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2815
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator delete' : 1 番目の実引数は 'void \*' 型でなければなりませんが、'param' が使用されました。  
  
 ユーザー定義関数 [operator delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md) の最初の仮パラメーターは、`void *` 型にする必要があります。  
  
 次の例では警告 C2815 が生成されます。  
  
```  
// C2815.cpp  
// compile with: /c  
class CMyClass {  
public:  
   void mf1(int *a);  
   void operator delete(CMyClass *);   // C2815  
   void operator delete(void *);   
};  
```