---
title: "missing_wait クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::missing_wait"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "missing_wait クラス"
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# missing_wait クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`task_group` オブジェクトまたは `structured_task_group` オブジェクトのデストラクターの実行時に、そのオブジェクトにスケジュールされたタスクがまだ存在する場合にスローされる例外を表します。  例外の結果としてのスタック アンワインドによりデストラクターが実行される場合、この例外はスローされません。  
  
## 構文  
  
```  
class missing_wait : public std::exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[missing\_wait::missing\_wait コンストラクター](../Topic/missing_wait::missing_wait%20Constructor.md)|オーバーロードされます。  `missing_wait` オブジェクトを構築します。|  
  
## 解説  
 例外フローがない場合、`task_group` オブジェクトまたは `structured_task_group` オブジェクトが破棄される前に、そのオブジェクトの `wait` メソッドまたは `run_and_wait` メソッドが呼び出される必要があります。  `wait` メソッドまたは `run_and_wait` メソッドが呼び出されない場合、ランタイムによってこの例外がスローされます。  
  
## 継承階層  
 `exception`  
  
 `missing_wait`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_group クラス](../Topic/task_group%20Class.md)   
 [task\_group::wait メソッド](../Topic/task_group::wait%20Method.md)   
 [task\_group::run\_and\_wait メソッド](../Topic/task_group::run_and_wait%20Method.md)   
 [structured\_task\_group クラス](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [structured\_task\_group::wait メソッド](../Topic/structured_task_group::wait%20Method.md)   
 [structured\_task\_group::run\_and\_wait メソッド](../Topic/structured_task_group::run_and_wait%20Method.md)