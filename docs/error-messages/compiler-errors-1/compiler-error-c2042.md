---
title: "コンパイラ エラー C2042 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2042"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2042"
ms.assetid: e111788f-41ce-405a-9824-a4c1c26059e6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2042
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'signed' と 'unsigned' が 1 つの宣言内で同時に使われています。  
  
 キーワード `signed` と `unsigned` は、1 つの宣言で使用します。  
  
 次の例では C2042 エラーが生成されます。  
  
```  
// C2042.cpp unsigned signed int i;   // C2042  
```  
  
 考えられる解決方法:  
  
```  
// C2042b.cpp // compile with: /c unsigned int i; signed int ii;  
```