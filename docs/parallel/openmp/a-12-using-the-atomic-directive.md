---
title: "Atomic ディレクティブを使用して A.12 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 12c6467ee3233ce5d36d131ec81072bab8b841fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="a12---using-the-atomic-directive"></a>A.12 atomic ディレクティブの使用
次の例は、競合状態を回避できます (の要素の同時更新*x*複数のスレッドで) を使用して、`atomic`ディレクティブ ([セクション 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) 19 ページ上)。  
  
```  
#pragma omp parallel for shared(x, y, index, n)  
    for (i=0; i<n; i++)   
    {  
        #pragma omp atomic  
            x[index[i]] += work1(i);  
        y[i] += work2(i);  
    }  
```  
  
 使用する利点、`atomic`この例ではディレクティブは、並列で実行する x の 2 つの要素を更新できます。 場合、`critical`ディレクティブ ([セクション 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) 18 ページ) の要素をすべて更新して代わりに、使用された*x*逐次的に (ただし、いずれかではなく、順序を保証) 実行されます。  
  
 なお、`atomic`ディレクティブは、C または C++ ステートメントの直後にのみ適用されます。  その結果、要素の*y*この例ではアトミックに更新されません。