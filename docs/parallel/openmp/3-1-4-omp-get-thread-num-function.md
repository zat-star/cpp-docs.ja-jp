---
title: "3.1.4 omp_get_thread_num Function | Microsoft Docs"
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
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.4 omp_get_thread_num Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`omp_get_thread_num` 関数の戻り値はスレッド番号関数を実行するスレッドにチーム内で。  スレッド番号は 0 と **omp\_get\_num\_threads \(\)**1 –中に包括的です。  チームのマスター スレッドはスレッド 0 です。  
  
 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_thread_num(void);  
```  
  
 シリアル領域から呼び出された場合`omp_get_thread_num` は 0 を返します。  から呼び出された場合という入れ子になった並列領域は0 が返されます。  
  
## cref:  
  
-   `omp_get_num_threads` の関数はページの 37 [セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) が表示されます。