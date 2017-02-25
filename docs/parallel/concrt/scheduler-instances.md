---
title: "スケジューラ インスタンス | Microsoft Docs"
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
  - "スケジューラ インスタンス"
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# スケジューラ インスタンス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、同時実行ランタイムでのスケジューラ インスタンスのロールをスケジューラ インスタンスを作成および管理するために [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) と [concurrency::CurrentScheduler](../Topic/CurrentScheduler%20Class.md) クラスを使用する方法を示します。  スケジューラ インスタンスは、明示的なスケジューリング ポリシーを特定の種類の作業負荷に関連付ける場合に役立ちます。  たとえば、昇格したスレッド優先順位で一部のタスクを実行するようにスケジューラ インスタンスを 1 つ作成し、他のタスクについては既定のスケジューラを使用して通常のスレッド優先順位で実行することができます。  
  
> [!TIP]
>  同時実行ランタイムには既定のスケジューラが備わっているため、アプリケーションでスケジューラを作成する必要はありません。  タスク スケジューラではアプリケーションのパフォーマンスを微調整できるため、同時実行ランタイムを初めて使用する場合は、[並列パターン ライブラリ \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md) または[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)から始めることをお勧めします。  
  
##  <a name="top"></a> セクション  
  
-   [Scheduler クラスおよび CurrentScheduler クラス](#classes)  
  
-   [スケジューラ インスタンスの作成](#creating)  
  
-   [スケジューラ インスタンスの有効期間の管理](#managing)  
  
-   [メソッドおよび機能](#features)  
  
-   [例](#example)  
  
##  <a name="classes"></a> Scheduler クラスおよび CurrentScheduler クラス  
 タスク スケジューラにより、アプリケーションは 1 つ以上の*スケジューラ インスタンス*を使用して作業をスケジュールできます。  [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) クラスは、スケジューラ インスタンスを表し、タスクのスケジューリングに関連する機能をカプセル化します。  
  
 スケジューラにアタッチされるスレッドは、*実行コンテキスト*、または単に*コンテキスト*と呼ばれます。  現在のコンテキストでは任意の時点に 1 つのスケジューラをアクティブにすることができます。  アクティブ スケジューラは、*現在のスケジューラ*とも呼ばれます。  同時実行ランタイムでは、現在のスケジューラへのアクセスを提供するために [concurrency::CurrentScheduler](../Topic/CurrentScheduler%20Class.md) クラスを使用します。  あるコンテキストの現在のスケジューラは、別のコンテキストの現在のスケジューラとは異なる場合があります。  ランタイムでは、現在のスケジューラのプロセス レベルでの表現は提供されません。  
  
 通常、現在のスケジューラへのアクセスには `CurrentScheduler` クラスが使用されます。  `Scheduler` クラスは、現在のスケジューラ以外のスケジューラを管理する必要がある場合に役立ちます。  
  
 次のセクションでは、スケジューラ インスタンスの作成方法および管理方法について説明します。  これらのタスクを示す完全な例については、「[方法: スケジューラ インスタンスを管理する](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)」を参照してください。  
  
 \[[トップ](#top)\]  
  
##  <a name="creating"></a> スケジューラ インスタンスの作成  
 `Scheduler` オブジェクトを作成する方法には次の 3 つがあります。  
  
-   スケジューラが存在しない場合に、ランタイム機能 \(たとえば、並列アルゴリズム\) を使用して作業を実行すると、ランタイムにより既定のスケジューラが作成される。  既定のスケジューラは、並列処理を開始するコンテキストの現在のスケジューラとなります。  
  
-   [concurrency::CurrentScheduler::Create](../Topic/CurrentScheduler::Create%20Method.md) のメソッドは、特定のポリシーをを現在のコンテキストに関連付けるそのスケジューラを使用する `Scheduler` オブジェクトを作成します。  
  
-   [concurrency::Scheduler::Create](../Topic/Scheduler::Create%20Method.md) のメソッドは、特定のポリシーを使用するが作成され、現在のコンテキストに関連付ける `Scheduler` オブジェクトを示します。  
  
 ランタイムで既定のスケジューラを作成できるようにすると、すべての同時実行タスクで同じスケジューラを共有できます。  通常は、[並列パターン ライブラリ](../../parallel/concrt/parallel-patterns-library-ppl.md) \(PPL\) または[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)によって提供される機能を使用して並列処理を実行します。  したがって、直接スケジューラを操作してそのポリシーまたは有効期間を制御する必要はありません。  PPL またはエージェント ライブラリを使用すると、スケジューラが存在しない場合には、ランタイムにより既定のスケジューラが作成され、そのスケジューラが各コンテキストの現在のスケジューラとなります。  スケジューラを作成し、それを現在のスケジューラとして設定すると、ランタイムはそのスケジューラを使用してタスクをスケジュールします。  特定のスケジューリング ポリシーが必要な場合に限り、追加のスケジューラ インスタンスを作成してください。  スケジューラに関連するポリシーの詳細については、「[スケジューラ ポリシー](../../parallel/concrt/scheduler-policies.md)」を参照してください。  
  
 \[[トップ](#top)\]  
  
##  <a name="managing"></a> スケジューラ インスタンスの有効期間の管理  
 ランタイムは、参照カウント メカニズムを使用して `Scheduler` オブジェクトの有効期間を制御します。  
  
 `CurrentScheduler::Create` メソッドまたは `Scheduler::Create` メソッドを使用して `Scheduler` オブジェクトを作成すると、ランタイムにより、そのスケジューラの参照カウントの初期値が 1 に設定されます。  ランタイムは [concurrency::Scheduler::Attach](../Topic/Scheduler::Attach%20Method.md) のメソッドを呼び出すときに参照カウントをインクリメントします。  `Scheduler::Attach` メソッドは、`Scheduler` オブジェクトを現在のコンテキストに関連付けます。  これにより、それが現在のスケジューラとなります。  `CurrentScheduler::Create` メソッドを呼び出すと、ランタイムにより `Scheduler` オブジェクトが作成され、そのオブジェクトが現在のコンテキストに関連付けられます \(さらに参照カウントが 1 に設定されます\)。  また `Scheduler` オブジェクトの参照カウントをインクリメントするには [concurrency::Scheduler::Reference](../Topic/Scheduler::Reference%20Method.md) のメソッドを使用できます。  
  
 ランタイムでは、現在のスケジューラをデタッチし [concurrency::CurrentScheduler::Detach](../Topic/CurrentScheduler::Detach%20Method.md) のメソッドを呼び出すデクリメントしましたりまたは [concurrency::Scheduler::Release](../Topic/Scheduler::Release%20Method.md) のメソッドを呼び出すときに参照カウントを。  参照カウントが 0 に達すると、スケジュールされたタスクがすべて終了した後、ランタイムにより `Scheduler` オブジェクトが破棄されます。  実行中のタスクは、現在のスケジューラの参照カウントをインクリメントできます。  したがって、参照カウントが 0 に達し、タスクが参照カウントをインクリメントした場合、参照カウントが再び 0 に達し、すべてのタスクが終了するまで、ランタイムは `Scheduler` オブジェクトを破棄しません。  
  
 ランタイムは、コンテキストごとに `Scheduler` オブジェクトの内部スタックを保持します。  `Scheduler::Attach` メソッドまたは `CurrentScheduler::Create` メソッドを呼び出すと、ランタイムはその `Scheduler` オブジェクトを現在のコンテキストのスタックにプッシュします。  これにより、それが現在のスケジューラとなります。  `CurrentScheduler::Detach` を呼び出すと、ランタイムは、現在のコンテキストのスタックから現在のスケジューラをポップし、前のスケジューラを現在のスケジューラとして設定します。  
  
 ランタイムは、スケジューラ インスタンスの有効期間を管理する複数の方法を提供します。  次の表に、現在のコンテキストに対してスケジューラを作成またはアタッチするメソッドごとに、現在のコンテキストからスケジューラを解放またはデタッチする適切なメソッドを示します。  
  
|作成メソッドまたはアタッチ メソッド|解放メソッドまたはデタッチ メソッド|  
|------------------------|------------------------|  
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|  
|`Scheduler::Create`|`Scheduler::Release`|  
|`Scheduler::Attach`|`CurrentScheduler::Detach`|  
|`Scheduler::Reference`|`Scheduler::Release`|  
  
 不適切な解放メソッドまたはデタッチ メソッドを呼び出すと、ランタイムで未定義の動作が発生します。  
  
 ランタイムにより既定のスケジューラが作成される機能 \(たとえば、PPL\) を使用する場合、そのスケジューラを解放またはデタッチしないでください。  ランタイムは、作成したスケジューラの有効期間を管理します。  
  
 すべてのタスクが終了するまで、ランタイムは `Scheduler` オブジェクトを破棄しません。このため、`Scheduler` オブジェクトが破棄されると [concurrency::Scheduler::RegisterShutdownEvent](../Topic/Scheduler::RegisterShutdownEvent%20Method.md) のメソッドまたは通知を受け取るために [concurrency::CurrentScheduler::RegisterShutdownEvent](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md) のメソッドを使用できます。  これは `Scheduler` オブジェクトによりスケジュールされたタスクがすべて終了するのを待機する必要がある場合に活用できます。  
  
 \[[トップ](#top)\]  
  
##  <a name="features"></a> メソッドおよび機能  
 このセクションでは、`CurrentScheduler` クラスおよび `Scheduler` クラスの重要なメソッドについて概説します。  
  
 `CurrentScheduler` クラスは、現在のコンテキストで使用するスケジューラを作成するためのヘルパーと考えてください。  `Scheduler` クラスにより、別のコンテキストに属するスケジューラを制御できます。  
  
 次の表に、`CurrentScheduler` クラスで定義されている重要なメソッドを示します。  
  
|方法|説明|  
|--------|--------|  
|[Create](../Topic/CurrentScheduler::Create%20Method.md)|指定したポリシーを使用する `Scheduler` オブジェクトを作成し、それを現在のコンテキストに関連付けます。|  
|[Get](../Topic/CurrentScheduler::Get%20Method.md)|現在のコンテキストに関連付けられている `Scheduler` オブジェクトへのポインターを取得します。  このメソッドは、`Scheduler` オブジェクトの参照カウントをインクリメントしません。|  
|[デタッチ](../Topic/CurrentScheduler::Detach%20Method.md)|現在のコンテキストから現在のスケジューラをデタッチし、前のスケジューラを現在のスケジューラとして設定します。|  
|[RegisterShutdownEvent](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md)|現在のスケジューラが破棄されたときにランタイムが設定するイベントを登録します。|  
|[CreateScheduleGroup](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md)|現在のスケジューラで [concurrency::ScheduleGroup](../Topic/ScheduleGroup%20Class.md) オブジェクトを作成します。|  
|[ScheduleTask](../Topic/CurrentScheduler::ScheduleTask%20Method.md)|現在のスケジューラのスケジューリング キューに軽量タスクを追加します。|  
|[GetPolicy](../Topic/CurrentScheduler::GetPolicy%20Method.md)|現在のスケジューラに関連付けられているポリシーのコピーを取得します。|  
  
 次の表に、`Scheduler` クラスで定義されている重要なメソッドを示します。  
  
|方法|説明|  
|--------|--------|  
|[Create](../Topic/Scheduler::Create%20Method.md)|指定したポリシーを使用する `Scheduler` オブジェクトを作成します。|  
|[アタッチ](../Topic/Scheduler::Attach%20Method.md)|`Scheduler` オブジェクトを現在のコンテキストに関連付けます。|  
|[参照](../Topic/Scheduler::Reference%20Method.md)|`Scheduler` オブジェクトの参照カウンターをインクリメントします。|  
|[リリース](../Topic/Scheduler::Release%20Method.md)|`Scheduler` オブジェクトの参照カウンターをデクリメントします。|  
|[RegisterShutdownEvent](../Topic/Scheduler::RegisterShutdownEvent%20Method.md)|`Scheduler` オブジェクトが破棄されたときにランタイムが設定するイベントを登録します。|  
|[CreateScheduleGroup](../Topic/Scheduler::CreateScheduleGroup%20Method.md)|`Scheduler` オブジェクトで [concurrency::ScheduleGroup](../Topic/ScheduleGroup%20Class.md) オブジェクトを作成します。|  
|[ScheduleTask](../Topic/Scheduler::ScheduleTask%20Method.md)|`Scheduler` オブジェクトから軽量タスクをスケジュールします。|  
|[GetPolicy](../Topic/Scheduler::GetPolicy%20Method.md)|`Scheduler` オブジェクトに関連付けられているポリシーのコピーを取得します。|  
|[SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)|ランタイムが既定のスケジューラを作成したときに、そのランタイムが使用するポリシーを設定します。|  
|[ResetDefaultSchedulerPolicy](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md)|既定のポリシーを、`SetDefaultSchedulerPolicy` の呼び出し前にアクティブになっていたポリシーに戻します。  この呼び出しの後に既定のスケジューラが作成される場合、ランタイムは既定のポリシー設定を使用してそのスケジューラを作成します。|  
  
 \[[トップ](#top)\]  
  
##  <a name="example"></a> 例  
 スケジューラ インスタンスを作成および管理する方法の基本的な例については、「[方法: スケジューラ インスタンスを管理する](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)」を参照してください。  
  
## 参照  
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [方法: スケジューラ インスタンスを管理する](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [スケジューラ ポリシー](../../parallel/concrt/scheduler-policies.md)   
 [スケジュール グループ](../../parallel/concrt/schedule-groups.md)