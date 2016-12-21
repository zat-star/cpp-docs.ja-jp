---
title: "is_trivially_move_assignable クラス | Microsoft Docs"
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
  - "is_trivially_move_assignable"
  - "std.is_trivially_move_assignable"
  - "std::is_trivially_move_assignable"
  - "type_traits/std::is_trivially_move_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_move_assignable"
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
caps.latest.revision: 11
caps.handback.revision: 1
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_move_assignable クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型が自明なムーブ代入演算子を持つかどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_trivially_move_assignable;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 型 `Ty` が自明なムーブ代入演算子を持つクラスの場合、型述語のインスタンスは true を保持します。それ以外の場合は false を保持します。  
  
 次の条件が満たされる場合、クラス `Ty` のムーブ代入演算子は自明です。  
  
 暗黙的に指定されている  
  
 クラス `Ty` に仮想関数がない  
  
 クラス `Ty` に仮想基底がない  
  
 クラス型のすべての非静的データ メンバーのクラスに自明なムーブ代入演算子がある  
  
 クラスの型配列のすべての非静的データ メンバーのクラスに自明なムーブ代入演算子がある  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)