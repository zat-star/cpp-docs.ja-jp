---
title: "is_trivially_copyable クラス | Microsoft Docs"
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
  - "is_trivially_copyable"
  - "std.is_trivially_copyable"
  - "std::is_trivially_copyable"
  - "type_traits/std::is_trivially_copyable"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_trivially_copyable"
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_copyable クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型は、普通にコピー可能型かどうかをテストします。  
  
## 構文  
  
```  
template<class T>  
    struct is_trivially_copyable;  
```  
  
#### パラメーター  
 `T`  
 照会する型。  
  
## 解説  
 場合、型述語のインスタンスは true を保持型 `T` は普通にコピー可能型の場合はそれ以外の場合は false を保持します。 非自明なコピー操作、移動操作またはデストラクター普通にコピー可能の型があるありません。 一般に、コピー操作は自明として扱われる場合はビットごとのコピーとして実装できます。 組み込み型と普通にコピー可能型の配列の両方は普通にコピー可能です。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)