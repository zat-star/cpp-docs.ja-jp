---
title: "A.11   Specifying a Fixed Number of Threads | Microsoft Docs"
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
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.11   Specifying a Fixed Number of Threads
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

あるプログラムはスレッドの固定事前に指定された数に正しく実行されるします。  スレッドの数を動的に調整の既定の設定では実装定義されているため動的なスレッドの機能をオフにし移植性を確認するスレッドの数を明示的に設定するにはこのようなプログラムを選択できます。  次の例に `omp_set_dynamic` ページの [セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) \(39\) を使用する方法およびページの `omp_set_num_threads` \(36\) を [セクション 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) する方法を示しています :  
  
```  
omp_set_dynamic(0);  
omp_set_num_threads(16);  
#pragma omp parallel shared(x, npoints) private(iam, ipoints)  
{  
    if (omp_get_num_threads() != 16)   
      abort();  
    iam = omp_get_thread_num();  
    ipoints = npoints/16;  
    do_by_16(x, iam, ipoints);  
}  
```  
  
 この例ではプログラムは 16 のスレッドによって実行された場合にのみ正しく実装します。  実装が 16 のスレッドをサポートする場合この例の動作は実装定義されます。  
  
 並列領域を実行するスレッド数が並列領域の間に設定しておく動的なスレッドの設定に関係なくことに注意してください。  動的なスレッドの機能は並列領域の開始時に使用するスレッドの数を確認し領域の期間に設定したとします。