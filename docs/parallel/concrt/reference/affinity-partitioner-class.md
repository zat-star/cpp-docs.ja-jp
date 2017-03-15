---
title: "affinity_partitioner クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppl/concurrency::affinity_partitioner
dev_langs:
- C++
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 92da56fd5b84537c2fa01a252dfee202c729cc96
ms.lasthandoff: 02/24/2017

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
|[affinity_partitioner コンス トラクター](#ctor)|`affinity_partitioner` オブジェクトを構築します。|  
|[~ affinity_partitioner デストラクター](#dtor)|破棄、`affinity_partitioner`オブジェクトです。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `affinity_partitioner`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namedtora-affinitypartitioner"></a><a name="dtor"></a>~ affinity_partitioner 

 破棄、`affinity_partitioner`オブジェクトです。  
  
```
~affinity_partitioner();
```  
  
##  <a name="a-namectora-affinitypartitioner"></a><a name="ctor"></a>affinity_partitioner 

 `affinity_partitioner` オブジェクトを構築します。  
  
```
affinity_partitioner();
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

