---
title: "max_unbounded クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators/stdext::max_unbounded"
  - "stdext::max_unbounded"
  - "stdext.max_unbounded"
  - "max_unbounded"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_unbounded クラス"
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# max_unbounded クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

説明、 [クラスを最大](../standard-library/allocators-header.md) の最大長を制限することはないオブジェクト、 [freelist](../Topic/freelist%20Class.md) オブジェクトです。  
  
## 構文  
  
```  
class max_unbounded  
```  
  
### メンバー関数  
  
|||  
|-|-|  
|[割り当てられています。](../Topic/max_unbounded::allocated.md)|割り当てられたメモリ ブロックの数を増やします。|  
|[割り当て解除](../Topic/max_unbounded::deallocated.md)|デクリメントの数には、メモリ ブロックが割り当てられます。|  
|[完全](../Topic/max_unbounded::full.md)|多くのメモリ ブロックがフリー リストに追加するかどうかを指定する値を返します。|  
|[リリース](../Topic/max_unbounded::released.md)|メモリの数がフリー リストでブロックをデクリメントします。|  
|[保存](../Topic/max_unbounded::saved.md)|フリー リスト上のメモリ ブロックの数を増やします。|  
  
## 必要条件  
 **ヘッダー:** \<allocators\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)