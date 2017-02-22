---
title: "omp_unset_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_unset_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_unset_lock OpenMP function"
ms.assetid: 68fcb728-040b-4bad-979e-aaecb9097a4e
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# omp_unset_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

ロックを解除します。  
  
## 構文  
  
```  
void omp_unset_lock(  
   omp_lock_t *lock  
);  
```  
  
## 解説  
 指定項目  
  
 `lock`  
 [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md) と関数のスレッドを実行して所有する型の変数初期化 [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md)。  
  
## 解説  
 詳細については、「[3.2.4 omp\_unset\_lock and omp\_unset\_nest\_lock Functions](../Topic/3.2.4%20omp_unset_lock%20and%20omp_unset_nest_lock%20Functions.md)」を参照してください。  
  
## 使用例  
 `omp_unset_lock` 使用例については[omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md) を参照してください。  
  
## 参照  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)