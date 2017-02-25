---
title: "sync_per_thread クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::sync_per_thread"
  - "sync_per_thread"
  - "allocators/stdext::sync_per_thread"
  - "stdext.sync_per_thread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_per_thread クラス"
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# sync_per_thread クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[同期フィルター](../standard-library/allocators-header.md) について説明します。スレッドごとに個別のキャッシュ オブジェクトを提供します。  
  
## 構文  
  
```  
template <class Cache> class sync_per_thread  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Cache`|同期フィルターに関連付けられた Cache の種類。  これは、[cache\_chunklist](../standard-library/cache-chunklist-class.md)[cache\_freelist](../standard-library/cache-freelist-class.md)、または [cache\_suballoc](../standard-library/cache-suballoc-class.md)のいずれでもかまいません。|  
  
## 解説  
 `sync_per_thread` を使用するアロケーターは 1 種類のスレッドに割り当てられたブロックが他のスレッドから解放することはできませんが、等号 \(\=\) を比較できます。  1 のスレッドに割り当てられるこれらのメモリ ブロックの 1 を使用すると、他のスレッドから参照できるようにする必要があります。  実際には、これは次の 1 つを使用するコンテナーをシングル スレッドにアクセスしないことを意味します。  
  
### メンバー関数  
  
|||  
|-|-|  
|[割り当てます。](../Topic/sync_per_thread::allocate.md)|メモリ ブロックを割り当てます。|  
|[解放してください。](../Topic/sync_per_thread::deallocate.md)|指定した位置にストレージの先頭から指定した数のオブジェクトを解放します。|  
|[equals](../Topic/sync_per_thread::equals.md)|同等の 2 種類のキャッシュを比較します。|  
  
## 必要条件  
 **ヘッダー:** の \<アロケーター\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)