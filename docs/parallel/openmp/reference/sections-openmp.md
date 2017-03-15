---
title: "sections (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "section"
  - "SECTIONS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sections OpenMP directive"
ms.assetid: 4cd1d776-e198-470e-930a-01fb0ab0a0bd
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# sections (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

すべてのスレッドに分割できます。コード例を示します。  
  
## 構文  
  
```  
#pragma omp [parallel] sections [clauses]  
{  
   #pragma omp section  
   {  
      code_block   
   }   
}  
```  
  
## 解説  
 指定項目  
  
 `clause` \(省略可能\)  
 ゼロ以上の句。   **セクション**  でサポートされる用語のリストについては" 解説 " を参照してください。  
  
## 解説  
 **セクション**  のディレクティブは  **セクション**  を指定できます。また詳細にディレクティブを含める。  
  
 **セクション**  の OpenMP のディレクティブは次の句をサポートします :  
  
-   [firstprivate](../Topic/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
 **並列**  も指定されている場合`clause` は `nowait` を除く  **並列**  または  **セクション**  のディレクティブによって使用される句になります。  
  
 詳細については、「[2.4.2 sections Construct](../../../parallel/openmp/2-4-2-sections-construct.md)」を参照してください。  
  
## 使用例  
  
```  
// omp_sections.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
    #pragma omp parallel sections num_threads(4)  
    {  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
        #pragma omp section  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
    }  
}  
```  
  
  **Hello スレッドから 0**   
**Hello スレッドから 0**    
## 参照  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)