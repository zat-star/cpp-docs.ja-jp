---
title: "コンパイラ エラー C3413 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3413"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3413"
ms.assetid: de6c9b05-c373-4bd8-8cb0-12c2cd2e5674
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C3413
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name': 明示的インスタンス化が無効です  
  
 不正な形式の明示的なインスタンス化が検出されました。  
  
 次の例では C3413 が生成されます。  
  
```  
// C3413.cpp template class MyClass {};   // C3413  
```  
  
 考えられる解決方法:  
  
```  
// C3413b.cpp // compile with: /c template <class T> class MyClass {}; template <> class MyClass<int> {};  
```