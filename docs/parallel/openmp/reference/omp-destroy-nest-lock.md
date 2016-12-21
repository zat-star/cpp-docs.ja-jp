---
title: "omp_destroy_nest_lock | Microsoft Docs"
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
  - "omp_destroy_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_destroy_nest_lock OpenMP function"
ms.assetid: 0ab1352b-668f-43dd-b441-31ec4cc53e68
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_destroy_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

入れ子にできるロック状態に戻します。  
  
## 構文  
  
```  
void omp_destroy_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## 解説  
 指定項目  
  
 `lock`  
 [omp\_init\_nest\_lock](../Topic/omp_init_nest_lock.md) 型の変数を初期化 [omp\_nest\_lock\_t](../Topic/omp_nest_lock_t.md)。  
  
## 解説  
 詳細については、「[3.2.2 omp\_destroy\_lock and omp\_destroy\_nest\_lock Functions](../Topic/3.2.2%20omp_destroy_lock%20and%20omp_destroy_nest_lock%20Functions.md)」を参照してください。  
  
## 使用例  
 `omp_destroy_nest_lock` 使用例については[omp\_init\_nest\_lock](../Topic/omp_init_nest_lock.md) を参照してください。  
  
## 参照  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)