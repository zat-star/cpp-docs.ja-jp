---
title: "invalid_scheduler_policy_key クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::invalid_scheduler_policy_key"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_scheduler_policy_key クラス"
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# invalid_scheduler_policy_key クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、無効なキーまたは不明なキーが `SchedulerPolicy` オブジェクトのコンストラクターに渡された場合、あるいは、本来他の方法 \(`SetConcurrencyLimits` メソッドなど\) で変更する必要のあるキーが `SchedulerPolicy` オブジェクトの `SetPolicyValue` メソッドに渡された場合にスローされる例外を表します。  
  
## 構文  
  
```  
class invalid_scheduler_policy_key : public std::exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[invalid\_scheduler\_policy\_key::invalid\_scheduler\_policy\_key コンストラクター](../Topic/invalid_scheduler_policy_key::invalid_scheduler_policy_key%20Constructor.md)|オーバーロードされます。  `invalid_scheduler_policy_key` オブジェクトを構築します。|  
  
## 継承階層  
 `exception`  
  
 `invalid_scheduler_policy_key`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [SchedulerPolicy クラス](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [PolicyElementKey 列挙型](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy::SetPolicyValue メソッド](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)   
 [SchedulerPolicy::SetConcurrencyLimits メソッド](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)