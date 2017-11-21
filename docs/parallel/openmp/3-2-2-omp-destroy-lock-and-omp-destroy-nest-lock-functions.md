---
title: "3.2.2 omp_destroy_lock 関数と omp_destroy_nest_lock 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 19da0297844357cfbf8a0266600224bb13673b26
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 omp_destroy_lock 関数と omp_destroy_nest_lock 関数
これらの関数いることを確認、とがったロック変数を*ロック*が初期化されていません。 形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_destroy_lock(omp_lock_t *lock);  
void omp_destroy_nest_lock(omp_nest_lock_t *lock);  
```  
  
 これらのルーチンが初期化されていないか、ロック解除をロック変数のいずれかを呼び出さない非準拠であります。