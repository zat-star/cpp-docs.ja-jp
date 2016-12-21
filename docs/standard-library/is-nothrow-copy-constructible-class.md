---
title: "is_nothrow_copy_constructible クラス | Microsoft Docs"
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
  - "is_nothrow_copy_constructible"
  - "std.is_nothrow_copy_constructible"
  - "std::is_nothrow_copy_constructible"
  - "type_traits/std::is_nothrow_copy_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_copy_constructible"
ms.assetid: f13a0bea-63b1-492a-9a45-d445df35c282
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_nothrow_copy_constructible クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型に [nothrow](../Topic/nothrow%20\(C++\).md) コピー コンストラクターが存在するかどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_nothrow_copy_constructible;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 型 `Ty` に nothrow コピー コンストラクターが存在する場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)