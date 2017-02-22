---
title: "is_nothrow_destructible クラス | Microsoft Docs"
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
  - "is_nothrow_destructible"
  - "std.is_nothrow_destructible"
  - "std::is_nothrow_destructible"
  - "type_traits/std::is_nothrow_destructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_destructible"
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# is_nothrow_destructible クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

種類は消滅させられると、デストラクターをスローしないようにコンパイラが認識するかどうかをテストします。  
  
## 構文  
  
```  
template <class T>  
    struct is_nothrow_destructible;  
```  
  
#### パラメーター  
 `T`  
 照会する型。  
  
## 解説  
 場合、型述語のインスタンスは true を保持型 `T` 消滅させられる型であり、デストラクターをスローしないようにコンパイラが認識されます。 それ以外の場合、false を保持します。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)