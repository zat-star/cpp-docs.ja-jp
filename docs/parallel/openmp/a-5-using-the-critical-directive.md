---
title: "重要なディレクティブを使用して A.5 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1ef678b58df9d2c323cdebb61feed52ebbaf607f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="a5---using-the-critical-directive"></a>A.5 critical ディレクティブの使用
次の例では、いくつか含まれています`critical`ディレクティブ ([セクション 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) 18 ページ)。 この例では、タスクがキューから削除して作業対象のキューのモデルを示します。 同じタスクをキューから削除する複数のスレッドを防ぐには、デキュー操作に必要な`critical`セクションです。 によって保護されているため、この例では 2 つのキューは独立して、 `critical` 、異なる名前のディレクティブ*xaxis*と*yaxis*です。  
  
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