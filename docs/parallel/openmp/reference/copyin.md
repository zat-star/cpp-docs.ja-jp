---
title: "copyin |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- copyin
dev_langs:
- C++
helpviewer_keywords:
- copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ff466d0ec280d4e31d49328a725da88d87bd2435
ms.lasthandoff: 02/24/2017

---
# <a name="copyin"></a>copyin
スレッドのマスター スレッドの値にアクセスできるように、 [threadprivate](../../../parallel/openmp/reference/threadprivate.md)変数です。  
  
## <a name="syntax"></a>構文  
  
```  
copyin(var)  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `var`  
 `threadprivate` Parallel コンストラクトの前に存在するマスター スレッド内の変数の値で初期化される変数です。  
  
## <a name="remarks"></a>コメント  
 `copyin`次のディレクティブに適用されます。  
  
-   [並列](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [セクション](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、次を参照してください。 [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md)します。  
  
## <a name="example"></a>例  
 参照してください[threadprivate](../../../parallel/openmp/reference/threadprivate.md)を使用する例については`copyin`です。  
  
## <a name="see-also"></a>関連項目  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)
