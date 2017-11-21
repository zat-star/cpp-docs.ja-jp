---
title: "Threadprivate ディレクティブを使用して A.26 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 6eda76c2-c4f1-4208-a900-e0ea98a53eca
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f6c24a3c00dad6e196d015518071978884260c93
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="a26---using-the-threadprivate-directive"></a>A.26 threadprivate ディレクティブの使用
次の例を使用する方法を示します、`threadprivate`ディレクティブ ([セクション 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md) 23 ページの) スレッドごとに別々 にカウンターを提供します。  
  
 **例 1:**  
  
```  
int counter = 0;  
#pragma omp threadprivate(counter)  
  
int sub()  
{  
    counter++;  
    return(counter);  
}  
```  
  
 **例 2:**  
  
```  
int sub()  
{  
    static int counter = 0;  
    #pragma omp threadprivate(counter)  
    counter++;  
    return(counter);  
}  
```