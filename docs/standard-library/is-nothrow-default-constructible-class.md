---
title: "is_nothrow_default_constructible クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_nothrow_default_constructible"
  - "std.is_nothrow_default_constructible"
  - "std::is_nothrow_default_constructible"
  - "type_traits/std::is_nothrow_default_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_default_constructible"
ms.assetid: c576fcc9-5be1-43aa-b93a-64d3f1848887
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# is_nothrow_default_constructible クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

スローしない既定コンストラクターが型に存在するかどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_nothrow_default_constructible;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 スローしない既定コンストラクターが型 `Ty` に存在する場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  型述語のインスタンスは `is_nothrow_constructible<Ty>` と同じです。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)