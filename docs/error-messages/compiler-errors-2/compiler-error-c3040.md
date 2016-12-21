---
title: "コンパイラ エラー C3040 | Microsoft Docs"
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
  - "C3040"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3040"
ms.assetid: 29e857ac-74f0-4ec6-becf-9026e38c160e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3040
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': 'reduction' 句の変数の型は、減少演算子 'operator' と互換性がありません  
  
 [reduction](../../parallel/openmp/reference/reduction.md) 句内の変数は、減少演算子では使用できません。  
  
 次の例では C3040 が生成されます。  
  
```  
// C3040.cpp // compile with: /openmp /c #include "omp.h" double d; int main() { #pragma omp parallel reduction(&:d)   // C3040 ; #pragma omp parallel reduction(-:d)  // OK ; }  
```