---
title: "3.1.2 omp_get_num_threads Function | Microsoft Docs"
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
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.2 omp_get_num_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**omp\_get\_num\_threads** 関数の戻り値とする並列領域を実行中のチーム現在のスレッドの数。  形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_num_threads(void);  
```  
  
 **num\_threads** の句**omp\_set\_num\_threads** の関数と **OMP\_NUM\_THREADS** 環境変数のコントロール チームのスレッドの数。  
  
 スレッドの数がユーザーによって明示的に設定されていない場合既定値は実装定義されます。  この関数は  **並列**  の最も近いのディレクティブにバインドします。  プログラムのシリアル化された部分この入れ子になった並列領域から呼び出される関数の戻り値。1.  
  
## cref:  
  
-   **OMP\_NUM\_THREADS** の環境変数はページの 48 [セクション 4.2](../../parallel/openmp/4-2-omp-num-threads.md) が表示されます。  
  
-   **num\_threads** の句はページの 8. [セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) が表示されます。  
  
-   **並列**  の構造はページの 8. [セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) が表示されます。