---
title: "decay クラス | Microsoft Docs"
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
  - "decay"
  - "std.tr1.decay"
  - "std::tr1::decay"
  - "std.decay"
  - "std::decay"
  - "type_traits/std::decay"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "decay クラス [TR1]"
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# decay クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

値で渡される型を生成します。 型の非参照、非定数、非揮発性、または関数、または配列型から型へのポインターを作成します。  
  
## 構文  
  
```  
template<class T>  
    struct decay;  
  
template<class T> using decay_t = typename decay<T>::type;  
```  
  
#### パラメーター  
 `T`  
 変更する型。  
  
## 解説  
 型が値を引数としてから渡されたかのように、結果の型を生成するのにには、減衰テンプレートを使用します。 テンプレート クラス メンバー typedef `type` 、次の段階で定義されている変更された型を保持します。  
  
-   型 `U` が `remove_reference<T>::type` として定義されます。  
  
-   場合 `is_array<U>::value` が true の場合、変更された型 `type` は `remove_extent<U>::type *`です。  
  
-   それ以外の場合 `is_function<U>::value` が true の場合、変更された型 `type` は `add_pointer<U>::type`です。  
  
-   それ以外の場合、変更後の型 `type` は `remove_cv<U>::type`です。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)