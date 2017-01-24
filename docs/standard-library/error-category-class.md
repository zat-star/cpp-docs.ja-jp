---
title: "error_category クラス | Microsoft Docs"
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
  - "std::error_category"
  - "system_error/std::error_category"
  - "error_category"
  - "std.error_category"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_category クラス"
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# error_category クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

抽象的な共通の基本クラス オブジェクトのエラー コードのカテゴリを説明するを表します。  
  
## 構文  
  
```  
class error_category;  
```  
  
## 解説  
 2 つの定義済みオブジェクトが実装 `error_category`: [generic\_category](../Topic/generic_category.md) と [system\_category](../Topic/system_category.md)です。  
  
### Typedef  
  
|||  
|-|-|  
|[value\_type](../Topic/error_category::value_type.md)|格納されたエラー コード値を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[default\_error\_condition](../Topic/error_category::default_error_condition.md)|エラー コードのエラー条件オブジェクトの値を格納します。|  
|[equivalent](../Topic/error_category::equivalent.md)|エラー オブジェクトが等しいかどうかを示す値を返します。|  
|[message](../Topic/error_category::message.md)|指定したエラー コードの名前を返します。|  
|[name](../Topic/error_category::name.md)|カテゴリの名前を返します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_category::operator==.md)|間の等値テスト `error_category` オブジェクトです。|  
|[operator\!\=](../Topic/error_category::operator!=.md)|間の非等値テスト `error_category` オブジェクトです。|  
|[operator\<](../Topic/error_category::operator%3C.md)|かどうか、 [error\_category](../standard-library/error-category-class.md) オブジェクトより小さい `error_category` 比較のために渡されたオブジェクト。|  
  
## 必要条件  
 **ヘッダー:** \<system\_error\>  
  
 **名前空間:** std  
  
## 参照  
 [\<system\_error\>](../standard-library/system-error.md)