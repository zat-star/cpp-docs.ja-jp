---
title: "is_trivially_move_constructible クラス | Microsoft Docs"
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
  - "is_trivially_move_constructible"
  - "std.is_trivially_move_constructible"
  - "std::is_trivially_move_constructible"
  - "type_traits/std::is_trivially_move_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_move_constructible"
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
caps.latest.revision: 11
caps.handback.revision: 1
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_move_constructible クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型に自明な移動コンストラクターが存在するかどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_trivially_move_constructible;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 型 `Ty` が自明な移動コンストラクターを持つクラスである場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
 クラス `Ty` の移動コンストラクターが自明であるのは、以下の場合です。  
  
 暗黙的に宣言されている  
  
 そのパラメーターの型が暗黙的な宣言のものと同じである  
  
 クラス `Ty` に仮想関数がない  
  
 クラス `Ty` に仮想基底がない  
  
 クラスに揮発性の非静的データ メンバーがない  
  
 クラス `Ty` のすべての直接基本に自明な移動コンストラクターがある  
  
 クラス型のすべての非静的データ メンバーのクラスに自明な移動コンストラクターがある  
  
 クラスの型配列のすべての非静的データ メンバーのクラスに自明な移動コンストラクターがある  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)