---
title: "allocator_fixed_size クラス | Microsoft Docs"
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
  - "allocators/stdext::allocators::allocator_fixed_size"
  - "allocators::allocator_fixed_size"
  - "allocators/stdext::allocator_fixed_size"
  - "allocator_fixed_size"
  - "stdext::allocators::allocator_fixed_size"
  - "allocators.allocator_fixed_size"
  - "stdext.allocators.allocator_fixed_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_fixed_size クラス"
ms.assetid: 138f3ef8-b0b3-49c3-9486-58f2213c172f
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# allocator_fixed_size クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[max\_fixed\_size](../standard-library/max-fixed-size-class.md)によって管理される期間の型 [cache\_freelist](../standard-library/cache-freelist-class.md) のキャッシュを使用して型 `Type` オブジェクトの記憶割振エラーと解放を管理するオブジェクトを表します。  
  
## 構文  
  
```  
template <class Type>  
    class allocator_fixed_size;  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Type`|アロケーターで割り当てられている要素の型。|  
  
## 解説  
 [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) マクロは次のステートメントの `name` パラメーターにこのクラスを渡します: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_fixed_size<10>), SYNC_DEFAULT, allocator_fixed_size);`  
  
## 必要条件  
 **ヘッダー:** の \<アロケーター\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)