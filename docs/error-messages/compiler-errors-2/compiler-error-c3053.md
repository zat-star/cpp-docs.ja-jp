---
title: "コンパイラ エラー C3053 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3053"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3053"
ms.assetid: ab9a25f3-e341-4f6e-8e69-069b4a963a64
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C3053
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : 'threadprivate' は、グローバルまたは静的データ項目にのみ有効です  
  
 [threadprivate](../Topic/threadprivate.md) に渡されるシンボルはグローバルと静的のどちらかでなければなりません。  
  
 次の例では C3053 が生成されます。  
  
```  
// C3053.cpp // compile with: /openmp void Test() { int x, y; #pragma omp threadprivate(x, y)   // C3053 #pragma omp parallel copyin(x, y) { x = y; } }  
```  
  
 考えられる解決策:  
  
```  
// C3053b.cpp // compile with: /openmp /LD int x, y; #pragma omp threadprivate(x, y) void Test() { #pragma omp parallel copyin(x, y) { x = y; } }  
```