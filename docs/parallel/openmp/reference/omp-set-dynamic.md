---
title: "omp_set_dynamic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_set_dynamic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_dynamic OpenMP function"
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# omp_set_dynamic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

後続の並列領域で使用できるスレッドの数が実行時までに調整できることを示します。  
  
## 構文  
  
```  
void omp_set_dynamic(  
   int val  
);  
```  
  
## 解説  
 指定項目  
  
 `val`  
 後続の並列領域で使用できるスレッドの数はランタイムに調整できることを示します。  以外の場合ランタイムはランタイムが動的にスレッド数を調整するスレッド数を調整できます。  
  
## 解説  
 スレッドの数は [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) または [OMP\_NUM\_THREADS](../Topic/OMP_NUM_THREADS.md) によって設定された値を超えることはできません。  
  
 `omp_set_dynamic` の現在の設定を表示するに [omp\_get\_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md) を使用します。  
  
 `omp_set_dynamic` の設定は [OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md) 環境変数の設定をオーバーライドします。  
  
 詳細については、「[3.1.7 omp\_set\_dynamic Function](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)」を参照してください。  
  
## 使用例  
  
```  
// omp_set_dynamic.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main()   
{  
    omp_set_dynamic(9);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_dynamic( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_dynamic( ));  
        }  
}  
```  
  
  **1**  
**1**   
## 参照  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)