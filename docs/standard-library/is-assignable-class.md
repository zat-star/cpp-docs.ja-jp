---
title: "is_assignable クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_assignable"
  - "std.is_assignable"
  - "std::is_assignable"
  - "type_traits/std::is_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_assignable"
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# is_assignable クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

値かどうか検査 `From` 型に割り当てることができます、 `To` 型です。  
  
## 構文  
  
```  
template <class To, class From>  
    struct is_assignable;  
```  
  
#### パラメーター  
 目的  
 代入を受け取るオブジェクトの型。  
  
 提供元  
 値を渡すオブジェクトの型。  
  
## 解説  
 評価されていない式 `declval<To>() = declval<From>()` 整形式である必要があります。 両方とも `From` と `To` 完全な型にする必要があります `void`, 、または不明なバインドの配列。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)