---
title: "3.1.3 omp_get_max_threads Function | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.3 omp_get_max_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**num\_threads** 句のない並列領域がコードにある場合そのチームを形成するために使用するスレッドの数以上大きいことが保証される整数 **omp\_get\_max\_threads** の関数はを返します。  形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_max_threads(void);  
```  
  
 次に **omp\_get\_max\_threads** の値の下限を搭載しています :  
  
```  
  
threads-used-for-next-team  
 <= omp_get_max_threads  
  
```  
  
 スレッドの数を要求するために次の並列領域が **num\_threads** の句を使用した場合の結果 **omp\_get\_max\_threads** の下限により長いを保持することに注意してください。  
  
 **omp\_get\_max\_threads** 関数の戻り値が動的に次の並列領域でチームのすべてのスレッドに対して十分なメモリを割り当てるために使用できます。  
  
## cref:  
  
-   **omp\_get\_num\_threads** の関数はページの 37 [セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) が表示されます。  
  
-   **omp\_set\_num\_threads** の関数はページの 36 [セクション 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) が表示されます。  
  
-   **omp\_set\_dynamic** の関数はページの 39 [セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) が表示されます。  
  
-   **num\_threads** の句はページの 8. [セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) が表示されます。