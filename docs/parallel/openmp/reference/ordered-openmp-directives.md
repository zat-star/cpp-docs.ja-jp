---
title: "ordered (OpenMP Directives) | Microsoft Docs"
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
  - "ordered"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ordered OpenMP directive"
ms.assetid: e1aa703e-d07d-4f6a-9b2a-f4f25203d850
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ordered (OpenMP Directives)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

FOR ループを並列化して中のコードでは順次ループとして実行することを指定します。  
  
## 構文  
  
```  
#pragma omp ordered  
   structured-block  
```  
  
## 解説  
 **順序あり**  のディレクティブは  **順序あり**  の句を使用して [for](../Topic/for%20\(OpenMP\).md) または構造体の動的  **並列の**  の範囲内である必要があります。  
  
 **順序あり**  のディレクティブはOpenMP 句をサポートしていません。  
  
 詳細については、「[2.6.6 ordered Construct](../../../parallel/openmp/2-6-6-ordered-construct.md)」を参照してください。  
  
## 使用例  
  
```  
// omp_ordered.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
static float a[1000], b[1000], c[1000];  
  
void test(int first, int last)   
{  
    #pragma omp for schedule(static) ordered  
    for (int i = first; i <= last; ++i) {  
        // Do something here.  
        if (i % 2)   
        {  
            #pragma omp ordered   
            printf_s("test() iteration %d\n", i);  
        }  
    }  
}  
  
void test2(int iter)   
{  
    #pragma omp ordered  
    printf_s("test2() iteration %d\n", iter);  
}  
  
int main( )   
{  
    int i;  
    #pragma omp parallel  
    {  
        test(1, 8);  
        #pragma omp for ordered  
        for (i = 0 ; i < 5 ; i++)  
            test2(i);  
    }  
}  
```  
  
  **\(\) イテレーション 1 をテストします。**  
**\(\) イテレーション 3 をテストします。**  
**\(\) イテレーション 5 をテストします。**  
**\(\) イテレーション 7 をテストします。**  
**test2 \(\) イテレーション 0**   
**test2 \(\) イテレーション 1**   
**test2 \(\) イテレーション 2**   
**test2 \(\) イテレーション 3**   
**test2 \(\) イテレーション 4**    
## 参照  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)