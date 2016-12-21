---
title: "is_trivially_copy_assignable | Microsoft Docs"
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
  - "is_trivially_copy_assignable"
  - "std.is_trivially_copy_assignable"
  - "std::is_trivially_copy_assignable"
  - "type_traits/std::is_trivially_copy_assignable"
dev_langs: 
  - "C++"
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
caps.latest.revision: 12
caps.handback.revision: 1
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_copy_assignable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型が自明なコピー代入演算子を持つかどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_trivially_copy_constructible;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 型 `Ty` が自明なコピー代入演算子を持つクラスの場合、型述語のインスタンスは true を保持します。それ以外の場合は false を保持します。  
  
 クラス `Ty` の代入コンストラクターが自明であるのは、以下の場合です。  
  
 暗黙的に指定されている  
  
 クラス `Ty` に仮想関数がない  
  
 クラス `Ty` に仮想基底がない  
  
 クラス型のすべての非静的データ メンバーのクラスに自明な代入演算子がある  
  
 クラスの型配列のすべての非静的データ メンバーのクラスに自明な代入演算子がある  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)