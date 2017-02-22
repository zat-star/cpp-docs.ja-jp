---
title: "task_canceled クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::task_canceled"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_canceled クラス"
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# task_canceled クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、現在のタスクを強制的に取り消すために PPL タスク レイヤーによってスローされる例外を表します。  また、取り消されたタスクに対して、[task](../Topic/Task%20Class%20-%20Internal%20Members.md) の `get()` メソッドによってもスローされます。  
  
## 構文  
  
```  
class task_canceled : public std::exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[task\_canceled::task\_canceled コンストラクター](../Topic/task_canceled::task_canceled%20Constructor.md)|オーバーロードされます。  `task_canceled` オブジェクトを構築します。|  
  
## 継承階層  
 `exception`  
  
 `task_canceled`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task::get メソッド](../Topic/task::get%20Method.md)   
 [cancel\_current\_task 関数](../Topic/cancel_current_task%20Function.md)