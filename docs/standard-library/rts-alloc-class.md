---
title: "rts_alloc クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::rts_alloc"
  - "allocators/stdext::rts_alloc"
  - "rts_alloc"
  - "stdext.rts_alloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rts_alloc クラス"
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# rts_alloc クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

rts\_alloc テンプレート クラスは、キャッシュ インスタンスの配列を保持し、コンパイル時ではなく、実行時に割り当てと割り当て解除に使用するインスタンスを判別する[フィルター](../standard-library/allocators-header.md)を記述します。  
  
## 構文  
  
```  
template <class Cache> class rts_alloc  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Cache`|配列に含まれているキャッシュ インスタンスの型。  これは、[cache\_chunklist クラス](../standard-library/cache-chunklist-class.md)、[cache\_freelist](../standard-library/cache-freelist-class.md)、[cache\_suballoc](../standard-library/cache-suballoc-class.md) のいずれかです。|  
  
## 解説  
 このテンプレート クラスは、複数のブロック アロケーター インスタンスを保持し、コンパイル時ではなく、実行時に割り当てと割り当て解除に使用するインスタンスを判別します。  再バインドをコンパイルできないコンパイラと一緒に使用します。  
  
### メンバー関数  
  
|||  
|-|-|  
|[allocate](../Topic/rts_alloc::allocate.md)|メモリのブロックを割り当てます。|  
|[deallocate](../Topic/rts_alloc::deallocate.md)|指定した位置から、指定数のオブジェクトをストレージから解放します。|  
|[次の値に等しい](../Topic/rts_alloc::equals.md)|2 つのキャッシュが等しいかどうかを比較します。|  
  
## 必要条件  
 **ヘッダー:** \<allocators\>  
  
 **名前空間:** stdext  
  
## 参照  
 [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md)   
 [\<allocators\>](../standard-library/allocators-header.md)