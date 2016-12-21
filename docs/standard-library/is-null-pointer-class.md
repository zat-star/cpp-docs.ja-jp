---
title: "is_null_pointer クラス | Microsoft Docs"
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
  - "is_null_pointer"
  - "std.is_null_pointer"
  - "std::is_null_pointer"
  - "type_traits/std::is_null_pointer"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_null_pointer"
ms.assetid: f3b3601b-f162-4803-a6e9-dabf5c3876cc
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_null_pointer クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型が std::nullptr\_t であるかどうか。  
  
## 構文  
  
```  
template<class T>  
    struct is_null_pointer;  
```  
  
#### パラメーター  
 `T`  
 照会する型。  
  
## 解説  
 場合、型述語のインスタンスは true を保持型 `T` は `std::nullptr_t`, 、それ以外の場合は false を保持します。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)