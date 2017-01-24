---
title: "omp_test_lock | Microsoft Docs"
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
  - "omp_test_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_test_lock OpenMP function"
ms.assetid: 314ca85e-0749-4c16-800f-b0f36fed256d
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_test_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

ロックを設定しようとするとスレッドが実行をブロックします。  
  
## 構文  
  
```  
int omp_test_lock(  
   omp_lock_t *lock  
);  
```  
  
## 解説  
 指定項目  
  
 `lock`  
 [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md) 型の変数を初期化 [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md)。  
  
## 解説  
 詳細については、「[3.2.5 omp\_test\_lock and omp\_test\_nest\_lock Functions](../Topic/3.2.5%20omp_test_lock%20and%20omp_test_nest_lock%20Functions.md)」を参照してください。  
  
## 使用例  
  
```  
// omp_test_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t simple_lock;                   
  
int main() {  
    omp_init_lock(&simple_lock);  
  
    #pragma omp parallel num_threads(4)  
    {  
        int tid = omp_get_thread_num();  
  
        while (!omp_test_lock(&simple_lock))  
            printf_s("Thread %d - failed to acquire simple_lock\n",  
                     tid);  
  
        printf_s("Thread %d - acquired simple_lock\n", tid);  
  
        printf_s("Thread %d - released simple_lock\n", tid);  
        omp_unset_lock(&simple_lock);  
    }  
  
    omp_destroy_lock(&simple_lock);  
}  
```  
  
  **スレッド 1 の派生 simple\_lock**   
**スレッド 1 で解放された simple\_lock**   
**スレッド 0 ~ simple\_lock を回避できます。**  
**スレッド 3 ~ simple\_lock を回避できます。**  
**スレッド 0 ~ simple\_lock を回避できます。**  
**スレッド 3 ~ simple\_lock を回避できます。**  
**スレッド 2 の派生 simple\_lock**   
**スレッド 0 ~ simple\_lock を回避できます。**  
**スレッド 3 ~ simple\_lock を回避できます。**  
**スレッド 0 ~ simple\_lock を回避できます。**  
**スレッド 3 ~ simple\_lock を回避できます。**  
**スレッド 2 で解放された simple\_lock**   
**スレッド 0 ~ simple\_lock を回避できます。**  
**スレッド 3 ~ simple\_lock を回避できます。**  
**スレッド 0 の派生 simple\_lock**   
**スレッド 3 ~ simple\_lock を回避できます。**  
**スレッド 0 で解放された simple\_lock**   
**スレッド 3 ~ simple\_lock を回避できます。**  
**スレッド 3 の派生 simple\_lock**   
**スレッド 3 で解放された simple\_lock**    
## 参照  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)