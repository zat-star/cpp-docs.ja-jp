---
title: "コンパイラ エラー C3008 | Microsoft Docs"
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
  - "C3008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3008"
ms.assetid: 04d93201-28e5-4be0-945c-aad616376f4b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg' : OpenMP 'directive' ディレクティブで、引数の終わりに '\)' がありません  
  
 引数を受け取る OpenMP ディレクティブに、閉じかっこがありませんでした。  
  
 次の例では C3008 が生成されます。  
  
```  
// C3008.c // compile with: /openmp int main() { int x, y, z; #pragma omp parallel shared(x   // C3008 // Try the following line instead: #pragma omp parallel shared(x) { } }  
```