---
title: "is_trivially_copy_constructible クラス | Microsoft Docs"
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
  - "is_trivially_copy_constructible"
  - "std.is_trivially_copy_constructible"
  - "std::is_trivially_copy_constructible"
  - "type_traits/std::is_trivially_copy_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_copy_constructible"
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: 24
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_copy_constructible クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型に自明なコピー コンス トラクターがある存在するかどうか。  
  
## 構文  
  
```  
template<class T>  
    struct is_trivially_copy_constructible;  
```  
  
#### パラメーター  
 `T`  
 照会する型。  
  
## 解説  
 型 `T` が自明なコピー コンストラクターを持つクラスである場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
 クラスのコピー コンス トラクター `T` は暗黙的に宣言されている場合、クラスに簡単では `T` 仮想関数または仮想基底クラス、クラスのすべての直接基底クラスを持たない `T` 自明なコピー コンス トラクターを持つ、クラス型のすべての非静的データ メンバーのクラスがある自明なコピー コンス トラクター、およびクラスの配列型のすべての非静的データ メンバーのクラスが自明なコピー コンス トラクターを持ちます。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)