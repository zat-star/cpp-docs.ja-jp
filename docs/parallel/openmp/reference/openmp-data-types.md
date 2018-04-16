---
title: "OpenMP のデータの種類 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2c1fb4643eba88b0d6fcdd9437479bcd4eed2b2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
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