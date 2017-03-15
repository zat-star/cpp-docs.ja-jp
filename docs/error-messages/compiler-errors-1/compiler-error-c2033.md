---
title: "コンパイラ エラー C2033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2033"
ms.assetid: fd5a1637-9db2-4c98-a7cc-b63b39737cd9
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : ビット フィールドは間接参照できません  
  
 ビット フィールドが、許可されていないポインターとして宣言されました。  
  
 次の例では C2033 が生成されます。  
  
```  
// C2033.cpp struct S { int *b : 1;  // C2033 };  
```  
  
 考えられる解決策:  
  
```  
// C2033b.cpp // compile with: /c struct S { int b : 1; };  
```