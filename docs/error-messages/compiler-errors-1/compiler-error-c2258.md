---
title: "コンパイラ エラー C2258 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2258"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2258"
ms.assetid: 105eaa87-befb-4ecb-9a3f-e09e14d2f5bf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2258
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

純粋仮想関数の宣言に構文上の誤りがあります、'\= 0' でなければなりません。  
  
 純粋仮想関数が正しくない構文で宣言されています。  
  
 次の例では C2258 が生成されます。  
  
```  
// C2258.cpp // compile with: /c class A { public: void virtual func1() = 1; // C2258 void virtual func2() = 0;   // OK };  
```