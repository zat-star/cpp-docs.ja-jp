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
ms.openlocfilehash: af833219039a03e7e403f7e3cd10210057f3abfa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="see-also"></a>関連項目  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)