---
title: "static_partitioner クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppl/concurrency::static_partitioner
dev_langs:
- C++
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
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
ms.openlocfilehash: f36b1e1dcc68d94bdebd8b7b10f4fec735ce9fb5
ms.lasthandoff: 02/24/2017

---
# <a name="staticpartitioner-class"></a>static_partitioner クラス
`static_partitioner` クラスは、`parallel_for` によって反復処理される範囲の静的パーティション分割を表します。 パーティショナーは範囲をチャンクに分割します。チャンクの数は、基になるスケジューラが使用できるワーカーと同じ数にします。  
  
## <a name="syntax"></a>構文  
  
```
class static_partitioner;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[static_partitioner コンス トラクター](#ctor)|`static_partitioner` オブジェクトを構築します。|  
|[~ static_partitioner デストラクター](#dtor)|`static_partitioner` オブジェクトを破棄します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `static_partitioner`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namedtora-staticpartitioner"></a><a name="dtor"></a>~ static_partitioner 

 `static_partitioner` オブジェクトを破棄します。  
  
```
~static_partitioner();
```  
  
##  <a name="a-namectora-staticpartitioner"></a><a name="ctor"></a>static_partitioner 

 `static_partitioner` オブジェクトを構築します。  
  
```
static_partitioner();
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

