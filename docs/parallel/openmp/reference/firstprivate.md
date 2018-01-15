---
title: "firstprivate |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: firstprivate
dev_langs: C++
helpviewer_keywords: firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c7d4a5ba23e343f7858bf3320ed05ebce84f1c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="firstprivate"></a>firstprivate
Parallel コンストラクトの前に存在するために、各スレッドは、変数の独自のインスタンスである必要があり、変数の値を持つ変数を初期化する必要がありますを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
firstprivate(var)  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`var`|各スレッド内のインスタンスを持つ変数は、parallel コンストラクトの前に存在するために、変数の値で初期化されます。 複数の変数が指定されている場合は、変数名をコンマで区切ります。|  
  
## <a name="remarks"></a>コメント  
  
## <a name="remarks"></a>コメント  
 `firstprivate`次のディレクティブに適用されます。  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [セクション](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../../../parallel/openmp/reference/single.md)  
  
 詳細については、次を参照してください。 [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md)です。  
  
## <a name="example"></a>例  
 使用する例については`firstprivate`、例を参照してください[プライベート](../../../parallel/openmp/reference/private-openmp.md)です。  
  
## <a name="see-also"></a>参照  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)