---
title: "3.2.3 omp_set_lock 関数と omp_set_nest_lock 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e709e43a0b32b68bc34c4e76e8680ae371e30670
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="323-ompsetlock-and-ompsetnestlock-functions"></a>3.2.3 omp_set_lock 関数と omp_set_nest_lock 関数
これらの各関数は、指定されたロックを使用し、ロックを設定するまでは、関数を実行するスレッドをブロックします。 単純なロックはロックされていない場合に使用できます。 ロックされていない場合、または関数を実行するスレッドによって既に所有している場合は、入れ子にできるロックは使用します。 形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_set_lock(omp_lock_t *lock);  
void omp_set_nest_lock(omp_nest_lock_t *lock);  
```  
  
 単純ロックへの引数、`omp_set_lock`関数は、初期化されたロック変数を指す必要があります。 ロックの所有権は、関数を実行するスレッドに与えられます。  
  
 入れ子にできるロックへの引数、`omp_set_nest_lock`関数は、初期化されたロック変数を指す必要があります。 入れ子のカウントがインクリメントされ、スレッドが付与されるか、ロックの所有権を保持します。 します。