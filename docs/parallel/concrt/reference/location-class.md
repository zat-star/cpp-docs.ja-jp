---
title: "location クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::location"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "location クラス"
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# location クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

ハードウェアの物理位置の抽象化です。  
  
## 構文  
  
```  
class location;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[location::location コンストラクター](../Topic/location::location%20Constructor.md)|オーバーロードされます。  `location` オブジェクトを構築します。|  
|[location::~location デストラクター](../Topic/location::~location%20Destructor.md)|`location` オブジェクトを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[location::current メソッド](../Topic/location::current%20Method.md)|`location` を表すオブジェクトを呼び出し元のスレッドが実行されている特定の位置を返します。|  
|[location::from\_numa\_node メソッド](../Topic/location::from_numa_node%20Method.md)|特定の NUMA ノードを表す `location` オブジェクトを返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[location::operator\!\= 演算子](../Topic/location::operator!=%20Operator.md)|`location` の 2 種類のオブジェクトが別の位置を表すかどうかを判定します。|  
|[location::operator\= 演算子](../Topic/location::operator=%20Operator.md)|この 1 への `location` の別のオブジェクトに割り当てます。|  
|[location::operator\=\= 演算子](../Topic/location::operator==%20Operator.md)|`location` の 2 種類のオブジェクトが同じ場所を表すかどうかを判定します。|  
  
## 継承階層  
 `location`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)