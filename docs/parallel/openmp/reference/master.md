---
title: "master | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "master"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "master OpenMP directive"
ms.assetid: 559ed974-e02a-486e-a23f-31556429b2c4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# master
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

マスターの threadshould だけプログラムのセクションを実行することを指定します。  
  
## 構文  
  
```  
#pragma omp master  
{  
   code_block  
}  
```  
  
## 解説  
 **マスター**  のディレクティブはOpenMP 句をサポートしていません。  
  
 一つのディレクティブはマスター スレッド コードのセクションをシングル スレッドで実行することを指定できるようにします。  
  
 詳細については、「[2.6.1 master Construct](../../../parallel/openmp/2-6-1-master-construct.md)」を参照してください。  
  
## 使用例  
  
```  
// omp_master.cpp  
// compile with: /openmp   
#include <omp.h>  
#include <stdio.h>  
  
int main( )   
{  
    int a[5], i;  
  
    #pragma omp parallel  
    {  
        // Perform some computation.  
        #pragma omp for  
        for (i = 0; i < 5; i++)  
            a[i] = i * i;  
  
        // Print intermediate results.  
        #pragma omp master  
            for (i = 0; i < 5; i++)  
                printf_s("a[%d] = %d\n", i, a[i]);  
  
        // Wait.  
        #pragma omp barrier  
  
        // Continue with the computation.  
        #pragma omp for  
        for (i = 0; i < 5; i++)  
            a[i] += i;  
    }  
}  
```  
  
  **a \[0\] \= 0**  
**a \[1\] \= 1**  
**a \[2\] \= 4**  
**a \[3\] \= 9**  
**a \[4\] \= 16**   
## 参照  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)