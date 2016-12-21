---
title: "uses_allocator 構造体 | Microsoft Docs"
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
  - "future/std::uses_allocator"
dev_langs: 
  - "C++"
ms.assetid: c418f002-62e9-4806-b70c-41c663cae583
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# uses_allocator 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

常に当てはまる特殊化。  
  
## 構文  
  
```  
template<class Ty, class Alloc>  
struct uses_allocator<promise<Ty>, Alloc> : true_type;  
template<class Ty, class Alloc>  
struct uses_allocator<packaged_task<Ty>, Alloc> : true_type;  
```  
  
## 必要条件  
 **ヘッダー:** future  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)