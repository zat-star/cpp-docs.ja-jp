---
title: "if (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "if OpenMP clause"
ms.assetid: db5940b6-2414-4bf8-934d-3edd8393c0f8
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# if (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

ループを並列でもシリアル実行するかどうかを指定します。  
  
## 構文  
  
```  
if(expression)  
```  
  
## 解説  
 指定項目  
  
 `expression`  
 true に評価される場合 \(以外\)並列領域でコードが並列実行に必要な式。  式が FALSE と評価された場合 \(ゼロ\)並列領域ではシリアル実行されます \(シングル スレッドによって\)。  
  
## 解説  
 `if` は次のディレクティブに対象 :  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../Topic/for%20\(OpenMP\).md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、「[2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md)」を参照してください。  
  
## 使用例  
  
```  
// omp_if.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
void test(int val)  
{  
    #pragma omp parallel if (val)  
    if (omp_in_parallel())  
    {  
        #pragma omp single  
        printf_s("val = %d, parallelized with %d threads\n",  
                 val, omp_get_num_threads());  
    }  
    else  
    {  
        printf_s("val = %d, serialized\n", val);  
    }  
}  
  
int main( )  
{  
    omp_set_num_threads(2);  
    test(0);  
    test(2);  
}  
```  
  
  **val \= 0シリアル化されます。**  
**val \= 22 種類のスレッドに並列化します**   
## 参照  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)