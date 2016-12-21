---
title: "スケジュール グループ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "スケジュール グループ"
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# スケジュール グループ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このドキュメントでは、同時実行ランタイムのスケジュール グループの役割について説明します。 A *スケジュール グループ* で、または、関連するタスク グループ化します。 すべてのスケジューラは、1 つまたは複数のスケジュール グループを持ちます。 スケジュール グループは、タスク間で高いレベルの局所性が求められる場合 (たとえば、関連するタスクのグループが同一プロセッサ ノードでの実行によって恩恵を受ける場合) に使用します。 逆に、アプリケーションが特定の品質要件など、一連のタスクに割り当てられている処理リソースの量を制限する場合に、スケジューラ インスタンスを使用します。 スケジューラ インスタンスの詳細については、次を参照してください。 [スケジューラ インスタンス](../../parallel/concrt/scheduler-instances.md)します。  
  
> [!TIP]
>  同時実行ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 タスク スケジューラにより、アプリケーションのパフォーマンスを微調整できますが、あるためにで開始することが勧め、 [並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) または [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) 同時実行ランタイムに慣れていない場合。  
  
 各 `Scheduler` スケジュール上のすべてのノードの既定のスケジュール グループが付きます。 A *スケジューリング ノード* 基になるシステム トポロジにマップします。 どちらの数値が大きい、ランタイムがプロセッサ パッケージごとに 1 つのスケジューリング ノードまたは Non-uniform Memory アーキテクチャ (NUMA) ノードを作成します。 スケジュール グループとタスクを明示的に関連付けるはない場合、スケジューラは、タスクを追加するグループを選択します。  
  
  `SchedulingProtocol` スケジューラ ポリシーが、スケジューラが実行されている各スケジュール グループのタスクの順序に影響します。  `SchedulingProtocol` に設定されている `EnhanceScheduleGroupLocality` (既定値は、)、タスク スケジューラは、それが実行されている場合、現在のタスクが終了または生成協調的、スケジュール グループから次のタスクを選択します。 タスク スケジューラは、次の使用可能なグループに移動する前に、作業の現在のスケジュール グループを検索します。 これに対し、 `SchedulingProtocol` に設定されている `EnhanceForwardProgress`, 、各タスクが終了または生成後に、スケジューラが次のスケジュール グループに移動します。 これらのポリシーの比較は、次を参照してください。 [方法: オーダーの実行に影響を使用してスケジュール グループ](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)します。  
  
 ランタイムを使用して、 [concurrency::schedulegroup](../Topic/ScheduleGroup%20Class.md) スケジュール グループを表すクラス。 作成する、 `ScheduleGroup` オブジェクトを呼び出し、 [concurrency::CurrentScheduler::CreateScheduleGroup](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md) または [concurrency::Scheduler::CreateScheduleGroup](../Topic/Scheduler::CreateScheduleGroup%20Method.md) メソッドです。 ランタイムでは、参照カウントのメカニズムを使用して、制御の有効期間 `ScheduleGroup` オブジェクトの場合と同様 `Scheduler` オブジェクトです。 作成するときに、 `ScheduleGroup` オブジェクトのランタイムでは、カウンターを 1 つの参照が設定されます。  [Concurrency::ScheduleGroup::Reference](../Topic/ScheduleGroup::Reference%20Method.md) メソッドは、いずれかによって参照カウンターをインクリメントします。  [Concurrency::ScheduleGroup::Release](../Topic/ScheduleGroup::Release%20Method.md) メソッドを 1 つの参照カウンターです。  
  
 同時実行ランタイムでさまざまな種類では、スケジュール グループと共にオブジェクトを関連付けることができます。 たとえば、 [concurrency::agent](../../parallel/concrt/reference/agent-class.md) などのクラスとメッセージのブロック クラス [concurrency::unbounded_buffer](../Topic/unbounded_buffer%20Class.md), 、[concurrency::join](../Topic/join%20Class.md), 、および同時実行制御::[タイマー](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d5d4c847-5ad6-4c7f-b35b-d0b6f446d8b4/locales/en-US), を受け取るコンス トラクターのオーバー ロードされたバージョンを提供、 `ScheduleGroup` オブジェクトです。 ランタイムを使用して、 `Scheduler` これに関連付けられているオブジェクト `ScheduleGroup` タスクをスケジュールするオブジェクト。  
  
 使用することも、 [concurrency::ScheduleGroup::ScheduleTask](../Topic/ScheduleGroup::ScheduleTask%20Method.md) 軽量タスクをスケジュールする方法です。 軽量タスクの詳細については、次を参照してください。 [軽量タスク](../../parallel/concrt/lightweight-tasks.md)します。  
  
## <a name="example"></a>例  
 使用してスケジュール タスクの実行順序を制御するグループを設定する例については、次を参照してください。 [方法: オーダーの実行に影響を使用してスケジュール グループ](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)します。  
  
## <a name="see-also"></a>関連項目  
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [スケジューラ インスタンス](../../parallel/concrt/scheduler-instances.md)   
 [方法: スケジュール グループを使用して、実行の順序に影響を与える](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)

