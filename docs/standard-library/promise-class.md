---
title: "promise クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "future/std::promise"
dev_langs: 
  - "C++"
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# promise クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*非同期プロバイダー*を記述します。  
  
## 構文  
  
```  
template<class Ty>  
class promise;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[promise::promise コンストラクター](../Topic/promise::promise%20Constructor.md)|`promise` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[promise::get\_future メソッド](../Topic/promise::get_future%20Method.md)|この約束に関連付けられている[予定](../standard-library/future-class.md)を返します。|  
|[promise::set\_exception メソッド](../Topic/promise::set_exception%20Method.md)|この約束の結果をアトミックに設定して、例外を示します。|  
|[promise::set\_exception\_at\_thread\_exit メソッド](../Topic/promise::set_exception_at_thread_exit%20Method.md)|この約束の結果をアトミックに設定して例外を示し、現在のスレッドのすべてのスレッド ローカルのオブジェクトが破棄された後にのみ通知を配信します \(通常はスレッド終了時\)。|  
|[promise::set\_value メソッド](../Topic/promise::set_value%20Method.md)|この約束の結果をアトミックに設定して、値を示します。|  
|[promise::set\_value\_at\_thread\_exit メソッド](../Topic/promise::set_value_at_thread_exit%20Method.md)|この約束の結果をアトミックに設定して値を示し、現在のスレッドのすべてのスレッド ローカルのオブジェクトが破棄された後にのみ通知を配信します \(通常はスレッド終了時\)。|  
|[promise::swap メソッド](../Topic/promise::swap%20Method.md)|この約束の*関連付けられた非同期状態*を、指定した約束オブジェクトの状態と交換します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[promise::operator\= 演算子](../Topic/promise::operator=%20Operator.md)|この約束オブジェクトの共有状態の割り当て。|  
  
## 継承階層  
 `promise`  
  
## 必要条件  
 **ヘッダー:** future  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)