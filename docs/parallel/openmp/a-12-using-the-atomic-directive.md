---
title: "A.12   Using the atomic Directive | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.12   Using the atomic Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次の例では `atomic` のディレクティブ \(ページの 19[セクション 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md)\) を使用して競合状態 \(複数のスレッドによって *x* の要素の同時更新が行われません\):  
  
```  
#pragma omp parallel for shared(x, y, index, n)  
    for (i=0; i<n; i++)   
    {  
        #pragma omp atomic  
            x[index[i]] += work1(i);  
        y[i] += work2(i);  
    }  
```  
  
 この例で `atomic` のディレクティブを使用する利点は x の 2 種類の要素の更新が同時に実行されるようにすることです。  `critical` のディレクティブ \(ページの 18[セクション 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md)\) が代わりに使用すると*x* の要素に対するすべての更新は連続的に実行されます \(ただしどの保証される順序になります\)。  
  
 `atomic` のディレクティブとそれに続く C または C\+\+ のステートメントのみであることに注意してください。  したがって*y* の要素はこの例でアトミックには更新されません。