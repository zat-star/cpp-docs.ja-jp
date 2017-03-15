---
title: "cache_freelist クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext.cache_freelist"
  - "allocators/stdext::cache_freelist"
  - "stdext::cache_freelist"
  - "cache_freelist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_freelist クラス"
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# cache_freelist クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

定義、 [アロケーターをブロックする](../standard-library/allocators-header.md) を割り当てるし、サイズが 1 つのメモリ ブロックの割り当てを解除します。  
  
## 構文  
  
```  
template <std::size_t Sz, class Max> class cache_freelist  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Sz`|割り当てられる配列内の要素の数。|  
|`Max`|フリー リストの最大サイズを表す最大クラスです。 これは、 [max\_fixed\_size](../standard-library/max-fixed-size-class.md), 、[max\_none](../Topic/max_none%20Class.md), 、[max\_unbounded](../standard-library/max-unbounded-class.md), 、または [max\_variable\_size](../standard-library/max-variable-size-class.md)します。|  
  
## 解説  
 Cache\_freelist テンプレート クラスは、サイズのメモリ ブロックの空きリストを保持 `Sz`します。 使用されている空きリストがいっぱいになったとき `operator delete` メモリの割り当てを解除するには、ブロックします。 使用されている空きリストが空の場合 `operator new` 新しいメモリ ブロックを割り当てる。 フリー リストの最大サイズは最大クラスが渡されたクラスによって決まります、 `Max` パラメーター。  
  
 各メモリ ブロックを保持して `Sz` 使用可能なメモリと、データのバイトを `operator new` と `operator delete` を必要とします。  
  
### コンストラクター  
  
|||  
|-|-|  
|[cache\_freelist](../Topic/cache_freelist::cache_freelist.md)|`cache_freelist` 型のオブジェクトを構築します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[allocate](../Topic/cache_freelist::allocate.md)|メモリのブロックを割り当てます。|  
|[deallocate](../Topic/cache_freelist::deallocate.md)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|  
  
## 必要条件  
 **ヘッダー:** \<allocators\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)