---
title: "num_threads | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "num_threads"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "num_threads OpenMP clause"
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# num_threads
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

スレッドのスレッドの数を設定します。  
  
## 構文  
  
```  
num_threads(num)  
```  
  
## 解説  
 指定項目  
  
 `num`  
 スレッドの数  
  
## 解説  
 `num_threads` の句に [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) の関数と同じ機能があります。  
  
 `num_threads` は次のディレクティブに対象 :  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../Topic/for%20\(OpenMP\).md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、「[2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md)」を参照してください。  
  
## 使用例  
 `num_threads` 句の使用例については[parallel](../../../parallel/openmp/reference/parallel.md) を参照してください。  
  
## 参照  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)