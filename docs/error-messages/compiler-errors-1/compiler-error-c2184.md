---
title: "コンパイラ エラー C2184 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2184"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2184"
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2184
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': \_\_ except 式の型が無効です。整数でなければなりません  
  
 [\_\_ except](../../c-language/try-except-statement-c.md) ステートメントで型を使用しましたが、その型は許可されていません。  
  
 次の例では C2184 が生成されます。  
  
```  
// C2184.cpp void f() { int * p; __try{} __except(p){};   // C2184 }  
```  
  
 考えられる解決策:  
  
```  
// C2184b.cpp // compile with: /c void f() { int i = 0; __try{} __except(i){}; }  
```