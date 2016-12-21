---
title: "allocator_suballoc クラス | Microsoft Docs"
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
  - "allocators::allocator_suballoc"
  - "allocator_suballoc"
  - "stdext.allocators.allocator_suballoc"
  - "allocators/stdext::allocators::allocator_suballoc"
  - "stdext::allocators::allocator_suballoc"
  - "allocators/stdext::allocator_suballoc"
  - "allocators.allocator_suballoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_suballoc クラス"
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
caps.latest.revision: 16
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# allocator_suballoc クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

記憶域の割り当てと型のオブジェクトの解放を管理できるオブジェクトを表す `Type` 型のキャッシュを使用して [cache\_suballoc](../standard-library/cache-suballoc-class.md)します。  
  
## 構文  
  
```  
template <class Type>  
    class allocator_suballoc;  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Type`|アロケーターによって割り当てられた要素の型。|  
  
## 解説  
 [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) マクロとしてこのクラスに渡します、 `name` 次のステートメント内のパラメーター。 `ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`  
  
## 必要条件  
 **ヘッダー:** \<allocators\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)