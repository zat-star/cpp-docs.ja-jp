---
title: "affinity_partitioner クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
dev_langs:
- C++
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ecc7e20947eee2491bf806f225178724b268ace
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="affinitypartitioner-class"></a>affinity_partitioner クラス
`affinity_partitioner` クラスは `static_partitioner` クラスに似ていますが、ワーカー スレッドへのマッピングのサブ範囲の選択によってキャッシュの関係が向上します。 同じデータ セットに対してループ処理が再実行されるときにパフォーマンスを大幅に向上させることができ、データはキャッシュに収まります。 データの局所性のメリットを利用するには、特定のデータ セットに対して実行される並列ループの以降のイテレーションで、同じ `affinity_partitioner` オブジェクトを使用する必要があります。  
  
## <a name="syntax"></a>構文  
  
```
class affinity_partitioner;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[affinity_partitioner](#ctor)|`affinity_partitioner` オブジェクトを構築します。|  
|[~ affinity_partitioner デストラクター](#dtor)|破棄、`affinity_partitioner`オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `affinity_partitioner`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="dtor"></a> ~affinity_partitioner 

 破棄、`affinity_partitioner`オブジェクト。  
  
```
~affinity_partitioner();
```  
  
##  <a name="ctor"></a> affinity_partitioner 

 `affinity_partitioner` オブジェクトを構築します。  
  
```
affinity_partitioner();
```  
  
## <a name="see-also"></a>参照  
 [concurrency 名前空間](concurrency-namespace.md)
