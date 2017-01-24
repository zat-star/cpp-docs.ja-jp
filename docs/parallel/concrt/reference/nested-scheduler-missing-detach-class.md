---
title: "nested_scheduler_missing_detach クラス | Microsoft Docs"
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
  - "concrt/concurrency::nested_scheduler_missing_detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nested_scheduler_missing_detach クラス"
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# nested_scheduler_missing_detach クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`Scheduler` オブジェクトの `Attach` メソッドによって別のスケジューラにアタッチされているコンテキストで `CurrentScheduler::Detach` メソッドが呼び出されなかったことを、同時実行ランタイムが検出した場合にスローされる例外を表します。  
  
## 構文  
  
```  
class nested_scheduler_missing_detach : public std::exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[nested\_scheduler\_missing\_detach::nested\_scheduler\_missing\_detach コンストラクター](../Topic/nested_scheduler_missing_detach::nested_scheduler_missing_detach%20Constructor.md)|オーバーロードされます。  `nested_scheduler_missing_detach` オブジェクトを構築します。|  
  
## 解説  
 この例外は、既に所有または別のスケジューラにアタッチされているコンテキストの `Scheduler` オブジェクトの `Attach` のメソッドを呼び出して、1 個のスケジューラを別の入れ子になっている場合にスローされます。  同時実行ランタイムでは、該当する状況を検出できた場合に、問題の特定を支援する便宜的な手段として、この例外がスローされます。  `CurrentScheduler::Detach` メソッドが呼び出されなかったからといって、常にこの例外がスローされるわけではありません。  
  
## 継承階層  
 `exception`  
  
 `nested_scheduler_missing_detach`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler クラス](../../../parallel/concrt/reference/scheduler-class.md)   
 [CurrentScheduler::Detach メソッド](../Topic/CurrentScheduler::Detach%20Method.md)   
 [Scheduler::Attach メソッド](../Topic/Scheduler::Attach%20Method.md)