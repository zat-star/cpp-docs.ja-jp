---
title: "4.2 OMP_NUM_THREADS | Microsoft Docs"
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
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4.2 OMP_NUM_THREADS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**OMP\_NUM\_THREADS** の環境変数は実行時に使用してその番号が **omp\_set\_num\_threads** のライブラリ ルーチンのメソッドまたは  **並列**  のディレクティブの **num\_threads** の明示的な句によって明示的に変更されていない場合スレッドの既定値を設定します。  
  
 **OMP\_NUM\_THREADS** の環境変数の値は正の整数である必要があります。  その効果がスレッド数の動的な変更が有効かどうかによって決まります。  スレッドの **OMP\_NUM\_THREADS** の環境変数と動的の間の相互作用に関する包括的な一連の規則ではページのセクション 2.3 8. を参照してください。  
  
 値が **OMP\_NUM\_THREADS** 環境変数に指定されていないか指定された値が正の整数でない場合または値がスレッドの最大数を超える場合はシステム サポート使用するスレッドの数は実装定義されます。  
  
 例:  
  
```  
setenv OMP_NUM_THREADS 16  
```  
  
## cref:  
  
-   **num\_threads** の句はページの 8. [セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) が表示されます。  
  
-   **omp\_set\_num\_threads** の関数はページの 36 [セクション 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) が表示されます。  
  
-   **omp\_set\_dynamic** の関数はページの 39 [セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) が表示されます。