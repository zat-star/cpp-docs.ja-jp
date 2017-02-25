---
title: "improper_scheduler_attach クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::improper_scheduler_attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_scheduler_attach クラス"
ms.assetid: 5a76da0a-091b-4748-8f62-b3a28f674f9e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# improper_scheduler_attach クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、現在のコンテキストに既にアタッチされている `Scheduler` オブジェクトで `Attach` メソッドが呼び出された場合にスローされる例外を表します。  
  
## 構文  
  
```  
class improper_scheduler_attach : public std::exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[improper\_scheduler\_attach::improper\_scheduler\_attach コンストラクター](../Topic/improper_scheduler_attach::improper_scheduler_attach%20Constructor.md)|オーバーロードされます。  `improper_scheduler_attach` オブジェクトを構築します。|  
  
## 継承階層  
 `exception`  
  
 `improper_scheduler_attach`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler クラス](../../../parallel/concrt/reference/scheduler-class.md)   
 [Scheduler::Attach メソッド](../Topic/Scheduler::Attach%20Method.md)