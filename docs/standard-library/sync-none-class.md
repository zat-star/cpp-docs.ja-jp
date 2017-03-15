---
title: "sync_none クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext.sync_none"
  - "sync_none"
  - "allocators/stdext::sync_none"
  - "stdext::sync_none"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_none クラス"
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# sync_none クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[同期フィルター](../standard-library/allocators-header.md) を説明します。同期を提供しません。  
  
## 構文  
  
```  
template <class Cache> class sync_none  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Cache`|同期フィルターに関連付けられた Cache の種類。  これは、[cache\_chunklist](../standard-library/cache-chunklist-class.md)[cache\_freelist](../standard-library/cache-freelist-class.md)、または [cache\_suballoc](../standard-library/cache-suballoc-class.md)のいずれでもかまいません。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[割り当てます。](../Topic/sync_none::allocate.md)|メモリ ブロックを割り当てます。|  
|[解放してください。](../Topic/sync_none::deallocate.md)|指定した位置にストレージの先頭から指定した数のオブジェクトを解放します。|  
|[equals](../Topic/sync_none::equals.md)|同等の 2 種類のキャッシュを比較します。|  
  
## 必要条件  
 **ヘッダー:** の \<アロケーター\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)