---
title: "Lastprivate 句を使用して A.6 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1744787e1dfb90fa9af93db5dba4eecd600b4334
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="a6---using-the-lastprivate-clause"></a>A.6 lastprivate 句の使用
正しい実行場合によっては、ループの最後の反復変数に代入する値に依存します。 このようなプログラムへの引数としてこのようなすべての変数を一覧表示する必要があります、`lastprivate`句 ([セクション 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) [27] ページ) できるように、変数の値は、ループが順番に実行されるときと同じです。  
  
```  
#pragma omp parallel  
{  
   #pragma omp for lastprivate(i)  
      for (i=0; i<n-1; i++)  
         a[i] = b[i] + b[i+1];  
}  
a[i]=b[i];  
```  
  
 前の例では、値で`i`並列領域の末尾が等しくなる`n-1`順次実行の場合のように、します。