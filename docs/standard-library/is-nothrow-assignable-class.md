---
title: "is_nothrow_assignable クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "is_nothrow_assignable"
  - "std.is_nothrow_assignable"
  - "std::is_nothrow_assignable"
  - "type_traits/std::is_nothrow_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_assignable"
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# is_nothrow_assignable クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

値かどうか検査 `From` 型に割り当てることができます `To` 型と、割り当てをスローしないように呼ばれます。  
  
## 構文  
  
```  
template <class To, class From>   
    struct is_nothrow_assignable;  
```  
  
#### パラメーター  
 目的  
 代入を受け取るオブジェクトの型。  
  
 提供元  
 値を渡すオブジェクトの型。  
  
## 解説  
 式 `declval<To>() = declval<From>()` 整形式である必要があるあり、スローしないようにコンパイラが認識する必要があります。 両方とも `From` と `To` 完全な型にする必要があります `void`, 、または不明なバインドの配列。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)