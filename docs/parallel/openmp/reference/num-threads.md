---
title: "num_threads |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: num_threads
dev_langs: C++
helpviewer_keywords: num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7289a843c33fbc9ba23d6006997dea8e09ba7c79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="numthreads"></a>num_threads
スレッドのチームのスレッドの数を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
num_threads(num)  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `num`  
 スレッドの数  
  
## <a name="remarks"></a>コメント  
 `num_threads`句と同じ機能には、 [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)関数。  
  
 `num_threads`次のディレクティブに適用されます。  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [セクション](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、次を参照してください。 [2.3 parallel コンストラクト](../../../parallel/openmp/2-3-parallel-construct.md)です。  
  
## <a name="example"></a>例  
 参照してください[並列](../../../parallel/openmp/reference/parallel.md)の使用例については`num_threads`句。  
  
## <a name="see-also"></a>参照  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)