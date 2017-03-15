---
title: "allocator_newdel クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators::allocator_newdel"
  - "allocators/stdext::allocators::allocator_newdel"
  - "stdext.allocators.allocator_newdel"
  - "allocators/stdext::allocator_newdel"
  - "allocator_newdel"
  - "stdext::allocators::allocator_newdel"
  - "allocators.allocator_newdel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_newdel クラス"
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# allocator_newdel クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メモリ ブロックと `operator new` を解放するためにメモリ ブロックを割り当てるに `operator delete` を使用するアロケーターを実装します。  
  
## 構文  
  
```  
template <class Type>  
    class allocator_newdel;  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Type`|アロケーターで割り当てられている要素の型。|  
  
## 解説  
 [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) マクロは次のステートメントの `name` パラメーターにこのクラスを渡します: `ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`  
  
## 必要条件  
 **ヘッダー:** の \<アロケーター\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)