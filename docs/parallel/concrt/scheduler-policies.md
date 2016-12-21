---
title: "スケジューラ ポリシー | Microsoft Docs"
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
  - "スケジューラ ポリシー"
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
caps.latest.revision: 12
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# スケジューラ ポリシー
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、同時実行ランタイムでのスケジューラ ポリシーの役割について説明します。  スケジューラでタスクを管理する場合、*スケジューラ ポリシー*によって、スケジューラが使用する方法を制御します。  たとえば、`THREAD_PRIORITY_NORMAL` で実行されるタスクと `THREAD_PRIORITY_HIGHEST`で実行するそのほかのタスクを必要とするアプリケーションがあるとします。2 種類のスケジューラ インスタンスを作成する: `THREAD_PRIORITY_NORMAL` と `ContextPriority` ポリシーを指定すると `THREAD_PRIORITY_HIGHEST`と同じポリシーを指定する別の 1 つ。  
  
 スケジューラ ポリシーを使用して、使用できる処理リソースを分割して、各スケジューラに固定の一連のリソースを割り当てることができます。  たとえば、4 つまでのプロセッサに対応した並列アルゴリズムを考えてみます。  この場合、タスクで同時に使用されるプロセッサを 4 つまでに制限するスケジューラ ポリシーを作成できます。  
  
> [!TIP]
>  同時実行ランタイムは既定のスケジューラを提供します。  したがって、アプリケーションで 1 を作成する必要はありません。  タスク スケジューラではアプリケーションのパフォーマンスを微調整できるため、同時実行ランタイムを初めて使用する場合は、[並列パターン ライブラリ \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md) または[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)から始めることをお勧めします。  
  
 スケジューラ インスタンスの作成に [concurrency::CurrentScheduler::Create](../Topic/CurrentScheduler::Create%20Method.md)、[concurrency::Scheduler::Create](../Topic/Scheduler::Create%20Method.md)、または [concurrency::Scheduler::SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md) のメソッドを使用すると、スケジューラの動作を指定するキーと値のペアのコレクションを含む [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) オブジェクトを提供します。  `SchedulerPolicy` コンストラクターは、可変個の引数を受け取ります。  1 番目の引数は、指定するポリシー要素の数です。  残りの引数は、各ポリシー要素を表すキーと値のペアです。  次の例では、3 つのポリシー要素を指定する `SchedulerPolicy` オブジェクトが作成されます。  ランタイムは、指定されていないポリシー キーに対して既定値を使用します。  
  
 [!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/CPP/scheduler-policies_1.cpp)]  
  
 [concurrency::PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md) の列挙体はタスク スケジューラに関連付けられているポリシー キーを定義します。  次の表で、ポリシー キーと、ランタイムが各ポリシー キーに対して使用する既定値について説明します。  
  
|ポリシー キー|説明|既定値|  
|-------------|--------|---------|  
|`SchedulerKind`|タスクをスケジュールするために使用するスレッドの種類を指定する [concurrency::SchedulerType](../Topic/SchedulerType%20Enumeration.md) 値。|`ThreadScheduler` \(通常スレッドを使用\)。  このキーの有効な値です。|  
|`MaxConcurrency`|スケジューラが使用する同時実行リソースの最大数を指定する `unsigned int` 値。|[concurrency::MaxExecutionResources](../Topic/MaxExecutionResources%20Constant.md)|  
|`MinConcurrency`|スケジューラが使用する同時実行リソースの最小数を指定する `unsigned int` 値。|`1`|  
|`TargetOversubscriptionFactor`|各処理リソースに割り当てるスレッドの数を指定する `unsigned int` 値。|`1`|  
|`LocalContextCacheSize`|各仮想プロセッサのローカル キューにキャッシュすることができるコンテキストの最大数を指定する `unsigned int` 値。|`8`|  
|`ContextStackSize`|各コンテキスト用に予約するスタックのサイズ \(キロバイト単位\) を指定する `unsigned int` 値。|`0` \(既定のスタック サイズを使用\)|  
|`ContextPriority`|各コンテキストのスレッド優先順位を指定する `int` 値。  これには、[SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) または `INHERIT_THREAD_PRIORITY` に渡すことができる任意の値を使用できます。|`THREAD_PRIORITY_NORMAL`|  
|`SchedulingProtocol`|使用するスケジューリング アルゴリズムを指定する [concurrency::SchedulingProtocolType](../Topic/SchedulingProtocolType%20Enumeration.md) 値。|`EnhanceScheduleGroupLocality`|  
|`DynamicProgressFeedback`|統計ベースの進行状況情報にリソースのバランスを再調整するかどうかを指定する [concurrency::DynamicProgressFeedbackType](../Topic/DynamicProgressFeedbackType%20Enumeration.md) 値。<br /><br /> **メモ** このポリシーに設定しないでください。`ProgressFeedbackDisabled` これは、ランタイムによる使用が予約されています。|`ProgressFeedbackEnabled`|  
  
 各スケジューラは、タスクをスケジュールするとき、独自のポリシーを使用します。  1 個のスケジューラに関連付けられているポリシーは、そのほかのスケジューラの動作には影響しません。  また、`Scheduler` オブジェクトを作成した後にスケジューラ ポリシーを変更することはできません。  
  
> [!IMPORTANT]
>  ランタイムによって作成されるスレッドの属性を制御するには、スケジューラ ポリシーだけを使用します。  これにより、未定義の動作が発生する可能性があるため、ランタイムによって作成されるスレッドの関係または優先順位を変更しないでください。  
  
 スケジューラを明示的に作成しない場合は、ランタイムによって既定のスケジューラが作成されます。  そのスケジューラで使用できるアプリケーションで既定のスケジューラを使用するがポリシーを指定する場合は、並列処理をスケジュールする前に [concurrency::Scheduler::SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md) のメソッドを呼び出します。  `Scheduler::SetDefaultSchedulerPolicy` メソッドを呼び出さない場合、ランタイムは表の既定ポリシー値を使用します。  
  
 スケジューラのポリシーのコピーを取得するために [concurrency::CurrentScheduler::GetPolicy](../Topic/CurrentScheduler::GetPolicy%20Method.md) と [concurrency::Scheduler::GetPolicy](../Topic/Scheduler::GetPolicy%20Method.md) のメソッドを使用します。  これらのメソッドから取得するポリシー値は、スケジューラを作成するときに指定したポリシー値とは異なる場合があります。  
  
## 例  
 スケジューラの動作を制御するために特定のスケジューラ ポリシーを使用して例を確認するには [方法: 特定のスケジューラ ポリシーを指定する](../Topic/How%20to:%20Specify%20Specific%20Scheduler%20Policies.md) と [方法: 特定のスケジューラ ポリシーを使用するエージェントを作成する](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)を参照してください。  
  
## 参照  
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [方法: 特定のスケジューラ ポリシーを指定する](../Topic/How%20to:%20Specify%20Specific%20Scheduler%20Policies.md)   
 [方法: 特定のスケジューラ ポリシーを使用するエージェントを作成する](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)