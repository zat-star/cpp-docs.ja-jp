---
title: "omp_get_nested |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_get_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_get_nested OpenMP function
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df6a3fafdb749031ae5e55a58e1e26ccad76985c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ompgetnested"></a>omp_get_nested
入れ子になった並列処理が有効になっているかどうかを示す値を返します。  
  
## <a name="syntax"></a>構文  
  
```  
int omp_get_nested( );  
```  
  
## <a name="return-value"></a>戻り値  
 ゼロ以外の場合は、入れ子になった並列化が有効にします。  
  
## <a name="remarks"></a>コメント  
 入れ子になった並列処理を指定した[omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)と[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)です。  
  
 詳細については、次を参照してください。 [3.1.10 omp_get_nested 関数](../../../parallel/openmp/3-1-10-omp-get-nested-function.md)です。  
  
## <a name="example"></a>例  
 参照してください[omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)の使用例については`omp_get_nested`します。  
  
## <a name="see-also"></a>参照  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)