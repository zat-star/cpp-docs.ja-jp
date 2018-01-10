---
title: "omp_set_num_threads |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_set_num_threads
dev_langs: C++
helpviewer_keywords: omp_set_num_threads OpenMP function
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 49383e47c161c7cec59f3f0fb7c618f4c4924655
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ompsetnumthreads"></a>omp_set_num_threads
オーバーライドされない限り、後続の並列領域で、スレッドの数を設定、 [num_threads](../../../parallel/openmp/reference/num-threads.md)句。  
  
## <a name="syntax"></a>構文  
  
```  
void omp_set_num_threads(  
   int num_threads  
);  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `num_threads`  
 並行領域内のスレッドの数。  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [3.1.1 omp_set_num_threads 関数](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)です。  
  
## <a name="example"></a>例  
 参照してください[omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)の使用例については`omp_set_num_threads`します。  
  
## <a name="see-also"></a>参照  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)