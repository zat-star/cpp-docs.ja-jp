---
title: "static_partitioner クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
dev_langs:
- C++
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 20dad961b694042c721f388c9a40e0bf99b9b77d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
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
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="dtor"></a> ~static_partitioner 

 `static_partitioner` オブジェクトを破棄します。  
  
```
~static_partitioner();
```  
  
##  <a name="ctor"></a> static_partitioner 

 `static_partitioner` オブジェクトを構築します。  
  
```
static_partitioner();
```  
  
## <a name="see-also"></a>参照  
 [concurrency 名前空間](concurrency-namespace.md)
