---
title: "is_trivially_constructible クラス | Microsoft Docs"
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
  - "is_trivially_constructible"
  - "std.is_trivially_constructible"
  - "std::is_trivially_constructible"
  - "type_traits/std::is_trivially_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_constructible"
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# is_trivially_constructible クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定した引数型を使用する場合は、型が普通によって構築可能かどうかをテストします。  
  
## 構文  
  
```  
template <class T, class... Args>  
    struct is_trivially_constructible;  
```  
  
#### パラメーター  
 `T`  
 照会する型。  
  
 `Args`  
 引数の型のコンス トラクターで一致するように `T`します。  
  
## 解説  
 場合、型述語のインスタンスは true を保持型 `T` 、内の引数の型を使用して簡単に構築可能な `Args`, 、それ以外の場合は false を保持します。 型 `T` 、簡単に構築可能な場合は変数定義 `T t(std::declval<Args>()...);` 整形式では、重要な操作を呼び出すしないことが判明しています。 両方とも `T` 内のすべての型と `Args` 完全な型にする必要があります `void`, 、または不明なバインドの配列。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)