---
title: "cache_chunklist クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators/stdext::cache_chunklist"
  - "stdext.cache_chunklist"
  - "stdext::cache_chunklist"
  - "cache_chunklist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_chunklist クラス"
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# cache_chunklist クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[ブロックのアロケーター](../standard-library/allocators-header.md) を定義する単一のサイズのメモリ ブロックの割り当てと解放する。  
  
## 構文  
  
```  
template <std::size_t Sz, std::size_t Nelts = 20> class cache_chunklist  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Sz`|割り当てる配列の要素数。|  
  
## 解説  
 このテンプレート クラスは、必要に応じてメモリ ブロックのストレージを割り当てるためにメモリ ブロックを suballocating 未加工のチャンクを割り当てるに `operator new` ;を このクラスは、各チャンクの別の空きリストでメモリ ブロックはいずれも、使用していないときは、解放されたメモリ ブロックを格納し、チャンクを解放するために `operator delete` を使用します。  
  
 各メモリ ブロックは、チャンクに使用可能なメモリのバイト `Sz`、ポインターを保持します。  各チャンクは `operator new` と `operator delete` に必要な `Nelts` のメモリ ブロック、スリーポイントの三つのポインター、int とデータを保持します。  
  
### コンストラクター  
  
|||  
|-|-|  
|[cache\_chunklist](../Topic/cache_chunklist::cache_chunklist.md)|`cache_chunklist` 型のオブジェクトを構築します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[割り当てます。](../Topic/cache_chunklist::allocate.md)|メモリ ブロックを割り当てます。|  
|[解放してください。](../Topic/cache_chunklist::deallocate.md)|指定した位置にストレージの先頭から指定した数のオブジェクトを解放します。|  
  
## 必要条件  
 **ヘッダー:** の \<アロケーター\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)