---
title: "task_completion_event クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppltasks/concurrency::task_completion_event"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_completion_event クラス"
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# task_completion_event クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`task_completion_event` クラスを使用すると、条件が満たされるまで、または外部イベントに応答してタスクを開始するまで、タスクの実行を遅延できます。  
  
## 構文  
  
```  
template<  
   typename _ResultType  
>  
class task_completion_event;  
  
template<>  
class task_completion_event<void>;  
```  
  
#### パラメーター  
 `_ResultType`  
 この `task_completion_event` クラスの結果の型。  
  
 `T`  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[task\_completion\_event::task\_completion\_event コンストラクター](../Topic/task_completion_event::task_completion_event%20Constructor.md)|`task_completion_event` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[task\_completion\_event::set メソッド](../Topic/task_completion_event::set%20Method.md)|オーバーロードされます。  タスクの完了イベントを設定します。|  
|[task\_completion\_event::set\_exception メソッド](../Topic/task_completion_event::set_exception%20Method.md)|オーバーロードされます。  このイベントに関連付けられているすべてのタスクに例外を反映します。|  
  
## 解説  
 タスクを作成するシナリオで、将来のいずれかの時点でタスクが終了し、そのタスクの継続が実行されるようにスケジュールする必要がある場合、タスクの完了イベントから作成されるタスクを使用します。  `task_completion_event` には、作成するタスクと同じ型を含める必要があります。また、その型の値を使用し、タスクの完了イベントで set メソッドを呼び出すと、関連するタスクが完了し、その値が結果としてタスクの継続に渡されます。  
  
 タスクの完了イベントがシグナルを受け取らない場合、そのイベントから作成されたタスクは、イベントが破棄されるときに取り消されます。  
  
 `task_completion_event` は、スマート ポインターのように動作し、値渡しされる必要があります。  
  
## 継承階層  
 `task_completion_event`  
  
## 必要条件  
 **ヘッダー:** ppltasks.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task Class](http://msdn.microsoft.com/ja-jp/5389e8a5-5038-40b6-844a-55e9b58ad35f)