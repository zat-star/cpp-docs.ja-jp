---
title: "コンパイラ エラー C3018 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3018"
ms.assetid: 685be45f-f116-43a8-a88d-05ab6616e2f1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C3018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var1' : OpenMP 'for' テストまたはインクリメントは、インデックス変数 'var2' を使用しなければなりません  
  
 OpenMP ステートメント内の `for` ループは、インデックスに使用するときのように、テストとインクリメントに同じ変数を使用する必要があります。  
  
 次の例では C3018 が生成されます。  
  
```  
// C3018.cpp // compile with: /openmp int main() { int i = 0, j = 5; #pragma omp parallel { #pragma omp for for (i = 0; j < 10; ++i)   // C3018 // try the the following line instead // for (i = 0; i < 10; ++i) j *= 2; #pragma omp for for (i = 0; i < 10; j = j + i)   // C3018 // try the the following line instead // for (i = 0; i < 10; i = j + i) j *= 2; } }  
```