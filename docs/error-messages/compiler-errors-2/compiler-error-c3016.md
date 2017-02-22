---
title: "コンパイラ エラー C3016 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3016"
ms.assetid: 3423467e-e8bb-4f35-b4db-7925cafa74c1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C3016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': OpenMP 'for' ステートメントのインデックス変数は、符号付きの整数型を含んでいなければなりません  
  
 OpenMP `for` ステートメントのインデックス変数は、符号付きの整数型である必要があります。  
  
 次の例では C3016 が生成されます。  
  
```  
// C3016.cpp // compile with: /openmp int main() { #pragma omp parallel { unsigned int i = 0; // Try the following line instead: // int i = 0; #pragma omp for for (i = 0; i <= 10; ++i)   // C3016 { } } }  
```