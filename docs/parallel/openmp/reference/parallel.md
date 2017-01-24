---
title: "parallel | Microsoft Docs"
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
  - "parallel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "parallel OpenMP directive"
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# parallel
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

複数のスレッドで同時に実行されるコードである並列領域を定義します。  
  
## 構文  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## 解説  
 指定項目  
  
 `clause` \(省略可能\)  
 ゼロ以上の句。   **並列**  でサポートされる用語のリストについては" 解説 " を参照してください。  
  
## 解説  
 **並列**  の OpenMP のディレクティブは次の句をサポートします :  
  
-   [copyin](../Topic/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../Topic/firstprivate.md)  
  
-   [if](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num\_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [shared](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **並列**  は[sections](../../../parallel/openmp/reference/sections-openmp.md) と [for](../Topic/for%20\(OpenMP\).md) のディレクティブで使用できます。  
  
 詳細については、「[2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md)」を参照してください。  
  
## 使用例  
 次の例ではスレッドの数を設定し並列領域を定義する方法を示します。  既定ではスレッドの数はコンピューターの論理プロセッサの数と同じになります。  したがってたとえば有効なハイパー スレッディングである 1 台の物理的なプロセッサが搭載されたコンピューターの場合2 種類の論理プロセッサおよび 2 のスレッドを使用します。  
  
```  
// omp_parallel.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(4)  
   {  
      int i = omp_get_thread_num();  
      printf_s("Hello from thread %d\n", i);  
   }  
}  
```  
  
  **Hello スレッドから 0**   
**Hello スレッドから 1**   
**Hello スレッドから 2**   
**Hello スレッドから 3**    
## コメント  
 出力順序が異なるコンピューターによって異なる場合があることに注意してください。  
  
## 参照  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)