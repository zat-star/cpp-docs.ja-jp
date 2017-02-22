---
title: "SchedulerPolicy クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::SchedulerPolicy"
  - "concrtrm/concurrency::SchedulerPolicy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SchedulerPolicy クラス"
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# SchedulerPolicy クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`SchedulerPolicy` クラスには、ポリシー要素ごとに 1 つずつ、スケジューラ インスタンスの動作を制御するキーと値のペアのセットが含まれています。  
  
## 構文  
  
```  
class SchedulerPolicy;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[SchedulerPolicy::SchedulerPolicy コンストラクター](../Topic/SchedulerPolicy::SchedulerPolicy%20Constructor.md)|オーバーロードされます。  新しいスケジューラ ポリシーを構築し、同時実行ランタイム スケジューラおよびリソース マネージャーでサポートされている[ポリシー キー](../Topic/PolicyElementKey%20Enumeration.md)の値を設定します。|  
|[SchedulerPolicy::~SchedulerPolicy デストラクター](../Topic/SchedulerPolicy::~SchedulerPolicy%20Destructor.md)|スケジューラ ポリシーを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[SchedulerPolicy::GetPolicyValue メソッド](../Topic/SchedulerPolicy::GetPolicyValue%20Method.md)|`_Key` パラメーターとして指定されるポリシー キーの値を取得します。|  
|[SchedulerPolicy::SetConcurrencyLimits メソッド](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)|`SchedulerPolicy` オブジェクトに対して、`MinConcurrency` ポリシーおよび `MaxConcurrency` ポリシーを同時に設定します。|  
|[SchedulerPolicy::SetPolicyValue メソッド](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)|`_Key` パラメーターとして指定されるポリシー キーの値を設定し、古い値を返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[SchedulerPolicy::operator\= 演算子](../Topic/SchedulerPolicy::operator=%20Operator.md)|別のスケジューラ ポリシーからスケジューラ ポリシーを割り当てます。|  
  
## 解説  
 `SchedulerPolicy` クラスを使用して制御できるポリシーの詳細については、「[PolicyElementKey 列挙型](../Topic/PolicyElementKey%20Enumeration.md)」を参照してください。  
  
## 継承階層  
 `SchedulerPolicy`  
  
## 必要条件  
 **ヘッダー:** concrt.h, concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [PolicyElementKey 列挙型](../Topic/PolicyElementKey%20Enumeration.md)   
 [CurrentScheduler クラス](../Topic/CurrentScheduler%20Class.md)   
 [Scheduler クラス](../../../parallel/concrt/reference/scheduler-class.md)   
 [タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)