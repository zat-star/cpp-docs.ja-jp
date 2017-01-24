---
title: "error_code クラス | Microsoft Docs"
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
  - "error_code"
  - "std.error_code"
  - "std::error_code"
  - "system_error/std::error_code"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_code クラス"
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
caps.latest.revision: 17
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# error_code クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

実装固有である低レベルのシステム エラーを表します。  
  
## 構文  
  
```  
class error_code;  
```  
  
## 解説  
 型の `error_code` クラス オブジェクトは、報告された低レベルのシステム エラーを示すエラー コードの [カテゴリ](../standard-library/error-category-class.md) を表すオブジェクトには、エラー コード値およびポインターを格納します。  
  
### コンストラクター  
  
|||  
|-|-|  
|[error\_code](../Topic/error_code::error_code.md)|`error_code` 型のオブジェクトを構築します。|  
  
### Typedef  
  
|||  
|-|-|  
|[value\_type](../Topic/error_code::value_type.md)|保存されたエラー コード値を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[assign](../Topic/error_code::assign.md)|エラー コードにエラー コード値およびカテゴリを割り当てます。|  
|[カテゴリ](../Topic/error_code::category.md)|エラー カテゴリを返します。|  
|[clear](../Topic/error_code::clear.md)|エラー コード値およびカテゴリを削除します。|  
|[default\_error\_condition](../Topic/error_code::default_error_condition.md)|既定のエラー状態を返します。|  
|[message](../Topic/error_code::message.md)|エラー コードの名前を返します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_code::operator==.md)|`error_code` オブジェクトが等しいかどうかをテストします。|  
|[operator\!\=](../Topic/error_code::operator!=.md)|`error_code` オブジェクトが異なっているかどうかをテストします。|  
|[operator\<](../Topic/error_code::operator%3C.md)|`error_code` オブジェクトである場合、比較対象に渡される `error_code` オブジェクトより小さいかどうかを調べます。|  
|[operator\=](../Topic/error_code::operator=.md)|`error_code` オブジェクトに新しい列挙値を割り当てます。|  
|[operator bool](../Topic/error_code::operator%20bool.md)|型 `error_code`変数をキャストします。|  
  
## 必要条件  
 **ヘッダー:** \<system\_error\>  
  
 **名前空間:** std  
  
## 参照  
 [error\_category クラス](../standard-library/error-category-class.md)   
 [\<system\_error\>](../standard-library/system-error.md)