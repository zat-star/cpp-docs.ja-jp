---
title: "omp_set_nest_lock |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_set_nest_lock
dev_langs: C++
helpviewer_keywords: omp_set_nest_lock OpenMP function
ms.assetid: b98ed889-ff8e-4217-a3e9-3993ed8699af
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b5393c937520eeb76acff0149949077205115f5f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ompsetnestlock"></a>omp_set_nest_lock
ロックが利用可能になるまで、スレッドの実行をブロックします。  
  
## <a name="syntax"></a>構文  
  
```  
void omp_set_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `lock`  
 型の変数[omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md)で初期化された[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)です。  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [3.2.3 omp_set_lock 関数と omp_set_nest_lock 関数](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)です。  
  
## <a name="examples"></a>例  
 参照してください[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)の使用例については`omp_set_nest_lock`します。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)