---
title: "auto_partitioner クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::auto_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_partitioner クラス"
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# auto_partitioner クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`auto_partitioner` クラスは、反復処理する範囲を分割するために、既定のメソッド `parallel_for`、`parallel_for_each`、および `parallel_transform` の使用を表します。  このパーティション分割のメソッドでは、負荷分散および反復ごとの取り消しで範囲スティーリングが使用されます。  
  
## 構文  
  
```  
class auto_partitioner;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[auto\_partitioner::auto\_partitioner コンストラクター](../Topic/auto_partitioner::auto_partitioner%20Constructor.md)|`auto_partitioner` オブジェクトを構築します。|  
|[auto\_partitioner::~auto\_partitioner デストラクター](../Topic/auto_partitioner::~auto_partitioner%20Destructor.md)|`auto_partitioner` オブジェクトを破棄します。|  
  
## 継承階層  
 `auto_partitioner`  
  
## 必要条件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)