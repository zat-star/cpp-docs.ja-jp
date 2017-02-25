---
title: "underlying_type クラス | Microsoft Docs"
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
  - "underlying_type"
  - "std.underlying_type"
  - "std::underlying_type"
  - "type_traits/std::underlying_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "underlying_type"
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# underlying_type クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

列挙型の基になる整数型を生成します。  
  
## 構文  
  
```  
template <class T>  
    struct underlying_type;  
```  
  
#### パラメーター  
 `T`  
 変更する型。  
  
## 解説  
 `type` テンプレート クラスのメンバーの typedef 名の基になる整数型 `T`, ときに、 `T` 列挙型の場合は、それ以外の場合はメンバー typedef `type`します。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)