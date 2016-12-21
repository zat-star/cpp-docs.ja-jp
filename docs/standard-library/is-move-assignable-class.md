---
title: "is_move_assignable クラス | Microsoft Docs"
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
  - "is_move_assignable"
  - "std.is_move_assignable"
  - "std::is_move_assignable"
  - "type_traits/std::is_move_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_move_assignable"
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_move_assignable クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

割り当てられた型かどうかに移動します。  
  
## 構文  
  
```  
template<class T>  
    struct is_move_assignable;  
```  
  
#### パラメーター  
 `T`  
 照会する型。  
  
## 解説  
 型では、割り当て可能な移動は型への右辺値参照型への参照に割り当てられる場合です。 型述語と同じ `is_assignable<T&, T&&>`します。 割り当てられた型が参照可能のスカラー型を含めるし、クラス型にコンパイラによって生成されたか、ユーザー定義の移動代入演算子を移動します。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)