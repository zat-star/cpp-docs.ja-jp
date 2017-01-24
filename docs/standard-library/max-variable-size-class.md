---
title: "max_variable_size クラス | Microsoft Docs"
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
  - "stdext::max_variable_size"
  - "allocators/stdext::max_variable_size"
  - "stdext.max_variable_size"
  - "max_variable_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_variable_size クラス"
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# max_variable_size クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

説明、 [クラスの最大](../standard-library/allocators-header.md) オブジェクトを制限する、 [freelist](../Topic/freelist%20Class.md) の数にほぼ比例の最大長にオブジェクトには、メモリ ブロックが割り当てられています。  
  
## 構文  
  
```  
class max_variable_size  
```  
  
### コンストラクター  
  
|||  
|-|-|  
|[max\_variable\_size](../Topic/max_variable_size::max_variable_size.md)|`max_variable_size` 型のオブジェクトを構築します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[割り当てられています。](../Topic/max_variable_size::allocated.md)|割り当てられたメモリ ブロックの数を増やします。|  
|[割り当て解除](../Topic/max_variable_size::deallocated.md)|デクリメントの数には、メモリ ブロックが割り当てられます。|  
|[完全](../Topic/max_variable_size::full.md)|多くのメモリ ブロックがフリー リストに追加するかどうかを指定する値を返します。|  
|[リリース](../Topic/max_variable_size::released.md)|メモリの数がフリー リストでブロックをデクリメントします。|  
|[保存](../Topic/max_variable_size::saved.md)|フリー リスト上のメモリ ブロックの数を増やします。|  
  
## 必要条件  
 **ヘッダー:** \<allocators\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)