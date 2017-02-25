---
title: "omp_unset_nest_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_unset_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_unset_nest_lock OpenMP function"
ms.assetid: 1721d061-3f9c-45d7-b479-a665cd0a121d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# omp_unset_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

入れ子にできるロックを解除します。  
  
## 構文  
  
```  
void omp_unset_nest_lock(   
   omp_nest_lock_t *lock   
);  
```  
  
## 解説  
 指定項目  
  
 `lock`  
 [omp\_init\_nest\_lock](../Topic/omp_init_nest_lock.md) と関数のスレッドを実行して所有する型の変数初期化 [omp\_nest\_lock\_t](../Topic/omp_nest_lock_t.md)。  
  
## 解説  
 詳細については、「[3.2.4 omp\_unset\_lock and omp\_unset\_nest\_lock Functions](../Topic/3.2.4%20omp_unset_lock%20and%20omp_unset_nest_lock%20Functions.md)」を参照してください。  
  
## 使用例  
 `omp_unset_nest_lock` 使用例については[omp\_init\_nest\_lock](../Topic/omp_init_nest_lock.md) を参照してください。  
  
## 参照  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)