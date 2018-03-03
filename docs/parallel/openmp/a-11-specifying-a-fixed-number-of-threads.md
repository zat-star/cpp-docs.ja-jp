---
title: "固定のスレッド数を指定する A.11 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72c8aca2b90f021771ba9f9fc8a86d784ffe24a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="a11---specifying-a-fixed-number-of-threads"></a>A.11 固定数のスレッドの指定
一部のプログラムは、正常に実行するスレッドの固定、事前に指定された数に依存します。  スレッドの数を動的に調整の既定の設定は、実装定義であるために、このようなプログラムは、動的なスレッド機能をオフにして、移植性を保証するには、明示的にスレッドの数を設定を選択できます。 次の例では、これを行う方法を使用して`omp_set_dynamic`([セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 ページで)、および`omp_set_num_threads`([セクション 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 36 ページ上)。  
  
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
  
 この例では、プログラムの実行正しく 16 のスレッドによって実行される場合にのみです。 実装が 16 スレッドをサポートできない場合は、この例の動作は実装定義します。  
  
 動的なスレッドの設定に関係なく、並列領域の中に、並行領域を実行しているスレッドの数が一定に注意してください。 動的なスレッド メカニズムでは、並列領域の開始時に使用するスレッドの数を決定され、領域の中に維持されます。