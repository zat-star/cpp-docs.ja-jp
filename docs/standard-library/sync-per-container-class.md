---
title: "sync_per_container クラス | Microsoft Docs"
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
  - "stdext.sync_per_container"
  - "sync_per_container"
  - "stdext::sync_per_container"
  - "allocators/stdext::sync_per_container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_per_container クラス"
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# sync_per_container クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[同期フィルター](../standard-library/allocators-header.md) について説明します。各アロケーター オブジェクトには、別のキャッシュ オブジェクトを提供します。  
  
## 構文  
  
```  
template <class Cache> class sync_per_container  
    : public Cache  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Cache`|同期フィルターに関連付けられた Cache の種類。  これは、[cache\_chunklist](../standard-library/cache-chunklist-class.md)[cache\_freelist](../standard-library/cache-freelist-class.md)、または [cache\_suballoc](../standard-library/cache-suballoc-class.md)のいずれでもかまいません。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[equals](../Topic/sync_per_container::equals.md)|同等の 2 種類のキャッシュを比較します。|  
  
## 必要条件  
 **ヘッダー:** の \<アロケーター\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)