---
title: "OpenMP Environment Variables | Microsoft Docs"
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
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Environment Variables
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

OpenMP API で使用される環境変数へのリンクを示します。  
  
 OpenMP 標準の Visual C\+\+ の実装は次の環境変数が含まれています。  これらの環境変数がプログラムの起動時に読み込まれ値の変更時には無視されます \(たとえば[\_putenv、\_wputenv](../../../c-runtime-library/reference/putenv-wputenv.md) を使用します。  
  
|環境変数|Description|  
|----------|-----------------|  
|[OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|OpenMP の実行時の並列領域のスレッド数を調整できるかどうかを指定します。|  
|[OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md)|入れ子になった並列化が `omp_set_nested` を有効にするか無効か入れ子になった並列化が有効かどうかを指定します。|  
|[OMP\_NUM\_THREADS](../Topic/OMP_NUM_THREADS.md)|[omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) または [num\_threads](../../../parallel/openmp/reference/num-threads.md) によってオーバーライドされない限り並列領域のスレッドの最大数を設定しません。|  
|[OMP\_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|`schedule(runtime)` が `for` または `parallel for` のディレクティブで指定されると [schedule](../../../parallel/openmp/reference/schedule.md) 句の動作を変更します。|  
  
## 参照  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)