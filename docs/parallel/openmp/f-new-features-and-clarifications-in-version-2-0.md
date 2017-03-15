---
title: "F. New Features and Clarifications in Version 2.0 | Microsoft Docs"
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
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# F. New Features and Clarifications in Version 2.0
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この移動の付録は Version 1.0 と Version 2.0 で行われた OpenMP C\/C\+\+ の仕様への主な変更点について説明します。  次の項目は仕様に追加された新機能です :  
  
-   コンマはOpenMP のディレクティブ \(7\)[セクション 2.1](../Topic/2.1%20Directive%20Format.md) のページで使用できます。  
  
-   `num_threads` の句が追加されました。  この句はユーザーが parallel コンストラクト \(ページの場合特定のスレッドの数を 8\)[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 要求できるようにします。  
  
-   `threadprivate` のディレクティブはの静的なブロック スコープの変数 \(ページの 23[セクション 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md)\) に拡張されました。  
  
-   たとえばC99 可変長の配列は `private``firstprivate` と `lastprivate` の句 \(ページの 25[セクション 2.7.2](../Topic/2.7.2%20Data-Sharing%20Attribute%20Clauses.md)\) の一覧で完全な型でありしたがって指定の場所で完全な型を指定できます。  
  
-   並列領域のプライベート変数は入れ子になったディレクティブ \(ページの 25[セクション 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md)\) の再指定されたプライベートです。  
  
-   `copyprivate` の句が追加されました。  またチームのメンバーの 1 人から他のメンバーに値をブロードキャストにプライベート変数を使用するようにの機能を提供します。  これは値に対して共有変数を使用するにはこのような共有変数を提供することが困難になる場合は代わりになります \(たとえば各レベルで別の変数を必要とする再帰\)。  `copyprivate` の句は  **シングル**  のディレクティブ \(ページの 32[セクション 2.7.2.8](../Topic/2.7.2.8%20copyprivate.md)\) でのみ使用できます。  
  
-   MPI ルーチンのようなタイミング ルーチン `omp_get_wtick` と `omp_get_wtime` が追加されました。  これらの関数はクロックのタイミング [セクション 3.3.1](../../parallel/openmp/3-3-1-omp-get-wtime-function.md) \(柱とページの 45 ページの 44 [セクション 3.3.2](../Topic/3.3.2%20omp_get_wtick%20Function.md)\) を実行するために必要です。  
  
-   OpenMP C\/C\+\+ の実装で定義されている動作のリストを持つ付録が追加されました。  実装ではこのような場合の動作を定義および文書化する必要があります \(ページの 97[付録 E](../Topic/E.%20Implementation-Defined%20Behaviors%20in%20OpenMP%20C-C++.md)\)。  
  
-   次の変更はC\/C\+\+ の前に示す OpenMP API の固有の機能を明確にするかまたは修正するために実行されます :  
  
    -   `omp_in_parallel` がゼロ以外を返します `omp_set_nested` と `omp_set_dynamic` 場合の動作は未定義であることを明記しました \(ページの 39[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)ページの 40 [セクション 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md)\)。  
  
    -   入れ子になった並列が使用されることを明記ディレクティブの入れ子 \(33 ページ [セクション 2.9](../../parallel/openmp/2-9-directive-nesting.md)\)。  
  
    -   ロック初期化およびロックのデストラクション関数は並列領域 \(ページの 42[セクション 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)ページの 42 [セクション 3.2.2](../Topic/3.2.2%20omp_destroy_lock%20and%20omp_destroy_nest_lock%20Functions.md)\) で呼び出すことができます。  
  
    -   新しい例が追加されました \(ページの 51[付録 A](../Topic/A.%20Examples.md)\)。