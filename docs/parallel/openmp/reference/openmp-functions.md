---
title: "OpenMP Functions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OpenMP Functions
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

OpenMP API で使用される関数へのリンクを示します。  
  
 OpenMP 標準の Visual C\+\+ の実装は次の機能が含まれています。  
  
|Function|Description|  
|--------------|-----------------|  
|[omp\_destroy\_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)|ロックの状態に戻します。|  
|[omp\_destroy\_nest\_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)|入れ子にできるロック状態に戻します。|  
|[omp\_get\_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md)|後続の並列領域で使用できるスレッドの数が実行時までに調整できる示す値を返します。|  
|[omp\_get\_max\_threads](../Topic/omp_get_max_threads.md)|同じまたは [num\_threads](../../../parallel/openmp/reference/num-threads.md) の並列領域がない場合にコードで定義するために使用できるスレッドの数より大きい整数を返します。|  
|[omp\_get\_nested](../../../parallel/openmp/reference/omp-get-nested.md)|入れ子になった並列化が有効かを示す値を返します。|  
|[omp\_get\_num\_procs](../../../parallel/openmp/reference/omp-get-num-procs.md)|関数が呼び出されたときに使用できるプロセッサの数を返します。|  
|[omp\_get\_num\_threads](../Topic/omp_get_num_threads.md)|並列領域のスレッドの数を返します。|  
|[omp\_get\_thread\_num](../../../parallel/openmp/reference/omp-get-thread-num.md)|スレッドのチーム内で実行されるスレッドのスレッド数を返します。|  
|[omp\_get\_wtick](../Topic/omp_get_wtick.md)|プロセッサのクロックのタイマー刻みの間隔の秒数を返します。|  
|[omp\_get\_wtime](../../../parallel/openmp/reference/omp-get-wtime.md)|時刻の秒の部分が経過する位置を返します。|  
|[omp\_in\_parallel](../../../parallel/openmp/reference/omp-in-parallel.md)|内部から呼び出された場合並列領域以外を返します。|  
|[omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md)|単純ロックを初期化します。|  
|[omp\_init\_nest\_lock](../Topic/omp_init_nest_lock.md)|ロックを初期化します。|  
|[omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)|後続の並列領域で使用できるスレッドの数が実行時までに調整できることを示します。|  
|[omp\_set\_lock](../../../parallel/openmp/reference/omp-set-lock.md)|ロックが使用可能になるまでスレッドの実行をブロックします。|  
|[omp\_set\_nest\_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)|ロックが使用可能になるまでスレッドの実行をブロックします。|  
|[omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md)|入れ子になった並列化を有効にします。|  
|[omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)|[num\_threads](../../../parallel/openmp/reference/num-threads.md) の句によってオーバーライドされると以降の並列領域のスレッドの数を設定しません。|  
|[omp\_test\_lock](../../../parallel/openmp/reference/omp-test-lock.md)|ロックを設定しようとするとスレッドが実行をブロックします。|  
|[omp\_test\_nest\_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)|入れ子にできるロックを設定しようとするとスレッドが実行をブロックします。|  
|[omp\_unset\_lock](../../../parallel/openmp/reference/omp-unset-lock.md)|ロックを解除します。|  
|[omp\_unset\_nest\_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)|入れ子にできるロックを解除します。|  
  
## 参照  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)