---
title: "つまり is_final クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_final"
  - "std.is_final"
  - "std::is_final"
  - "type_traits/std::is_final"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "つまり is_final"
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# つまり is_final クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

種類がマークされたクラス型であるかどうかをテスト `final`します。  
  
## 構文  
  
```  
template<class T>  
    struct is_final;  
```  
  
#### パラメーター  
 `T`  
 照会する型。  
  
## 解説  
 場合、型述語のインスタンスは true を保持型 `T` クラス型になって `final`, 、それ以外の場合は false を保持します。 場合 `T` クラス型は、完全な型である必要があります。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [final 指定子](../cpp/final-specifier.md)