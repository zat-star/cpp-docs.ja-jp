---
title: "invalid_scheduler_policy_value クラス | Microsoft Docs"
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
  - "concrt/concurrency::invalid_scheduler_policy_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_scheduler_policy_value クラス"
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_scheduler_policy_value クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`SchedulerPolicy` オブジェクトのポリシー キーがそのキーの無効な値に設定された場合にスローされる例外を表します。  
  
## 構文  
  
```  
class invalid_scheduler_policy_value : public std::exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[invalid\_scheduler\_policy\_value::invalid\_scheduler\_policy\_value コンストラクター](../Topic/invalid_scheduler_policy_value::invalid_scheduler_policy_value%20Constructor.md)|オーバーロードされます。  `invalid_scheduler_policy_value` オブジェクトを構築します。|  
  
## 継承階層  
 `exception`  
  
 `invalid_scheduler_policy_value`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [SchedulerPolicy クラス](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [PolicyElementKey 列挙型](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy::SetPolicyValue メソッド](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)   
 [SchedulerPolicy::SetConcurrencyLimits メソッド](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)