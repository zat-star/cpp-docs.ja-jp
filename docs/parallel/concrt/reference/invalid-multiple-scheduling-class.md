---
title: "invalid_multiple_scheduling クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::invalid_multiple_scheduling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_multiple_scheduling クラス"
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# invalid_multiple_scheduling クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`task_group` オブジェクトまたは `structured_task_group` オブジェクトの `run` メソッドを使用して `task_handle` オブジェクトが複数回スケジュールされた場合、間に `wait` メソッドまたは `run_and_wait` メソッドを呼び出さなかったときにスローされる例外を表します。  
  
## 構文  
  
```  
class invalid_multiple_scheduling : public std::exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[invalid\_multiple\_scheduling::invalid\_multiple\_scheduling コンストラクター](../Topic/invalid_multiple_scheduling::invalid_multiple_scheduling%20Constructor.md)|オーバーロードされます。  `invalid_multiple_scheduling` オブジェクトを構築します。|  
  
## 継承階層  
 `exception`  
  
 `invalid_multiple_scheduling`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_handle クラス](../../../parallel/concrt/reference/task-handle-class.md)   
 [task\_group クラス](../Topic/task_group%20Class.md)   
 [task\_group::run メソッド](../Topic/task_group::run%20Method.md)   
 [task\_group::wait メソッド](../Topic/task_group::wait%20Method.md)   
 [task\_group::run\_and\_wait メソッド](../Topic/task_group::run_and_wait%20Method.md)   
 [structured\_task\_group クラス](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [structured\_task\_group::run メソッド](../Topic/structured_task_group::run%20Method.md)   
 [structured\_task\_group::wait メソッド](../Topic/structured_task_group::wait%20Method.md)   
 [structured\_task\_group::run\_and\_wait メソッド](../Topic/structured_task_group::run_and_wait%20Method.md)