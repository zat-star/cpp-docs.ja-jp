---
title: "3.2 Lock Functions | Microsoft Docs"
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
ms.assetid: 0ec855c6-55a9-49d7-bee4-5edae6e86a1b
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2 Lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このセクションで説明する関数は同期に使用するロックを処理します。  
  
 次の関数に対してロック変数は型 **omp\_lock\_t** が必要です。  この変数はこれらの関数によってアクセスがあります。  すべてのロック機能は **omp\_lock\_t** の型へのポインターを持つ引数が必要です。  
  
-   `omp_init_lock` の関数は単純ロックを初期化します。  
  
-   `omp_destroy_lock` の関数は単純ロックを削除します。  
  
-   `omp_set_lock` の関数は単純ロックが使用可能になるまで待機します。  
  
-   `omp_unset_lock` の関数は単純ロックを解除します。  
  
-   関数の `omp_test_lock` テスト単純ロック。  
  
 次の関数に対してロック変数は型 **omp\_nest\_lock\_t** が必要です。  この変数はこれらの関数によってアクセスがあります。  すべての入れ子にできるロック ロック機能は **omp\_nest\_lock\_t** の型へのポインターを持つ引数が必要です。  
  
-   `omp_init_nest_lock` の関数は入れ子にできるロックを初期化します。  
  
-   `omp_destroy_nest_lock` の関数は入れ子にできるロックを削除します。  
  
-   `omp_set_nest_lock` の関数は入れ子にできるロックが使用可能になるまで待機します。  
  
-   `omp_unset_nest_lock` の関数は入れ子にできるロックを解除します。  
  
-   テスト `omp_test_nest_lock` の関数入れ子にできるロック。  
  
 OpenMP のロック機能はロック変数の現在の値を常に読み取り更新するようにロック変数にアクセスします。  したがってOpenMP のプログラムがロック変数の値が異なるスレッド間で一貫していることを確認するに  **フラッシュ**  の明示的なディレクティブを含める必要はありません。  \(他の変数の値をする一貫した方法で  **フラッシュ**  のディレクティブが必要になる場合があります\)。