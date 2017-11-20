---
title: "既定値 (OpenMP) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: default
dev_langs: C++
helpviewer_keywords:
- default OpenMP clause
- defaults, OpenMP clause
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: caafb7818c32dad7b21ac7a05d10f77753c1da73
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="default-openmp"></a>default (OpenMP)
並列領域で、対象範囲外の変数の動作を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
default(shared | none)  
```  
  
## <a name="remarks"></a>コメント  
 `shared`を有効になっている場合、`default`句が指定されていないこと、並行領域内の変数として扱われることを指定したことを意味、[共有](../../../parallel/openmp/reference/shared-openmp.md)句。 `none`すべての変数とスコープは設定されませんを並列領域で使用される、[プライベート](../../../parallel/openmp/reference/private-openmp.md)、[共有](../../../parallel/openmp/reference/shared-openmp.md)、[削減](../../../parallel/openmp/reference/reduction.md)、 [firstprivate](../../../parallel/openmp/reference/firstprivate.md)、または[lastprivate](../../../parallel/openmp/reference/lastprivate.md)句には、コンパイラ エラーが発生します。  
  
 `default`次のディレクティブに適用されます。  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [セクション](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、次を参照してください。 [2.7.2.5 既定](../../../parallel/openmp/2-7-2-5-default.md)です。  
  
## <a name="example"></a>例  
 参照してください[プライベート](../../../parallel/openmp/reference/private-openmp.md)の使用例については`default`します。  
  
## <a name="see-also"></a>関連項目  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)