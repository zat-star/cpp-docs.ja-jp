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
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 84cdbb30068f8dd9d2a1130e53d06d9b718b0c02
ms.lasthandoff: 03/17/2017

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
|[static_partitioner](#ctor)|`static_partitioner` オブジェクトを構築します。|  
|[~ static_partitioner デストラクター](#dtor)|`static_partitioner` オブジェクトを破棄します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `static_partitioner`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="dtor"></a>~ static_partitioner 

 `static_partitioner` オブジェクトを破棄します。  
  
```
~static_partitioner();
```  
  
##  <a name="ctor"></a>static_partitioner 

 `static_partitioner` オブジェクトを構築します。  
  
```
static_partitioner();
```  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

