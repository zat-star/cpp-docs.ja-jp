---
title: "static_partitioner クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
dev_langs: C++
helpviewer_keywords: static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 110091a414f9cfeebcdf236b7eed6a9e46e06ea2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
