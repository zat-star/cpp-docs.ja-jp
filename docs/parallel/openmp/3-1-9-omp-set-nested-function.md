---
title: "3.1.9 omp_set_nested Function | Microsoft Docs"
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
ms.assetid: e4afc3aa-bb96-4314-9849-fd5df5f437d9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.9 omp_set_nested Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**omp\_set\_nested** の関数は入れ子になった並列化を有効または無効にします。  形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_set_nested(int nested);  
```  
  
 *入り込まれたら*  0 になり既定では入れ子になった並列領域を現在のスレッドによってシリアル化され実行されます入れ子になった並列化が無効になります。   *入り込まれたら*  以外の値になり入れ子になった並列化が有効になり入れ子になったチームは並列領域を作成するときに追加のスレッドを配置する場合があります。  
  
 プログラムの部分から呼び出されたとき **omp\_in\_parallel** 関数の戻り値をこの関数は前に説明した結果になります。  これは **omp\_in\_parallel** 関数の戻り値が以外の値この関数の動作は未定義にするプログラムの部分から呼び出されます。  
  
 この呼び出しに **OMP\_NESTED** の環境変数上の方が優先されます。  
  
 入れ子になった並列化を有効にすると入れ子になった並列領域を実行するために使用されるスレッドの数は実装定義されます。  その結果入れ子になった並列化が有効になっている場合でもOpenMP 対応実装が入れ子になった並列領域をシリアル化する。  
  
## cref:  
  
-   **OMP\_NESTED** の環境変数はページの 49 [セクション 4.4](../Topic/4.4%20OMP_NESTED.md) が表示されます。  
  
-   **omp\_in\_parallel** の関数はページの 38 [セクション 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) が表示されます。