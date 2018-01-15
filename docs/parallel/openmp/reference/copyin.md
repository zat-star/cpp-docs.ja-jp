---
title: "copyin |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: copyin
dev_langs: C++
helpviewer_keywords: copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3190c1f6914ae8ea24b968a8cf286de1867938cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="copyin"></a>copyin
スレッドのマスター スレッドの値にアクセスできるように、 [threadprivate](../../../parallel/openmp/reference/threadprivate.md)変数。  
  
## <a name="syntax"></a>構文  
  
```  
copyin(var)  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `var`  
 `threadprivate` Parallel コンストラクトの前に存在する場合に、マスター スレッド内の変数の値で初期化される変数です。  
  
## <a name="remarks"></a>コメント  
 `copyin`次のディレクティブに適用されます。  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [セクション](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、次を参照してください。 [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md)です。  
  
## <a name="example"></a>例  
 参照してください[threadprivate](../../../parallel/openmp/reference/threadprivate.md)の使用例については`copyin`します。  
  
## <a name="see-also"></a>参照  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)