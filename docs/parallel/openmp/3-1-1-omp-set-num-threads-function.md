---
title: "3.1.1 omp_set_num_threads Function | Microsoft Docs"
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
ms.assetid: b94cf2b5-8011-4a3b-ba56-676982642857
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.1 omp_set_num_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`omp_set_num_threads` の関数のセット `num_threads` の句を指定しない後続の並列領域に使用する既定のスレッドの数。  形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_set_num_threads(int num_threads);  
```  
  
 パラメーターの *num\_threads* の値が正の整数である必要があります。  その効果がスレッド数の動的な変更が有効かどうかによって決まります。  スレッドの `omp_set_num_threads` の関数と動的の間の相互作用に関する包括的な一連の規則ではページのセクション 2.3 8. を参照してください。  
  
 プログラムの部分から呼び出されたとき `omp_in_parallel` 関数の戻り値をこの関数は前に説明した結果になります。  これは `omp_in_parallel` 関数の戻り値が以外の値この関数の動作は未定義にするプログラムの部分から呼び出されます。  
  
 この呼び出しに `OMP_NUM_THREADS` の環境変数上の方が優先されます。  `omp_set_num_threads` を呼び出すか`OMP_NUM_THREADS` 環境変数を設定することによって設定できるスレッドの数の既定値は  **並列**  の一つのディレクティブで `num_threads` の句を指定して明示的にオーバーライドできます。  
  
## cref:  
  
-   `omp_set_dynamic` の関数はページの 39 [セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) が表示されます。  
  
-   `omp_get_dynamic` の関数はページの 40 [セクション 3.1.8](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md) が表示されます。  
  
-   `OMP_NUM_THREADS` の環境変数はページの 48 [セクション 4.2](../../parallel/openmp/4-2-omp-num-threads.md)ページのセクション 2.3 8. を参照してください。  
  
-   `num_threads` の句はページの 8 [セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) が表示されます。