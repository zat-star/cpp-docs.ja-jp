---
title: "is_destructible クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "is_destructible"
  - "std.is_destructible"
  - "std::is_destructible"
  - "type_traits/std::is_destructible"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_destructible"
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
caps.latest.revision: 16
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_destructible クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型が破棄可能かどうかをテストします。  
  
## 構文  
  
```  
template <class T>  
    struct is_destructible;  
```  
  
#### パラメーター  
 `T`  
 照会する型。  
  
## 解説  
 型 `T` が破棄可能な型である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 破棄可能な型は、参照型、オブジェクト型、および `remove_all_extents_t<T>` に等しいいくつかの型 `U` に対して、未評価オペランド `std::declval<U&>.~U()` が整形式である型です。 不完全な型、`void`、および関数型を含む他の型は、破棄可能な型ではありません。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)