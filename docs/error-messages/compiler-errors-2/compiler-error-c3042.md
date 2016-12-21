---
title: "コンパイラ エラー C3042 | Microsoft Docs"
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
  - "C3042"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3042"
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3042
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'copyprivate' 句および 'nowait' 句は、OpenMP 'directive' ディレクティブで同時に使用することはできません  
  
 [copyprivate](../Topic/copyprivate.md) 句と [nowait](../../parallel/openmp/reference/nowait.md) 句は、指定されたディレクティブでは同時に使用できません。 このエラーを解決するには、`copyprivate` 句か `nowait` 句の一方または両方を削除します。  
  
 次の例では C3042 が生成されます。  
  
```  
// C3042.cpp // compile with: /openmp /c #include <stdio.h> #include "omp.h" double d; int main() { #pragma omp parallel private(d) { #pragma omp single copyprivate(d) nowait   // C3042 { } } }  
```