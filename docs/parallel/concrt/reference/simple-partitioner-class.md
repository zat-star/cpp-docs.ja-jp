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
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 08d378c841fd9181fe9a2cf918bde9fe3ebbdc32
ms.lasthandoff: 03/17/2017

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
|[simple_partitioner](#ctor)|`simple_partitioner` オブジェクトを構築します。|  
|[~ simple_partitioner デストラクター](#dtor)|`simple_partitioner` オブジェクトを破棄します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `simple_partitioner`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="dtor"></a>~ simple_partitioner 

 `simple_partitioner` オブジェクトを破棄します。  
  
```
~simple_partitioner();
```  
  
##  <a name="ctor"></a>simple_partitioner 

 `simple_partitioner` オブジェクトを構築します。  
  
```
explicit simple_partitioner(_Size_type _Chunk_size);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Chunk_size`  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

