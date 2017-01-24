---
title: "is_trivially_default_constructible クラス | Microsoft Docs"
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
  - "is_trivially_default_constructible"
  - "std.is_trivially_default_constructible"
  - "std::is_trivially_default_constructible"
  - "type_traits/std::is_trivially_default_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_default_constructible"
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
caps.latest.revision: 17
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_default_constructible クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型に自明な既定コンストラクターが存在するかどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct  is_trivially_default_constructible;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 型 `Ty` が自明なコンストラクターを持つクラスである場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
 クラス `Ty` の既定コンストラクターが自明であるのは、以下の場合です。  
  
-   暗黙的に宣言された既定のコンス トラクターである  
  
-   クラス `Ty` に仮想関数がない  
  
-   クラス `Ty` に仮想基底がない  
  
-   クラス `Ty` のすべての直接基底に自明なコンストラクターがある  
  
-   クラス型のすべての非静的データ メンバーのクラスに自明なコンストラクターがある  
  
-   クラスの型配列のすべての非静的データ メンバーのクラスに自明なコンストラクターがある  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)