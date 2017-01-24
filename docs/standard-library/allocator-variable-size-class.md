---
title: "allocator_variable_size クラス | Microsoft Docs"
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
  - "allocators.allocator_variable_size"
  - "allocators::allocator_variable_size"
  - "allocators/stdext::allocator_variable_size"
  - "stdext.allocators.allocator_variable_size"
  - "allocator_variable_size"
  - "allocators/stdext::allocators::allocator_variable_size"
  - "stdext::allocators::allocator_variable_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_variable_size クラス"
ms.assetid: c3aa4105-ae45-4385-bbbe-9f23060478cb
caps.latest.revision: 16
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# allocator_variable_size クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[max\_variable\_size](../standard-library/max-variable-size-class.md)によって管理される期間の型 [cache\_freelist](../standard-library/cache-freelist-class.md) のキャッシュを使用して型 `Type` オブジェクトの記憶割振エラーと解放を管理するオブジェクトを表します。  
  
## 構文  
  
```  
template <class Type>  
    class allocator_variable_size;  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Type`|アロケーターで割り当てられている要素の型。|  
  
## 解説  
 [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) マクロは次のステートメントの `name` パラメーターにこのクラスを渡します: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`  
  
## 必要条件  
 **ヘッダー:** の \<アロケーター\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)