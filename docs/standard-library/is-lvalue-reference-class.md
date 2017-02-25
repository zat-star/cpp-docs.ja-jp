---
title: "is_lvalue_reference クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.is_lvalue_reference"
  - "std::tr1::is_lvalue_reference"
  - "is_lvalue_reference"
  - "std.is_lvalue_reference"
  - "std::is_lvalue_reference"
  - "type_traits/std::is_lvalue_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_lvalue_reference クラス [TR1]"
  - "is_lvalue_reference"
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# is_lvalue_reference クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型が左辺値参照かどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_lvalue_reference;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 型 `Ty` がオブジェクトへの参照または関数への参照である場合、この型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  `Ty` は右辺値参照でない場合があることに注意してください。  右辺値の詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [左辺値と右辺値](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md)