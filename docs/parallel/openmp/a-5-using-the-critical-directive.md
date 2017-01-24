---
title: "A.5   Using the critical Directive | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.5   Using the critical Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次の例では `critical` の複数のディレクティブ \(ページの 18[セクション 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md)\) が含まれます。  この例ではタスクが削除されるとキューイング アウト モデルを示しています。  同じタスクを複数スレッドのキューに対して防御するキュー操作は `critical` のセクションにある必要があります。  この例の 2 種類のキューは独立しているため別の名前*x 軸*  半径と *y 軸* `critical` のディレクティブによって保護されています。  
  
```  
#pragma omp parallel shared(x, y) private(x_next, y_next)  
{  
    #pragma omp critical ( xaxis )  
        x_next = dequeue(x);  
    work(x_next);  
    #pragma omp critical ( yaxis )  
        y_next = dequeue(y);  
    work(y_next);  
}  
```