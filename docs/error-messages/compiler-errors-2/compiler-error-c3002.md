---
title: "コンパイラ エラー C3002 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3002"
ms.assetid: 2d4241a7-c8eb-4d43-a128-dca255d137bc
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name1 name2' : 複数の OpenMP ディレクティブ名が存在します  
  
 複数のディレクティブ名を指定することはできません。  
  
 次の例では C3002 が生成されます。  
  
```  
// C3002.c // compile with: /openmp int main() { #pragma omp parallel single   // C3002 }  
```