---
title: "omp_get_dynamic |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_get_dynamic
dev_langs: C++
helpviewer_keywords: omp_get_dynamic OpenMP function
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2715b7b27871f6b6ee0449bf96b81bef727dd45b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ompgetdynamic"></a>omp_get_dynamic
実行時以降の並列領域で使用できるスレッドの数を調整することができるかどうかを示す値を返します。  
  
## <a name="syntax"></a>構文  
  
```  
int omp_get_dynamic();  
```  
  
## <a name="return-value"></a>戻り値  
 ゼロ以外の場合、スレッドを動的に調整が有効にします。  
  
## <a name="remarks"></a>コメント  
 スレッドの動的な調整を指定した[omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)と[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)です。  
  
 詳細については、次を参照してください。 [3.1.7 omp_set_dynamic 関数](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)です。  
  
## <a name="example"></a>例  
 参照してください[omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)の使用例については`omp_get_dynamic`します。  
  
## <a name="see-also"></a>参照  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)