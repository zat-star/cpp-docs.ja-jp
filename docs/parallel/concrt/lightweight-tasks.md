---
title: "軽量タスク | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "軽量タスク"
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 軽量タスク
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、同時実行ランタイムでの軽量タスクの役割について説明します。  *軽量タスク*は、`concurrency::Scheduler` オブジェクトまたは `concurrency::ScheduleGroup` オブジェクトから直接スケジュールするタスクです。  軽量タスクは、Windows API の [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) 関数に指定する関数と類似しています。  したがって、軽量タスクは、既存のコードを改変して同時実行ランタイムのスケジュール機能を使用する場合に有用です。  同時実行ランタイム自体は、非同期エージェントのスケジュールおよび非同期メッセージ ブロック間におけるメッセージの送信に、軽量タスクを使用します。  
  
> [!TIP]
>  同時実行ランタイムには既定のスケジューラが備わっているため、アプリケーションでスケジューラを作成する必要はありません。  タスク スケジューラではアプリケーションのパフォーマンスを微調整できるため、同時実行ランタイムを初めて使用する場合は、[並列パターン ライブラリ \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md) または[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)から始めることをお勧めします。  
  
 軽量タスクは、非同期エージェントおよびタスク グループよりもオーバーヘッドが少なくて済みます。  たとえば、軽量タスクが終了しても、ランタイムは通知を行いません。  さらに、軽量タスクからスローされた例外を、ランタイムはキャッチまたは処理しません。  例外処理および軽量タスクの詳細については、「[例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)」を参照してください。  
  
 ほとんどのタスクで、タスク グループ、並列アルゴリズムなどの、より信頼性の高い機能を使用することをお勧めします。これらを使用することにより、複雑なタスクをより基本的なタスクに簡単に分割することができるためです。  タスク グループの詳細については、「[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)」を参照してください。  並列アルゴリズムの詳細については、「[並列アルゴリズム](../Topic/Parallel%20Algorithms.md)」を参照してください。  
  
 軽量タスクを作成するには、[concurrency::ScheduleGroup::ScheduleTask](../Topic/ScheduleGroup::ScheduleTask%20Method.md)、[concurrency::CurrentScheduler::ScheduleTask](../Topic/CurrentScheduler::ScheduleTask%20Method.md)、または [concurrency::Scheduler::ScheduleTask](../Topic/Scheduler::ScheduleTask%20Method.md) のメソッドを呼び出します。  シャットダウンするために終了したとき、親スケジューラが待機または [concurrency::event](../Topic/event%20Class.md) オブジェクトなどの同期機構を使用する軽量タスクを待機する。  
  
## 例  
 既存のコードを改変して軽量タスクを使用する方法を示した例については、「[チュートリアル: 既存のコードを改変して軽量タスクを使用する](../Topic/Walkthrough:%20Adapting%20Existing%20Code%20to%20Use%20Lightweight%20Tasks.md)」を参照してください。  
  
## 参照  
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [チュートリアル: 既存のコードを改変して軽量タスクを使用する](../Topic/Walkthrough:%20Adapting%20Existing%20Code%20to%20Use%20Lightweight%20Tasks.md)