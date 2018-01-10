---
title: "omp_unset_lock 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_unset_lock
dev_langs: C++
helpviewer_keywords: omp_unset_lock OpenMP function
ms.assetid: 68fcb728-040b-4bad-979e-aaecb9097a4e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5dae4888176807ba2d3a3356d71c55eb82f2a55c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ompunsetlock"></a>omp_unset_lock
ロックを解放します。  
  
## <a name="syntax"></a>構文  
  
```  
void omp_unset_lock(  
   omp_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `lock`  
 型の変数[omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md)で初期化された[omp_init_lock 関数](../../../parallel/openmp/reference/omp-init-lock.md)スレッドによって所有されている、および関数で実行します。  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [3.2.4 omp_unset_lock 関数と omp_unset_nest_lock 関数](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)です。  
  
## <a name="example"></a>例  
 参照してください[omp_init_lock 関数](../../../parallel/openmp/reference/omp-init-lock.md)の使用例については`omp_unset_lock`します。  
  
## <a name="see-also"></a>参照  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)