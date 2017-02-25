---
title: "is_error_condition_enum クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::is_error_condition_enum"
  - "std.is_error_condition_enum"
  - "is_error_condition_enum"
  - "system_error/std::is_error_condition_enum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_error_condition_enum クラス"
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# is_error_condition_enum クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この型述語を [error\_condition](../standard-library/error-condition-class.md) の列挙体のテスト表します。  
  
## 構文  
  
```  
template<_Enum>  
    class is_error_condition_enum;  
```  
  
## 解説  
 この [型述語](../standard-library/type-traits.md) のインスタンスは、型 `_Enum` が型 `error_condition`オブジェクトの格納に適した列挙値である場合。  
  
 ユーザー定義型のこの型に特化したクラスを追加してもかまいません。  
  
## 必要条件  
 **ヘッダー:** \<system\_error\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [\<system\_error\>](../standard-library/system-error.md)