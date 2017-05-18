---
title: "firstprivate |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- firstprivate
dev_langs:
- C++
helpviewer_keywords:
- firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 03bea93209428a0edbd4c87779d46c633bbe6259
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="firstprivate"></a>firstprivate
Parallel コンストラクトの前に存在するために、各スレッドが、変数の独自のインスタンスを持つことと、変数の値を持つ、変数を初期化する必要がありますを指定します。  
  
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
  
-   [並列](../../../parallel/openmp/reference/parallel.md)  
  
-   [セクション](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [1 つ](../../../parallel/openmp/reference/single.md)  
  
 詳細については、次を参照してください。 [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md)します。  
  
## <a name="example"></a>例  
 使用する例については`firstprivate`、例を参照して[プライベート](../../../parallel/openmp/reference/private-openmp.md)します。  
  
## <a name="see-also"></a>関連項目  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)
