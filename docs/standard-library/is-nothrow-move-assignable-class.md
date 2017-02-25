---
title: "is_nothrow_move_assignable クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_nothrow_move_assignable"
  - "std.is_nothrow_move_assignable"
  - "std::is_nothrow_move_assignable"
  - "type_traits/std::is_nothrow_move_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_move_assignable"
ms.assetid: 000baa02-cbba-49de-9870-af730033348e
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# is_nothrow_move_assignable クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型が [nothrow](../Topic/nothrow%20\(C++\).md) ムーブ代入演算子を持つかどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_nothrow_move_assignable;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 型 `Ty` が nothrow ムーブ代入演算子を持つ場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)