---
title: "2.5.2 parallel sections のコンストラクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 086552c72e37822920e0afa213c7966befa052f7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="252-parallel-sections-construct"></a>2.5.2 parallel sections のコンストラクト
**Parallel sections の**ディレクティブを指定するショートカット フォームを提供する、**並列**が 1 つのみが含まれる領域**セクション**ディレクティブです。 セマンティクスは明示的に指定することと同じ、**並列**ディレクティブの直後に続く、**セクション**ディレクティブです。 構文、 **parallel sections の**ディレクティブは、次のようにします。  
  
```  
#pragma omp parallel sections  [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block  ]  
   ...  
}  
```  
  
 *句*で受け入れられる句のいずれかになります、**並列**と**のセクションでは**、ディレクティブを除く、 **nowait**句。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **並列**ディレクティブを参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページのです。  
  
-   **セクションでは**ディレクティブを参照してください[2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) [14] ページ。