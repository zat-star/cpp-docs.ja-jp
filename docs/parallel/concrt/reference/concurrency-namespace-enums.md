---
title: "concurrency 名前空間を持つ列挙型 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a40e3b2d-ad21-4229-9880-2cfa84f7ab8f
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 8f7488ff07c9789e2d5f35056de390a5bc464f56
ms.openlocfilehash: ff187e827b2dd979466b746eee297235e6a6c0ca
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-enums"></a>concurrency 名前空間を持つ列挙型
||||  
|-|-|-|  
|[Agents_EventType 列挙型](#agents_eventtype)|[ConcRT_EventType 列挙型](#concrt_eventtype)|[Concrt_TraceFlags 列挙型](#concrt_traceflags)|  
|[CriticalRegionType 列挙型](#criticalregiontype)|[DynamicProgressFeedbackType 列挙型](#dynamicprogressfeedbacktype)|[PolicyElementKey 列挙型](#policyelementkey)|  
|[SchedulerType 列挙型](#schedulertype)|[SchedulingProtocolType 列挙型](#schedulingprotocoltype)|[SwitchingProxyState 列挙型](#switchingproxystate)|  
|[WinRTInitializationType 列挙型](#winrtinitializationtype)|[agent_status 列挙体](#agent_status)|[join_type 列挙体](#join_type)|  
|[message_status 列挙型](#message_status)|[task_group_status 列挙型](#task_group_status)|  
  
##  <a name="a-nameagentstatusa--agentstatus-enumeration"></a><a name="agent_status"></a>agent_status 列挙体  
 `agent` の有効な状態。  
  
```
enum agent_status;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`agent_canceled`|`agent` は取り消されました。|  
|`agent_created`|`agent`作成されましたが、開始されていません。|  
|`agent_done`|`agent`取り消されることは正常に完了します。|  
|`agent_runnable`|`agent`された開始されるが入力されていない、`run`メソッドです。|  
|`agent_started`|`agent`が開始します。|  

### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期エージェント](../../../parallel/concrt/asynchronous-agents.md)します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h

##  <a name="a-nameagentseventtypea--agentseventtype-enumeration"></a><a name="agents_eventtype"></a>Agents_EventType 列挙型  
 エージェント ライブラリによって提供されるトレース機能を使用してトレースできるイベントの種類。  
  
```
enum Agents_EventType;
```  

### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`AGENTS_EVENT_CREATE`|イベントの種類を表すオブジェクトの作成|  
|`AGENTS_EVENT_DESTROY`|イベントの種類を表すオブジェクトの削除|  
|`AGENTS_EVENT_END`|イベントの種類を表すいくつかの処理の終了処理|  
|`AGENTS_EVENT_LINK`|メッセージ ブロックのリンクを表すイベントの種類|  
|`AGENTS_EVENT_NAME`|オブジェクトの名前を表すイベントの種類|  
|`AGENTS_EVENT_SCHEDULE`|プロセスのスケジュールを表すイベントの種類|  
|`AGENTS_EVENT_START`|いくつかの開始を表すイベントの種類の処理|  
|`AGENTS_EVENT_UNLINK`|イベントの種類を表すメッセージ ブロックのリンクを解除します。|  

### <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h

##  <a name="a-nameconcrteventtypea--concrteventtype-enumeration"></a><a name="concrt_eventtype"></a>ConcRT_EventType 列挙型  
 同時実行ランタイムによって提供されるトレース機能を使用してトレースできるイベントの種類。  
  
```
enum ConcRT_EventType;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`CONCRT_EVENT_ATTACH`|スケジューラへのアタッチの動作を表すイベントの種類。|  
|`CONCRT_EVENT_BLOCK`|コンテキストのブロックの動作を表すイベントの種類。|  
|`CONCRT_EVENT_DETACH`|スケジューラからデタッチの動作を表すイベントの種類。|  
|`CONCRT_EVENT_END`|開始/終了イベントのペアの最初をマークするイベントの種類。|  
|`CONCRT_EVENT_GENERIC`|その他のイベントに使用されるイベントの種類。|  
|`CONCRT_EVENT_IDLE`|アイドル状態になるコンテキストの動作を表すイベントの種類。|  
|`CONCRT_EVENT_START`|開始/終了イベントのペアの最初をマークするイベントの種類。|  
|`CONCRT_EVENT_UNBLOCK`|コンテキストのブロック解除の動作を表すイベントの種類。|  
|`CONCRT_EVENT_YIELD`|として生成されるコンテキストの動作を表すイベントの種類。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h

##  <a name="a-nameconcrttraceflagsa--concrttraceflags-enumeration"></a><a name="concrt_traceflags"></a>Concrt_TraceFlags 列挙型  
 イベントの種類のトレース フラグ。  
  
```
enum Concrt_TraceFlags;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`AgentEventFlag`||  
|`AllEventsFlag`||  
|`ContextEventFlag`||  
|`PPLEventFlag`||  
|`ResourceManagerEventFlag`||  
|`SchedulerEventFlag`||  
|`VirtualProcessorEventFlag`||

### <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h

##  <a name="a-namecriticalregiontypea--criticalregiontype-enumeration"></a><a name="criticalregiontype"></a>CriticalRegionType 列挙型  
 コンテキストが存在するクリティカル領域の種類。  
  
```
enum CriticalRegionType;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`InsideCriticalRegion`|コンテキストがクリティカル領域内にあることを示します。 非同期の中断は、クリティカル領域内、スケジューラからは見えません。 このような中断ようなリソース マネージャーが可能になるし、スケジューラをもう一度呼び出す代わりにそれを再開するスレッドの待機します。 このような領域内に取得されたロックは、十分注意で実行する必要があります。|  
|`InsideHyperCriticalRegion`|コンテキストがハイパー クリティカル領域内にあることを示します。 同期および非同期の中断は、ハイパー クリティカル領域内、スケジューラからは見えません。 このような中断またはブロックが発生すると、リソース マネージャーが可能になるし、スケジューラをもう一度呼び出す代わりにそれを再開するスレッドの待機します。 このような領域で取得されたロックは、このような領域の外側で実行されているコードと共有する必要があることはありません。 そうと、予測不可能なデッドロックとします。|  
|`OutsideCriticalRegion`|コンテキストがクリティカル領域の外部にあることを示します。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h 

##  <a name="a-namedynamicprogressfeedbacktypea--dynamicprogressfeedbacktype-enumeration"></a><a name="dynamicprogressfeedbacktype"></a>DynamicProgressFeedbackType 列挙型  
 `DynamicProgressFeedback` ポリシーによって使用され、スケジューラのリソースのバランスを再調整する際の判断基準として、スケジューラから収集された統計情報に従うか、または `Activate` インターフェイスの `Deactivate` メソッドおよび `IVirtualProcessorRoot` メソッドの呼び出しによってアイドル状態との間で状態が変化する仮想プロセッサのみに基づくかを示します。 使用可能なスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey 列挙体](concurrency-namespace-enums.md)します。  
  
```
enum DynamicProgressFeedbackType;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`ProgressFeedbackDisabled`|スケジューラは、進行状況に関する情報を収集しません。 再均衡化に基づいて行われます基になるハードウェア スレッドのサブスクリプション レベルだけにします。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](IExecutionResource-structure.md)します。<br /><br /> この値は、ランタイムで使用するために予約されています。|  
|`ProgressFeedbackEnabled`|スケジューラは、進行状況に関する情報を収集し、リソース マネージャーに渡されます。 リソース マネージャーでは、この統計情報を基になるハードウェア スレッドのサブスクリプション レベルだけでなく、スケジューラの代わりにリソースを再調整を利用します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](IExecutionResource-structure.md)します。|  
##  <a name="a-namejointypea--jointype-enumeration"></a><a name="join_type"></a>join_type 列挙体  
 `join` メッセージング ブロックの種類。  
  
```
enum join_type;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`greedy`|最長一致`join`メッセージング ブロックには、メッセージの伝達にすぐにそのまま使用します。 これにより、方が効率的ですが、ライブのロックをネットワーク構成によって発生する可能性を持ちます。|  
|`non_greedy`|最短`join`メッセージング ブロックのメッセージを延期し、すべてに到着した後、それらを使用します。 これらは確実に動作が、速度が低下します。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  

##  <a name="a-namemessagestatusa--messagestatus-enumeration"></a><a name="message_status"></a>message_status 列挙型  
 ブロックへの `message` オブジェクトの提供に対する有効な応答。  
  
```
enum message_status;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`accepted`|ターゲットは、メッセージを受け入れました。|  
|`declined`|ターゲットでは、メッセージは受け入れられませんでした。|  
|`missed`|ターゲットは、メッセージを受信しようとしていますが、使用できませんでした。|  
|`postponed`|ターゲットは、メッセージを延期します。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  

##  <a name="a-namepolicyelementkeya--policyelementkey-enumeration"></a><a name="policyelementkey"></a>PolicyElementKey 列挙型  
 ポリシー キーは、スケジューラの動作をさまざまな側面から表します。 各ポリシー要素は、キーと値の組み合わせで表現されます。 スケジューラのスケジューラ ポリシーとその影響に関する詳細については、次を参照してください。[タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)します。  
  
```
enum PolicyElementKey;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`ContextPriority`|オペレーティング システム スレッドの優先度、スケジューラ内の各コンテキスト。 このキーが値に設定されている場合`INHERIT_THREAD_PRIORITY`スケジューラ コンテキストは、スケジューラを作成したスレッドの優先順位を継承します。<br /><br /> 有効な値: Windows の有効な値のいずれかの`SetThreadPriority`関数、および特殊な値`INHERIT_THREAD_PRIORITY`<br /><br /> 既定値:`THREAD_PRIORITY_NORMAL`|  
|`ContextStackSize`|キロバイト単位で、スケジューラ内で各コンテキストの予約済みのスタック サイズ。<br /><br /> 有効な値: 正の整数<br /><br /> 既定値: `0`、スタック サイズのプロセスの既定値が使用することを示します。|  
|`DynamicProgressFeedback`|スケジューラのリソースが、スケジューラから収集された、または基になるハードウェア スレッドのサブスクリプション レベルに基づいてのみの統計情報に従う再調整されるかどうかを決定します。 詳細については、次を参照してください。 [DynamicProgressFeedbackType 列挙体](#dynamicprogressfeedbacktype)します。<br /><br /> 有効な値: のメンバー、`DynamicProgressFeedbackType`列挙型か、`ProgressFeedbackEnabled`または`ProgressFeedbackDisabled`<br /><br /> 既定値:`ProgressFeedbackEnabled`|  
|`LocalContextCacheSize`|ときに、`SchedulingProtocol`ポリシー キーが値に設定されている`EnhanceScheduleGroupLocality`、ローカル キューでの仮想プロセッサごとにキャッシュできる実行可能なコンテキストの最大数を指定します。 このようなコンテキストは、発生したため、実行可能になる仮想プロセッサ上で最後先出し (LIFO) の順序で通常実行されます。 このポリシー キーがない場合、`SchedulingProtocol`キーが値に設定されている`EnhanceForwardProgress`します。<br /><br /> 有効な値: 正の整数<br /><br /> 既定値:`8`|  
|`MaxConcurrency`|スケジューラによって必要なレベルの最大同時実行します。 リソース マネージャーは最初にこのような多数の仮想プロセッサを割り当てるしようとします。 特殊な値[MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources)必要な同時実行レベルがコンピューター上のハードウェア スレッドの数と同じであることを示します。 値が指定されている場合`MinConcurrency`、マシン上のハードウェア スレッドの数よりも大きいと`MaxConcurrency`として指定された`MaxExecutionResources`の値`MaxConcurrency`に設定されている一致するようには、発生`MinConcurrency`します。<br /><br /> 有効な値: 正の整数と特別な値`MaxExecutionResources`<br /><br /> 既定値:`MaxExecutionResources`|  
|`MaxPolicyElementKey`|最大ポリシー要素キー。 要素の有効なキーではないです。|  
|`MinConcurrency`|最小同時実行レベル、リソース マネージャーで、スケジューラに提供する必要があります。 スケジューラに割り当てる仮想プロセッサの数は、最小値を下回ることはありません。 特殊な値[MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources)最小同時実行レベルがコンピューター上のハードウェア スレッドの数と同じであることを示します。 値が指定されている場合`MaxConcurrency`がコンピューター上のハードウェア スレッドの数より少ないと`MinConcurrency`として指定された`MaxExecutionResources`の値`MinConcurrency`に設定されている一致するように値を下げた`MaxConcurrency`します。<br /><br /> 有効な値: 正の整数と特別な値`MaxExecutionResources`です。 同時実行ランタイム スケジューラ、値を構築するために使用されるスケジューラ ポリシーの`0`が無効です。<br /><br /> 既定値:`1`|  
|`SchedulerKind`|基になる実行コンテキスト用にスケジューラが利用するスレッドの種類。 詳細については、次を参照してください。 [SchedulerType 列挙体](#schedulertype)します。<br /><br /> 有効な値: のメンバー、`SchedulerType`などの列挙型`ThreadScheduler`<br /><br /> 既定値:`ThreadScheduler`です。 これは、すべてのオペレーティング システムで Win32 スレッドに変換します。|  
|`SchedulingProtocol`|スケジューラによって使用されるスケジューリング アルゴリズムについて説明します。 詳細については、次を参照してください。 [SchedulingProtocolType 列挙体](#schedulingprotocoltype)します。<br /><br /> 有効な値: のメンバー、`SchedulingProtocolType`列挙型か、`EnhanceScheduleGroupLocality`または`EnhanceForwardProgress`<br /><br /> 既定値:`EnhanceScheduleGroupLocality`|  
|`TargetOversubscriptionFactor`|ハードウェア スレッドあたりの仮想プロセッサ数の仮承諾します。 ターゲット オーバー サブスクリプション係数拡大の上限 リソース マネージャーを満たすために、必要に応じて`MaxConcurrency`コンピューター上のハードウェア スレッドにします。<br /><br /> 有効な値: 正の整数<br /><br /> 既定値:`1`|  
|`WinRTInitialization`||  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  

##  <a name="a-nameschedulertypea--schedulertype-enumeration"></a><a name="schedulertype"></a>SchedulerType 列挙型  
 基になる実行コンテキスト用にスケジューラが利用するスレッドの種類を示すために、`SchedulerKind` ポリシーにより使用されます。 使用可能なスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey 列挙体](concurrency-namespace-enums.md)します。  
  
```
enum SchedulerType;
``` 

### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`ThreadScheduler`|通常の Win32 スレッドの明示的な要求を示します。|  
|`UmsThreadDefault`|Visual Studio 2013 での同時実行ランタイムでは、ユーザー モード スケジュール可能 (UMS) スレッドはサポートされていません。 `UmsThreadDefault` ポリシーの値として `SchedulerType` を使用しても、エラーは発生しません。 ただし、そのポリシーで作成されたスケジューラでは、既定で Win32 スレッドが使用されます。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
##  <a name="a-nameschedulingprotocoltypea--schedulingprotocoltype-enumeration"></a><a name="schedulingprotocoltype"></a>SchedulingProtocolType 列挙型  
 スケジューラに使用されるスケジューリング アルゴリズムを記述するために、`SchedulingProtocol` ポリシーによって使用されます。 使用可能なスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey 列挙体](concurrency-namespace-enums.md)します。  
  
```
enum SchedulingProtocolType;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`EnhanceForwardProgress`|スケジューラは、スケジュール グループ間のラウンド ロビンを各タスクを実行した後です。 ブロックされていないコンテキストは一般的最初先出し (FIFO) 方式でスケジュールを設定します。 仮想プロセッサでは、ブロック解除のコンテキストをキャッシュすることはできます。|  
|`EnhanceScheduleGroupLocality`|スケジューラは別々 のスケジュール グループに移動する前に、現在のスケジュール グループ内のタスクで作業を続行します。 ブロックされていないコンテキストでは、仮想プロセッサごとにキャッシュられ、それらをブロック解除する仮想プロセッサして最終先出し (LIFO) 方式で通常スケジュール設定します。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
 
##  <a name="a-nameswitchingproxystatea--switchingproxystate-enumeration"></a><a name="switchingproxystate"></a>SwitchingProxyState 列挙型  
 あるスレッド プロキシから別のスレッド プロキシへの協調的なコンテキスト切り替えを実行するときに、スレッド プロキシの状態を示すために使用します。  
  
```
enum SwitchingProxyState;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`Blocking`|呼び出し元のスレッドが排他的に所有、呼び出し元が後でもう一度実行し、その他のアクションを実行するまでが協調的にブロックしていることを示します。|  
|`Idle`|呼び出し元のスレッドが、スケジューラで不要になったリソース マネージャーに返されることを示します。 ディスパッチされていたコンテキストは、リソース マネージャーでを利用することはありません。|  
|`Nesting`|呼び出し元のスレッドが子スケジューラの入れ子が別のスケジューラにアタッチするために、呼び出し元が必要なことを示します。|  

### <a name="remarks"></a>コメント  
 型のパラメーター`SwitchingProxyState`メソッドに渡された`IThreadProxy::SwitchTo`にリソース マネージャーの呼び出しを行っているスレッド プロキシを処理する方法を指示します。  
  
 この型の使用方法の詳細については、次を参照してください。 [ithreadproxy::switchto](ithreadproxy-structure.md#switchto)します。  
  
##  <a name="a-nametaskgroupstatusa--taskgroupstatus-enumeration"></a><a name="task_group_status"></a>task_group_status 列挙型  
 `task_group` オブジェクトまたは `structured_task_group` オブジェクトの実行状態を示します。 この型の値は、タスク グループに対してスケジュールされたタスクが完了するのを待機している多数のメソッドによって返されます。  
  
```
enum task_group_status;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`canceled`|`task_group` オブジェクトまたは `structured_task_group` オブジェクトは取り消されました。 1 つまたは複数のタスクが実行されていない可能性があります。|  
|`completed`|`task_group` オブジェクトまたは `structured_task_group` オブジェクトのキューに格納されたタスクは、正常に完了しました。|  
|`not_complete`|`task_group` オブジェクトのキューに格納されたタスクは完了していません。 この値は、同時実行ランタイムによって現在返されていないことに注意してください。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** pplinterface.h  

##  <a name="a-namewinrtinitializationtypea--winrtinitializationtype-enumeration"></a><a name="winrtinitializationtype"></a>WinRTInitializationType 列挙型  
 `WinRTInitialization` ポリシーによって使用され、Windows 8 以上のオペレーティング システムで実行されるアプリケーション用のスケジューラ スレッドで、Windows ランタイムを初期化するかどうか、またどのように初期化するかを表します。 使用可能なスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey 列挙体](concurrency-namespace-enums.md)します。  
  
```
enum WinRTInitializationType;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`DoNotInitializeWinRT`|アプリケーションが Windows 8 またはそれ以降のバージョンのオペレーティング システムで実行される場合、スケジューラ内のスレッドは、Windows ランタイムを初期化しません。|  
|`InitializeWinRTAsMTA`|アプリケーションが Windows 8 またはそれ以降のバージョンのオペレーティング システムで実行される場合、スケジューラ内の各スレッドは、Windows ランタイムを初期化し、マルチスレッド アパートメントの一部であることを宣言します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  

## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

