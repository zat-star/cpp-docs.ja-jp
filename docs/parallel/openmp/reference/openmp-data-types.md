---
title: "OpenMP のデータの種類 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c777e672354d257ce8923c8ee0974860fdcbe8c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="openmp-data-types"></a>OpenMP のデータ型
OpenMP API で使用されるデータ型へのリンクを提供します。  
  
 OpenMP の標準の Visual C の実装には、次のデータ型が含まれています。  
  
|データ型|説明|  
|---------------|-----------------|  
|[omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md)|ロックが、ロックが使用できるかどうか、またはスレッドにロックを所有しているかどうかの状態を保持する型。|  
|[omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md)|ロックに関する情報の次の 1 つを保持する型: かどうか、ロックが使用できる、およびスレッドの id を所有しているロックが解除され、入れ子になった回数です。|  
  
## <a name="see-also"></a>参照  
 [ライブラリ リファレンス](../../../parallel/openmp/reference/openmp-library-reference.md)