---
title: "max_fixed_size クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators/stdext::max_fixed_size"
  - "max_fixed_size"
  - "stdext::max_fixed_size"
  - "stdext.max_fixed_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_fixed_size クラス"
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# max_fixed_size クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[最大クラス](../standard-library/allocators-header.md) オブジェクトを制限する最大固定長に [freelist](../Topic/freelist%20Class.md) オブジェクトについて説明します。  
  
## 構文  
  
```  
template <std::size_t Max> class max_fixed_size  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Max`|`freelist`に格納する要素の最大数を決定する最大クラス。|  
  
### コンストラクター  
  
|||  
|-|-|  
|[max\_fixed\_size](../Topic/max_fixed_size::max_fixed_size.md)|`max_fixed_size` 型のオブジェクトを構築します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[割り当てられた](../Topic/max_fixed_size::allocated.md)|割り当てられたメモリ ブロックの数をインクリメントします。|  
|[解放される](../Topic/max_fixed_size::deallocated.md)|割り当てられたメモリ ブロックの数をデクリメントします。|  
|[&#91;full&#93;](../Topic/max_fixed_size::full.md)|より多くのメモリ ブロックは空きリストに追加するかどうかを示す値を返します。|  
|[解放する](../Topic/max_fixed_size::released.md)|空きリストのメモリ ブロックの数をデクリメントします。|  
|[格納されている](../Topic/max_fixed_size::saved.md)|空きリストのメモリ ブロックの数をインクリメントします。|  
  
## 必要条件  
 **ヘッダー:** の \<アロケーター\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)