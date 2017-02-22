---
title: "allocator_unbounded クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::allocators::allocator_unbounded"
  - "allocator_unbounded"
  - "allocators/stdext::allocator_unbounded"
  - "allocators::allocator_unbounded"
  - "allocators/stdext::allocators::allocator_unbounded"
  - "allocators.allocator_unbounded"
  - "stdext.allocators.allocator_unbounded"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_unbounded クラス"
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# allocator_unbounded クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[max\_unbounded](../standard-library/max-unbounded-class.md)によって管理される期間の型 [cache\_freelist](../standard-library/cache-freelist-class.md) のキャッシュを使用して型 `Type` オブジェクトの記憶割振エラーと解放を管理するオブジェクトを表します。  
  
## 構文  
  
```  
template <class Type>  
    class allocator_unbounded;  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Type`|アロケーターで割り当てられている要素の型。|  
  
## 解説  
 [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) マクロは次のステートメントの `name` パラメーターにこのクラスを渡します:`ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`  
  
## 必要条件  
 **ヘッダー:** の \<アロケーター\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)