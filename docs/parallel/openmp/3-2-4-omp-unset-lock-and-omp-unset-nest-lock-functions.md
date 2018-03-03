---
title: "3.2.4 omp_unset_lock 関数と omp_unset_nest_lock 関数 |Microsoft ドキュメント"
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
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dc71c6c31a1d93b6e9c9cce2cd4f7830502a1a2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="324-ompunsetlock-and-ompunsetnestlock-functions"></a>3.2.4 omp_unset_lock 関数と omp_unset_nest_lock 関数
これらの関数は、ロックの所有権を解放する手段を提供します。 形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_unset_lock(omp_lock_t *lock);  
void omp_unset_nest_lock(omp_nest_lock_t *lock);  
```  
  
 これらの各関数の引数は、関数を実行するスレッドが所有する初期化されたロック変数を指す必要があります。 スレッドがそのロックを所有していない場合、動作は定義されません。  
  
 単純ロック、`omp_unset_lock`関数は、ロックの所有権から関数を実行するスレッドを解放します。  
  
 入れ子にできるロックで、`omp_unset_nest_lock`関数デクリメント、入れ子のカウントとリリース、結果のカウントが 0 の場合は、ロックの所有権から関数を実行するスレッド。