---
title: "result_of クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "result_of"
  - "std.result_of"
  - "std::result_of"
  - "type_traits/std::result_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "result_of"
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# result_of クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定した引数型を受け取る呼び出し可能型の戻り値の型を決定します。  
  
## 構文  
  
```  
template <class Fn, class... ArgTypes>  
    struct result_of<Fn(ArgTypes...)>;  
```  
  
#### パラメーター  
 `Fn`  
 照会する呼び出し可能型。  
  
 `ArgTypes`  
 クエリに呼び出し可能型の引数リストの種類。  
  
## 解説  
 このテンプレートを使用して、結果の型をコンパイル時に決定する `Fn`\(`ArgTypes`\) ここで、 `Fn` 内の型の引数リストで呼び出された呼び出し可能型は、 `ArgTypes`です。`type` の結果の型のテンプレート クラスのメンバー名 `decltype(INVOKE(declval<Fn>(), declval<ArgTypes>()...))` 場合は評価されていない式 `INVOKE(declval<Fn>(), declval<ArgTypes>()...)` が整形式です。 それ以外の場合、このテンプレート クラスを持たないメンバー `type`します。 種類 `Fn` 、パラメーター パック内のすべての型と `ArgTypes` 完全な型にする必要があります `void`, 、または不明なバインドの配列。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)