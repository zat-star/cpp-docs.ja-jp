---
title: "3.1.4 omp_get_thread_num 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9beb9e81d767a11b4ca701725ac44cc19cd3c3e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="314-ompgetthreadnum-function"></a>3.1.4 omp_get_thread_num 関数
`omp_get_thread_num`関数、スレッドの数を返します、そのチーム内で関数を実行するスレッド。 0 との間のスレッドの番号にあると**omp_get_num_threads()**-1、包括的です。 チームのマスター スレッドはスレッド 0 です。  
  
 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_thread_num(void);  
```  
  
 シリアル領域から呼び出された場合`omp_get_thread_num`0 を返します。 シリアル化される入れ子になった並行領域内から呼び出されると、この関数は 0 を返します。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   `omp_get_num_threads`関数を参照してください[セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) [37] ページ。