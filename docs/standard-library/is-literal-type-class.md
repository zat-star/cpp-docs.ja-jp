---
title: "is_literal_type クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_literal_type"
  - "std.is_literal_type"
  - "std::is_literal_type"
  - "type_traits/std::is_literal_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_literal_type"
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_literal_type クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型として使用できるかどうかをテスト、 `constexpr` 変数または構築で使用またはから返された `constexpr` 関数です。  
  
## 構文  
  
```  
template <class T>  
    struct is_literal_type;  
```  
  
#### パラメーター  
 `T`  
 照会する型。  
  
## 解説  
 場合、型述語のインスタンスは true を保持型 `T` は、 *リテラルの型*, 、それ以外の場合は false を保持します。 リテラルの型は、いずれかの `void`, 、スカラー型、参照型、リテラルの型の配列またはリテラルのクラス型です。 リテラルのクラス型を自明なデストラクターを持つクラス型、集約型またはが少なくとも 1 つ以外の移動、コピー以外 `constexpr` コンス トラクター、およびすべての基底クラスと非静的データ メンバーは、非揮発性リテラル型。 リテラルの型は、リテラルの型では常に、リテラルの型の概念は、コンパイラとして評価できる、 `constexpr` コンパイル時にします。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)