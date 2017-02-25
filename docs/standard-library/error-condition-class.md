---
title: "error_condition クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "system_error/std::error_condition"
  - "std::error_condition"
  - "error_condition"
  - "std.error_condition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_condition クラス"
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# error_condition クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザー定義のエラー コードを表します。  
  
## 構文  
  
```  
class error_condition;  
```  
  
## 解説  
 型 `error_condition` オブジェクトが報告されたユーザー定義エラーに使用するエラー コードの [カテゴリ](../standard-library/error-category-class.md) を表すオブジェクトには、エラー コード値およびポインターを格納します。  
  
### コンストラクター  
  
|||  
|-|-|  
|[error\_condition](../Topic/error_condition::error_condition.md)|`error_condition` 型のオブジェクトを構築します。|  
  
### Typedef  
  
|||  
|-|-|  
|[value\_type](../Topic/error_condition::value_type.md)|保存されたエラー コード値を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[assign](../Topic/error_condition::assign.md)|エラー条件にエラー コード値およびカテゴリを割り当てます。|  
|[カテゴリ](../Topic/error_condition::category.md)|エラー カテゴリを返します。|  
|[clear](../Topic/error_condition::clear.md)|エラー コード値およびカテゴリを削除します。|  
|[message](../Topic/error_condition::message.md)|エラー コードの名前を返します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_condition::operator==.md)|`error_condition` オブジェクトが等しいかどうかをテストします。|  
|[operator\!\=](../Topic/error_condition::operator!=.md)|`error_condition` オブジェクトが異なっているかどうかをテストします。|  
|[operator\<](../Topic/error_condition::operator%3C.md)|`error_condition` オブジェクトである場合、比較対象に渡される `error_code` オブジェクトより小さいかどうかを調べます。|  
|[operator\=](../Topic/error_condition::operator=.md)|`error_condition` オブジェクトに新しい列挙値を割り当てます。|  
|[operator bool](../Topic/error_condition::operator%20bool.md)|型 `error_condition`変数をキャストします。|  
  
## 必要条件  
 **ヘッダー:** \<system\_error\>  
  
 **名前空間:** std  
  
## 参照  
 [error\_category クラス](../standard-library/error-category-class.md)   
 [\<system\_error\>](../standard-library/system-error.md)