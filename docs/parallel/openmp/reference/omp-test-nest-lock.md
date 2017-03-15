---
title: "omp_test_nest_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_test_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_test_nest_lock OpenMP function"
ms.assetid: 4c909bbe-80e0-4100-aca6-d415d7dc5294
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# omp_test_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

入れ子にできるロックを設定しようとするとスレッドが実行をブロックします。  
  
## 構文  
  
```  
int omp_test_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## 解説  
 指定項目  
  
 `lock`  
 [omp\_init\_nest\_lock](../Topic/omp_init_nest_lock.md) 型の変数を初期化 [omp\_nest\_lock\_t](../Topic/omp_nest_lock_t.md)。  
  
## 解説  
 詳細については、「[3.2.5 omp\_test\_lock and omp\_test\_nest\_lock Functions](../Topic/3.2.5%20omp_test_lock%20and%20omp_test_nest_lock%20Functions.md)」を参照してください。  
  
## 使用例  
  
```  
// omp_test_nest_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_nest_lock_t nestable_lock;      
  
int main() {  
   omp_init_nest_lock(&nestable_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int tid = omp_get_thread_num();  
      while (!omp_test_nest_lock(&nestable_lock))  
         printf_s("Thread %d - failed to acquire nestable_lock\n",  
                tid);  
  
      printf_s("Thread %d - acquired nestable_lock\n", tid);  
  
      if (omp_test_nest_lock(&nestable_lock)) {  
         printf_s("Thread %d - acquired nestable_lock again\n",  
                tid);  
         printf_s("Thread %d - released nestable_lock\n",   
                tid);  
         omp_unset_nest_lock(&nestable_lock);  
      }  
  
      printf_s("Thread %d - released nestable_lock\n", tid);  
      omp_unset_nest_lock(&nestable_lock);  
   }  
  
   omp_destroy_nest_lock(&nestable_lock);  
}  
```  
  
  **スレッド 1 の派生 nestable\_lock**   
**スレッド 0 ~ nestable\_lock を回避できます。**  
**スレッド 1 の派生 nestable\_lock 再度**  
**スレッド 0 ~ nestable\_lock を回避できます。**  
**スレッド 1 で解放された nestable\_lock**   
**スレッド 0 ~ nestable\_lock を回避できます。**  
**スレッド 1 で解放された nestable\_lock**   
**スレッド 0 ~ nestable\_lock を回避できます。**  
**スレッド 3 の派生 nestable\_lock**   
**スレッド 0 ~ nestable\_lock を回避できます。**  
**スレッド 3 の派生 nestable\_lock 再度**  
**スレッド 0 ~ nestable\_lock を回避できます。**  
**スレッド 2 ~ nestable\_lock を回避できます。**  
**スレッド 3 で解放された nestable\_lock**   
**スレッド 2 ~ nestable\_lock を回避できます。**  
**スレッド 3 で解放された nestable\_lock**   
**スレッド 2 ~ nestable\_lock を回避できます。**  
**スレッド 0 の派生 nestable\_lock**   
**スレッド 2 ~ nestable\_lock を回避できます。**  
**スレッド 2 ~ nestable\_lock を回避できます。**  
**スレッド 2 ~ nestable\_lock を回避できます。**  
**スレッド 0 の派生 nestable\_lock 再度**  
**スレッド 2 ~ nestable\_lock を回避できます。**  
**スレッド 0 で解放された nestable\_lock**   
**スレッド 2 ~ nestable\_lock を回避できます。**  
**スレッド 0 で解放された nestable\_lock**   
**スレッド 2 ~ nestable\_lock を回避できます。**  
**スレッド 2 の派生 nestable\_lock**   
**スレッド 2 の派生 nestable\_lock 再度**  
**スレッド 2 で解放された nestable\_lock**   
**スレッド 2 で解放された nestable\_lock**    
## 参照  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)