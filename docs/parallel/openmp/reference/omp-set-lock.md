---
title: "omp_set_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_set_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_lock OpenMP function"
ms.assetid: ded839cb-ca19-403f-8622-eb52ce512d31
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# omp_set_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

ロックが使用可能になるまでスレッドの実行をブロックします。  
  
## 構文  
  
```  
void omp_set_lock(  
   omp_lock_t *lock  
);  
```  
  
## 解説  
 指定項目  
  
 `lock`  
 [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md) 型の変数を初期化 [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md)。  
  
## 解説  
 詳細については、「[3.2.3 omp\_set\_lock and omp\_set\_nest\_lock Functions](../Topic/3.2.3%20omp_set_lock%20and%20omp_set_nest_lock%20Functions.md)」を参照してください。  
  
## 例  
 `omp_set_lock` 使用例については[omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md) を参照してください。  
  
## 参照  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)