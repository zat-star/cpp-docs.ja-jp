---
title: "順序付けられたディレクティブの例については A.23 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 83d77bb4f064a7ee69b013b36de919b57486b3e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="a23---examples-of-the-ordered-directive"></a>A.23 ordered ディレクティブの例
順序付けられた複数のセクションを取得することは、`for`で指定された、`ordered`句。 最初の例は、API は、次を指定するために準拠していません。  
  
 "でループのイテレーション、`for`コンストラクト実行してはいけません同じ`ordered`と、それ以上のディレクティブは 1 つ以上を実行できません必要があります`ordered`ディレクティブです"。 (を参照してください[セクション 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) 22 ページ上)  
  
 この規則違反の例では、すべてのイテレーションは、2 つの順序付けられたセクションを実行します。  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
}  
```  
  
 準拠している例を次に、`for`順序付けられた複数のセクション。  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    if (i <= 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
    (i > 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
}  
```