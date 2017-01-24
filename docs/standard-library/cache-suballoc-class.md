---
title: "cache_suballoc クラス | Microsoft Docs"
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
  - "stdext.cache_suballoc"
  - "allocators/stdext::cache_suballoc"
  - "stdext::cache_suballoc"
  - "cache_suballoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_suballoc クラス"
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
caps.latest.revision: 17
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# cache_suballoc クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

定義、 [アロケーターをブロックする](../standard-library/allocators-header.md) を割り当てるし、サイズが 1 つのメモリ ブロックの割り当てを解除します。  
  
## 構文  
  
```  
template <std::size_t Sz, size_t Nelts = 20> class cache_suballoc  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Sz`|割り当てられる配列内の要素の数。|  
  
## 解説  
 Cache\_suballoc テンプレート クラスは、無制限の長さの空きリストの割り当てが解除されたメモリ ブロックを格納を使用して `freelist<sizeof(Type), max_unbounded>`, 、メモリ ブロックを使用して割り当てられたより大きなまとまったから suballocates と `operator new` フリー リストが空の場合。  
  
 各チャンクを保持して `Sz * Nelts` 使用可能なメモリと、データのバイトを `operator new` と `operator delete` を必要とします。 割り当てられているチャンクが解放されることはありません。  
  
### コンストラクター  
  
|||  
|-|-|  
|[cache\_suballoc](../Topic/cache_suballoc::cache_suballoc.md)|`cache_suballoc` 型のオブジェクトを構築します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[allocate](../Topic/cache_suballoc::allocate.md)|メモリのブロックを割り当てます。|  
|[deallocate](../Topic/cache_suballoc::deallocate.md)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|  
  
## 必要条件  
 **ヘッダー:** \<allocators\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)