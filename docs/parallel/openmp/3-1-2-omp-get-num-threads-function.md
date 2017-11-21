---
title: "3.1.2 omp_get_num_threads 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7b832cd4e4e44706bbd4ffc63b5912f941bb0ca6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 omp_get_num_threads 関数
**Omp_get_num_threads**関数現在を返しますスレッドの数、並列領域の呼び出し元を実行するチームにします。 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_num_threads(void);  
```  
  
 **Num_threads**句、 **omp_set_num_threads**関数、および**OMP_NUM_THREADS**環境変数は、チーム内のスレッドの数を制御します。  
  
 スレッドの数が設定されていない場合に明示的にユーザーが、既定値は、実装定義します。 この関数に、最も近い外側にあるバインド**並列**ディレクティブです。 呼び出された場合、プログラムのシリアル部分から、またはシリアル化される入れ子になった並列領域から、この関数は 1 を返します。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **OMP_NUM_THREADS**環境変数を参照してください[セクション 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 48 ページ。  
  
-   **num_threads**句を参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページのです。  
  
-   **並列**構築を参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページのです。