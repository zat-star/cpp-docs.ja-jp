---
title: "is_constructible クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_constructible"
  - "std.is_constructible"
  - "std::is_constructible"
  - "type_traits/std::is_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_constructible"
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# is_constructible クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定した引数型を使用する場合は、型がによって構築可能かどうかをテストします。  
  
## 構文  
  
```  
template <class T, class... Args>  
    struct is_constructible;  
```  
  
#### パラメーター  
 `T`  
 照会する型。  
  
 `Args`  
 引数の型のコンス トラクターで一致するように `T`します。  
  
## 解説  
 場合、型述語のインスタンスは true を保持型 `T` の引数の型を使用して、構築可能な `Args`, 、それ以外の場合は false を保持します。 型 `T` 、構築可能な場合は、変数の定義 `T t(std::declval<Args>()...);` が整形式です。 両方とも `T` 内のすべての型と `Args` 完全な型にする必要があります `void`, 、または不明なバインドの配列。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)