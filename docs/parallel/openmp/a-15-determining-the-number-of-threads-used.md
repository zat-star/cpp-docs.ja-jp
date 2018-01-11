---
title: "使用するスレッドの数を決定する A.15 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8b7fb8cf6218863287d582a097cb43b399cff07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="a15---determining-the-number-of-threads-used"></a>A.15 使用されるスレッド数の確認
次の不適切な使用例を検討してください (の[セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) [37] ページ)。  
  
```  
np = omp_get_num_threads(); // misplaced   
#pragma omp parallel for schedule(static)  
    for (i=0; i<np; i++)  
        work(i);  
```  
  
 `omp_get_num_threads()`ためシリアル、コードのセクションでは 1 を返しますを呼び出す*np*前の例では、1 に等しいは常になります。 並列領域に対して展開されるスレッドの数を調べるには、並行領域内の呼び出しでなければなりません。  
  
 次の例では、スレッドの数のクエリを含めずにこのプログラムを書き換える方法を示します。  
  
```  
#pragma omp parallel private(i)  
{  
    i = omp_get_thread_num();  
    work(i);  
}  
```