---
title: "is_move_constructible クラス | Microsoft Docs"
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
  - "is_move_constructible"
  - "std.is_move_constructible"
  - "std::is_move_constructible"
  - "type_traits/std::is_move_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_move_constructible"
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_move_constructible クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型に移動コンス トラクターがある存在するかどうかをテストします。  
  
## 構文  
  
```  
template <class T>  
    struct is_move_constructible;  
```  
  
#### パラメーター  
 T  
 評価される型  
  
## 解説  
 型の場合は true に評価される型述語 `T` 移動操作を使用して作成できます。 この述語と同じ `is_constructible<T, T&&>`します。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)