---
title: "is_nothrow_constructible クラス | Microsoft Docs"
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
  - "is_nothrow_constructible"
  - "std.is_nothrow_constructible"
  - "std::is_nothrow_constructible"
  - "type_traits/std::is_nothrow_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_constructible"
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# is_nothrow_constructible クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型が、構築可能なし、指定した引数型が使用されるとスローしないことが判明しているかどうかをテストします。  
  
## 構文  
  
```  
template <class T, class... Args>  
    struct is_nothrow_constructible;  
```  
  
#### パラメーター  
 `T`  
 照会する型。  
  
 `Args`  
 引数の型のコンス トラクターで一致するように `T`します。  
  
## 解説  
 場合、型述語のインスタンスは true を保持型 `T` の引数の型を使用して、構築可能な `Args`, とコンス トラクターをスローしないように、コンパイラで呼ばれます。 それ以外の場合は false を保持します。 型 `T` 、構築可能な場合は、変数の定義 `T t(std::declval<Args>()...);` が整形式です。 両方とも `T` 内のすべての型と `Args` 完全な型にする必要があります `void`, 、または不明なバインドの配列。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)