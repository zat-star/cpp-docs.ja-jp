---
title: "3.2.1 omp_init_lock 関数と omp_init_nest_lock 関数 |Microsoft ドキュメント"
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
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3802822465d6527e4c98a0be6a8c274d767b0f52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 omp_init_lock 関数と omp_init_nest_lock 関数
これらの関数は、ロックの初期化の唯一の手段を提供します。 各関数は、パラメーターに関連付けられているロック、初期化*ロック*後続の呼び出しで使用するためです。 形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_init_lock(omp_lock_t *lock);  
void omp_init_nest_lock(omp_nest_lock_t *lock);  
```  
  
 初期状態のロックが解除されている (つまり、スレッド ロックを所有していません)。 入れ子にできるロックでは、最初の入れ子になった数は 0 です。 これらのルーチンは既に初期化されているロック変数のいずれかを呼び出さない非準拠であります。