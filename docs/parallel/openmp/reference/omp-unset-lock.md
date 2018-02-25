---
title: "omp_unset_lock 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_unset_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_unset_lock OpenMP function
ms.assetid: 68fcb728-040b-4bad-979e-aaecb9097a4e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0a2809bbf31a283fe19f707a94363309616afcee
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
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