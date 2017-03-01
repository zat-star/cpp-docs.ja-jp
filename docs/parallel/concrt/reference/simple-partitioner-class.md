---
title: "simple_partitioner クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppl/concurrency::simple_partitioner
dev_langs:
- C++
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
caps.latest.revision: 8
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
ms.openlocfilehash: dc90df5ba9fbbf5566a26a014a6a2db2ae4a0459
ms.lasthandoff: 02/24/2017

---
# <a name="simplepartitioner-class"></a>simple_partitioner クラス
`simple_partitioner` クラスは、`parallel_for` によって反復処理される範囲の静的パーティション分割を表します。 パーティショナーは範囲をチャンクに分割します。各チャンクには、少なくともチャンク サイズによって指定された数のイテレーションが含まれます。  
  
## <a name="syntax"></a>構文  
  
```
class simple_partitioner;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[simple_partitioner コンス トラクター](#ctor)|`simple_partitioner` オブジェクトを構築します。|  
|[~ simple_partitioner デストラクター](#dtor)|`simple_partitioner` オブジェクトを破棄します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `simple_partitioner`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namedtora-simplepartitioner"></a><a name="dtor"></a>~ simple_partitioner 

 `simple_partitioner` オブジェクトを破棄します。  
  
```
~simple_partitioner();
```  
  
##  <a name="a-namectora-simplepartitioner"></a><a name="ctor"></a>simple_partitioner 

 `simple_partitioner` オブジェクトを構築します。  
  
```
explicit simple_partitioner(_Size_type _Chunk_size);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Chunk_size`  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

