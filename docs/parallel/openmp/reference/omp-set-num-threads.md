---
title: "omp_set_num_threads | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_set_num_threads"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_num_threads OpenMP function"
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# omp_set_num_threads
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

[num\_threads](../../../parallel/openmp/reference/num-threads.md) の句によってオーバーライドされると以降の並列領域のスレッドの数を設定しません。  
  
## 構文  
  
```  
void omp_set_num_threads(  
   int num_threads  
);  
```  
  
## 解説  
 指定項目  
  
 `num_threads`  
 並列領域のスレッドの数。  
  
## 解説  
 詳細については、「[3.1.1 omp\_set\_num\_threads Function](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)」を参照してください。  
  
## 使用例  
 `omp_set_num_threads` 使用例については[omp\_get\_num\_threads](../Topic/omp_get_num_threads.md) を参照してください。  
  
## 参照  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)