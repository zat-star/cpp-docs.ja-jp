---
title: "A.15   Determining the Number of Threads Used | Microsoft Docs"
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
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.15   Determining the Number of Threads Used
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次の正しくない例について考えます \(ページの 37 [セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) の場合\):  
  
```  
np = omp_get_num_threads(); // misplaced   
#pragma omp parallel for schedule(static)  
    for (i=0; i<np; i++)  
        work(i);  
```  
  
 `omp_get_num_threads()` の呼び出しはコードの逐次刊行物係の 1 を返します。したがって *np は* 前の例の 1 と常に等しくなります。  並列領域に配置されるスレッドの数を確認するにはの呼び出しが並列領域の内部にある必要があります。  
  
 次の例はスレッドの数のクエリを含まないでこのプログラムを記述する方法を示しています :  
  
```  
#pragma omp parallel private(i)  
{  
    i = omp_get_thread_num();  
    work(i);  
}  
```