---
title: "4.2 OMP_NUM_THREADS |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9c2b766d0e3be9b4f1d272a6e3fa205cfcb87039
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="42-ompnumthreads"></a>4.2 OMP_NUM_THREADS
**OMP_NUM_THREADS**環境変数がその番号が明示的に呼び出すことによって変更されない限り、既定の実行中に、使用するスレッド数を設定、 **omp_set_num_threads**ライブラリ ルーチンまたは明示的な**num_threads**句、**並列**ディレクティブです。  
  
 値、 **OMP_NUM_THREADS**環境変数は、正の整数を指定する必要があります。 その効果は、スレッドの数を動的に調整が有効になっているかどうかによって異なります。 間の相互作用についてのルールの包括的セット、 **OMP_NUM_THREADS**環境、スレッドの変数および動的な調整は、8 ページのセクションで 2.3 を参照してください。  
  
 値が指定されていない場合、 **OMP_NUM_THREADS**環境変数、または指定された値が正の整数ではないか、システムができる値がスレッドの最大数よりも大きい場合のサポートを使用するスレッドの数実装定義されます。  
  
 例:  
  
```  
setenv OMP_NUM_THREADS 16  
```  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **num_threads**句を参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページのです。  
  
-   **omp_set_num_threads**関数を参照してください[セクション 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)ページ 36 にします。  
  
-   **omp_set_dynamic**関数を参照してください[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)ページ 39 にします。