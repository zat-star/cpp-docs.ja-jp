---
title: "concurrency 名前空間関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::Alloc
- concrt/concurrency::DisableTracing
- concrt/concurrency::EnableTracing
- concrtrm/concurrency::GetExecutionContextId
- concrtrm/concurrency::GetOSVersion
- concrtrm/concurrency::GetProcessorNodeCount
- concrtrm/concurrency::GetSchedulerId
- agents/concurrency::asend
- ppltasks/concurrency::cancel_current_task
- ppltasks/concurrency::create_async
- ppltasks/concurrency::create_task
- concurrent_vector/concurrency::internal_assign_iterators
- ppl/concurrency::interruption_point
- agents/concurrency::make_choice
- agents/concurrency::make_greedy_join
- ppl/concurrency::make_task
- ppl/concurrency::parallel_buffered_sort
- ppl/concurrency::parallel_for_each
- ppl/concurrency::parallel_invoke
- ppl/concurrency::parallel_reduce
- ppl/concurrency::parallel_sort
- agents/concurrency::receive
- ppl/concurrency::run_with_cancellation_token
- pplconcrt/concurrency::set_ambient_scheduler
- concrt/concurrency::set_task_execution_resources
- ppltasks/concurrency::task_from_exception
- ppltasks/concurrency::task_from_result
- concrt/concurrency::wait
- ppltasks/concurrency::when_all
- ppltasks/concurrency::when_any
dev_langs:
- C++
ms.assetid: 520a6dff-9324-4df2-990d-302e3050af6a
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 4a01f48a7d087281ab1e9222d1077e92ab8b0d6c
ms.openlocfilehash: 179913d9a7f0b39349b6a6c85fb03837c98041bc
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-functions"></a>concurrency 名前空間の関数
||||  
|-|-|-|  
|[Alloc](#alloc)|[CreateResourceManager](#createresourcemanager)|[DisableTracing](#disabletracing)|  
|[EnableTracing](#enabletracing)|[無料](#free)|[GetExecutionContextId](#getexecutioncontextid)|  
|[GetOSVersion](#getosversion)|[GetProcessorCount](#getprocessorcount)|[GetProcessorNodeCount](#getprocessornodecount)|  
|[GetSchedulerId](#getschedulerid)|[Trace_agents_register_name](#trace_agents_register_name)|[asend](#asend)|  
|[cancel_current_task](#cancel_current_task)|[clear](#clear)|[create_async](#create_async)|  
|[create_task](#create_task)|[get_ambient_scheduler](#get_ambient_scheduler)|[internal_assign_iterators](#internal_assign_iterators)|  
|[interruption_point](#interruption_point)|[is_current_task_group_canceling](#is_current_task_group_canceling)|[make_choice](#make_choice)|  
|[make_greedy_join](#make_greedy_join)|[make_join](#make_join)|[make_task](#make_task)|  
|[parallel_buffered_sort](#parallel_buffered_sort)|[parallel_for](#parallel_for)|[parallel_for_each](#parallel_for_each)|  
|[parallel_invoke](#parallel_invoke)|[parallel_radixsort](#parallel_radixsort)|[parallel_reduce](#parallel_reduce)|  
|[parallel_sort](#parallel_sort)|[parallel_transform](#parallel_transform)|[表示されます。](#receive)|  
|[run_with_cancellation_token](#run_with_cancellation_token)|[送信](#send)|[set_ambient_scheduler](#set_ambient_scheduler)|  
|[set_task_execution_resources](#set_task_execution_resources)|[swap](#swap)|[task_from_exception](#task_from_exception)|  
|[task_from_result](#task_from_result)|[try_receive](#try_receive)|[待機](#wait)|  
|[when_all](#when_all)|[when_any](#when_any)|  
  
##  <a name="alloc"></a>Alloc  
 同時実行ランタイムのキャッシュ サブアロケータから、指定したサイズのメモリ ブロックを割り当てます。  
  
```
void* __cdecl Alloc(size_t _NumBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 `_NumBytes`  
 割り当てるメモリのバイト数。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリへのポインター。  
  
### <a name="remarks"></a>コメント  
 詳細についてはどのシナリオは、アプリケーションの利点がもたらされるキャッシュ サブアロケータを使用して、次を参照してください。[タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)します。  
  
##  <a name="asend"></a>asend  
 ターゲット ブロックにデータを反映するタスクをスケジュールする非同期送信操作です。  
  
```
template <class T>
bool asend(
    _Inout_ ITarget<T>* _Trg,
    const T& _Data);

template <class T>
bool asend(
    ITarget<T>& _Trg,
    const T& _Data);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 送信されるデータの型。  
  
 `_Trg`  
 ポインターまたはデータの送付先となるターゲットへの参照。  
  
 `_Data`  
 送信されるデータへの参照。  
  
### <a name="return-value"></a>戻り値  
 `true`メソッドが返される前に、メッセージが受け入れられた場合`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[メッセージを渡す関数](../../../parallel/concrt/message-passing-functions.md)します。  
  
##  <a name="cancel_current_task"></a>cancel_current_task  
 現在実行中のタスクを取り消します。 この関数は、タスクの実行を中止して `canceled` 状態に遷移させるために、タスクの本体から呼び出すことができます。  
  
 `task` の本体以外では、この関数を呼び出すシナリオはサポートされません。 これを行うと、アプリケーションのクラッシュや停止など、定義されていない動作が発生します。  
  
```
inline __declspec(noreturn) void __cdecl cancel_current_task();
```  
  
##  <a name="clear"></a>オフ  
 破棄、同時実行キューをクリア現在キューに格納された要素です。 このメソッドは同時実行セーフではありません。  
  
```
template<typename T, class _Ax>
void concurrent_queue<T, _Ax>::clear();
```   
  
### <a name="parameters"></a>パラメーター  
 `T`  
 `_Ax`  
  
##  <a name="create_async"></a>create_async  
 ユーザーが指定したラムダまたは関数オブジェクトに基づいて Windows ランタイムの非同期構造を作成します。 `create_async` の戻り値の型は、`IAsyncAction^`、`IAsyncActionWithProgress<TProgress>^`、`IAsyncOperation<TResult>^`、`IAsyncOperationWithProgress<TResult, TProgress>^` のいずれかで、メソッドに渡されるラムダのシグネチャに基づいています。  
  
```
template<typename _Function>
__declspec(noinline) auto create_async(const _Function& _Func)
    -> decltype(ref new details::_AsyncTaskGeneratorThunk<_Function>(_Func));
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 `_Func`  
 Windows ランタイムの非同期構造の作成元となるラムダまたは関数オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 IAsyncAction で表される非同期構造 ^、IAsyncActionWithProgress\<TProgress > ^、IAsyncOperation\<TResult > ^、または IAsyncOperationWithProgress\<TResult, TProgress > ^ です。 返されるインターフェイスは、関数に渡されるラムダのシグネチャによって異なります。  
  
### <a name="remarks"></a>コメント  
 ラムダの戻り値の型によって、構造がアクションであるか操作であるかが判別されます。  
  
 ラムダが void を返すと、アクションが作成されます。 ラムダが型 `TResult` の結果を返すと、TResult の操作が作成されます。  
  
 ラムダは `task<TResult>` を返すことがあります。この戻り値は、それ自体に非同期操作をカプセル化します。また、非同期操作を表すタスクのチェーンの継続として機能する場合もあります。 この場合、ラムダ自体はインラインで実行されます。これは、タスクが非同期的に実行されたタスクであり、ラムダの戻り値の型がラップ解除され `create_async` によって返される非同期構造を生成するためです。 つまり、あるラムダを返すタスク\<void > 操作、およびタスクを返すラムダが作成される\<TResult > TResult の操作が作成されます。  
  
 ラムダでは、引数を使用しない場合、または&1; つか&2; つの引数を使用する場合があります。 有効な引数は `progress_reporter<TProgress>` と `cancellation_token` です。これらを両方とも使用する場合は、この順序で指定してください。 ラムダで引数を使用しないと、進行状況の報告機能を持たない非同期構造が作成されます。 ラムダで progress_reporter\<TProgress > により`create_async`を毎回型 TProgress の進行状況を報告する非同期構造を返す、 `report` progress_reporter オブジェクトのメソッドが呼び出されます。 cancellation_token を使用するラムダでは、そのトークンを利用して取り消しを確認する場合があります。また、作成されるタスクにこのトークンを渡す場合もあります。これにより、非同期構造を取り消すと、それらのタスクも取り消されます。  
  
 ラムダまたは関数オブジェクトの本体が結果を返す場合 (task\<TResult >)、タスク、ランタイムのコンテキスト内の MTA が暗黙的に作成してプロセス内で、ラムダを非同期的に実行されます。 `IAsyncInfo::Cancel` のメソッドにより、暗黙のタスクが取り消されます。  
  
 ラムダの本体がタスクを返す場合、ラムダはインラインで実行されます。また、ラムダが型 `cancellation_token` の引数を使用するように宣言すると、タスクの作成時にこのトークンを渡すことによって、ラムダ内で作成されるタスクの取り消しをトリガーできます。 また、トークンに対して `register_callback` メソッドを使用すると、生成される非同期操作や非同期アクションで `IAsyncInfo::Cancel` を呼び出すときに、ランタイムでコールバックを呼び出すこともできます。  
  
 この関数は、Windows ストア アプリでのみ使用できます。  
  
##  <a name="createresourcemanager"></a>CreateResourceManager  
 同時実行ランタイムのリソース マネージャーのシングルトン インスタンスを表すインターフェイスを返します。 リソース マネージャーは、相互の連携を必要とするスケジューラにリソースを割り当てます。  
  
```
IResourceManager* __cdecl CreateResourceManager();
```  
  
### <a name="return-value"></a>戻り値  
 `IResourceManager` インターフェイス。  
  
### <a name="remarks"></a>コメント  
 それ以降、このメソッドを複数回呼び出すと、リソース マネージャーの同じインスタンスが返されます。 メソッドへの各呼び出しの参照は、リソース マネージャーをカウントしへの呼び出しと一致する必要があります、 [iresourcemanager::release](http://msdn.microsoft.com/en-us/5d1356ec-fbd3-4284-a361-1e9e20bbb522)メソッド、スケジューラが終わったときにリソース マネージャーと通信します。  
  
 [unsupported_os](unsupported-os-class.md)が、同時実行ランタイムによって、オペレーティング システムがサポートされていない場合にスローされます。  
  
##  <a name="create_task"></a>create_task  
 作成、PPL[タスク](http://msdn.microsoft.com/en-us/5389e8a5-5038-40b6-844a-55e9b58ad35f)オブジェクトです。 `create_task` は、タスク コンストラクターを使用した任意の場所で使用できます。 タスクの作成中に `auto` キーワードが使用できるようになるため、これは参考用として用意されています。  
  
```
template<typename T>
__declspec(noinline) auto create_task(T _Param, const task_options& _TaskOptions = task_options())
    -> task<typename details::_TaskTypeFromParam<T>::T>;

template<typename _ReturnType>
__declspec( noinline) task<_ReturnType> create_task(const task<_ReturnType>& _Task);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 パラメーターの型。これに基づいてタスクが構築されます。  
  
 `_ReturnType`  
 `_Param`  
 パラメーター。これに基づいてタスクが構築されます。 Windows ストア アプリでタスクを使用する場合、ラムダまたは関数オブジェクト、`task_completion_event` オブジェクト、別の `task` オブジェクト、または Windows::Foundation::IAsyncInfo インターフェイスを指定できます。  
  
 `_TaskOptions`  
 `_Task`  
  
### <a name="return-value"></a>戻り値  
 型 `T` の新しいタスク。`_Param` から推論されます。  
  
### <a name="remarks"></a>コメント  
 最初のオーバーロードは、単一のパラメーターを受け取るタスク コンストラクターのように動作します。  
  
 2 番目のオーバーロードは、新しく作成されたタスクで指定されたキャンセル トークンを関連付けます。 このオーバーロードを使用すると、最初のパラメーターとして別の `task` オブジェクトを渡すことができません。  
  
 返されたタスクの種類は、関数の最初のパラメーターから推測されます。 `_Param` が `task_completion_event<T>`、`task<T>`、または型 `T` か型 `task<T>` を返すファンクタの場合、作成されたタスクの型は `task<T>` です。  
  
 Windows ストア アプリで場合`_Param`型:iasyncoperation\<T > ^ または:iasyncoperationwithprogress\<T, P > ^、それらの型のいずれかを返すファンクタ、作成されたタスク型であるか`task<T>`します。 場合`_Param`のデータ型::iasyncaction ^ か Windows::Foundation::IAsyncActionWithProgress\<P > ^、またはそれらの型のいずれかを返すファンクタ、作成したタスクの型が`task<void>`です。  
  
##  <a name="disabletracing"></a>DisableTracing  
 同時実行ランタイムでのトレースを無効にします。 この関数は、ETW トレースが既定で未登録であるため推奨されません。  
  
```
__declspec(deprecated("Concurrency::DisableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl DisableTracing();
```  
  
### <a name="return-value"></a>戻り値  
 トレースが正しく無効になっている場合は、`S_OK`が返されます。 トレースが開始されていませんが場合、`E_NOT_STARTED`が返されます  
  
##  <a name="enabletracing"></a>EnableTracing  
 同時実行ランタイムでトレースを有効にします。 この関数は、ETW トレースが既定でオンであるため推奨されません。  
  
```
__declspec(deprecated("Concurrency::EnableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl EnableTracing();
```  
  
### <a name="return-value"></a>戻り値  
 トレースが正常に開始された場合`S_OK`を返します。 それ以外の場合、`E_NOT_STARTED`が返されます。  
  
##  <a name="free"></a>無料  
 以前に `Alloc` メソッドによって同時実行ランタイムのキャッシュ サブアロケータに割り当てられたメモリ ブロックを解放します。  
  
```
void __cdecl Free(_Pre_maybenull_ _Post_invalid_ void* _PAllocation);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PAllocation`  
 以前に `Alloc` メソッドによって割り当てられた解放するメモリへのポインター。 `_PAllocation` パラメーターの値が `NULL` に設定されている場合、このメソッドはそれを無視してすぐに制御を戻します。  
  
### <a name="remarks"></a>コメント  
 詳細についてはどのシナリオは、アプリケーションの利点がもたらされるキャッシュ サブアロケータを使用して、次を参照してください。[タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)します。  
  
##  <a name="get_ambient_scheduler"></a>get_ambient_scheduler  
  
```
inline std::shared_ptr<::Concurrency::scheduler_interface> get_ambient_scheduler();
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="getexecutioncontextid"></a>GetExecutionContextId  
 `IExecutionContext` インターフェイスを実装する実行コンテキストに割り当てることのできる一意識別子を返します。  
  
```
unsigned int __cdecl GetExecutionContextId();
```  
  
### <a name="return-value"></a>戻り値  
 実行コンテキストの一意の識別子。  
  
### <a name="remarks"></a>コメント  
 渡す前に、実行コンテキストの識別子を取得するには、このメソッドを使用して、`IExecutionContext`リソース マネージャーによって提供されるメソッドのいずれかのパラメーターとしてインターフェイスです。  
  
##  <a name="getosversion"></a>GetOSVersion  
 オペレーティング システムのバージョンを返します。  
  
```
IResourceManager::OSVersion __cdecl GetOSVersion();
```  
  
### <a name="return-value"></a>戻り値  
 オペレーティング システムを表す列挙値。  
  
### <a name="remarks"></a>コメント  
 [unsupported_os](unsupported-os-class.md)が、同時実行ランタイムによって、オペレーティング システムがサポートされていない場合にスローされます。  
  
##  <a name="getprocessorcount"></a>GetProcessorCount  
 基になるシステム上のハードウェア スレッドの数を返します。  
  
```
unsigned int __cdecl GetProcessorCount();
```  
  
### <a name="return-value"></a>戻り値  
 ハードウェア スレッドの数。  
  
### <a name="remarks"></a>コメント  
 [unsupported_os](unsupported-os-class.md)が、同時実行ランタイムによって、オペレーティング システムがサポートされていない場合にスローされます。  
  
##  <a name="getprocessornodecount"></a>GetProcessorNodeCount  
 基になるシステム上の NUMA ノードまたはプロセッサ パッケージの数を返します。  
  
```
unsigned int __cdecl GetProcessorNodeCount();
```  
  
### <a name="return-value"></a>戻り値  
 NUMA ノードまたはプロセッサ パッケージの数。  
  
### <a name="remarks"></a>コメント  
 システムに含まれる NUMA ノードの数がプロセッサ パッケージの数より多い場合は、NUMA ノードの数が返されます。それ以外の場合は、プロセッサ パッケージの数が返されます。  
  
 [unsupported_os](unsupported-os-class.md)が、同時実行ランタイムによって、オペレーティング システムがサポートされていない場合にスローされます。  
  
##  <a name="getschedulerid"></a>GetSchedulerId  
 `IScheduler` インターフェイスを実装するスケジューラに割り当てることができる一意識別子を返します。  
  
```
unsigned int __cdecl GetSchedulerId();
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラの一意の識別子。  
  
### <a name="remarks"></a>コメント  
 渡す前に、スケジューラの識別子を取得するには、このメソッドを使用して、`IScheduler`リソース マネージャーによって提供されるメソッドのいずれかのパラメーターとしてインターフェイスです。  
  
##  <a name="internal_assign_iterators"></a>internal_assign_iterators  
  
```
template<typename T, class _Ax>
template<class _I> 
void concurrent_vector<T, _Ax>::internal_assign_iterators(
   _I first,
   _I last);
```   
  
### <a name="parameters"></a>パラメーター  
 `T`  
 `_Ax`  
 `_I`  
 `first`  
 `last`  
  
##  <a name="interruption_point"></a>interruption_point  
 取り消しの割り込みポイントを作成します。 この関数が呼び出されるコンテキストで取り消しが進行中の場合、現在実行中の並列処理を中止する内部例外がスローされます。 取り消しが進行中でない場合は、何も実行されません。  
  
```
inline void interruption_point();
```  
  
### <a name="remarks"></a>コメント  
 によってスローされる内部のキャンセル例外キャッチしないで、`interruption_point()`関数です。 例外をキャッチし、ランタイムによって処理され、キャッチ異常動作するプログラムが発生する可能性があります。  
  
##  <a name="is_current_task_group_canceling"></a>is_current_task_group_canceling  
 現在のコンテキストで現在インラインで実行されているタスク グループがアクティブなキャンセル処理中である (または間もなくキャンセル処理が開始される) かどうかを示す値を返します。 現在のコンテキストで現在インラインで実行されているタスク グループが存在しない場合は、`false` が返されます。  
  
```
bool __cdecl is_current_task_group_canceling();
```  
  
### <a name="return-value"></a>戻り値  
 `true`現在実行されているタスク グループを取り消す場合`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[キャンセル](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)します。  
  
##  <a name="make_choice"></a>make_choice  
 オプションの `choice` や `Scheduler`、および&2; つ以上の入力ソースから `ScheduleGroup` メッセージング ブロックを構築します。  
  
```
template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    Scheduler& _PScheduler,
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    ScheduleGroup& _PScheduleGroup,
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);
```  
  
### <a name="parameters"></a>パラメーター  
 `T1`  
 1 番目のソースのメッセージ ブロックの型。  
  
 `T2`  
 2 番目のソースのメッセージ ブロックの型。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `choice` オブジェクト。  
  
 `_Item1`  
 1 番目のソース。  
  
 `_Item2`  
 2 番目のソース。  
  
 `_Items`  
 その他のソース。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `choice` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="return-value"></a>戻り値  
 2 個またはそれ以上の入力ソースを持つ `choice` メッセージ ブロック。  
  
##  <a name="make_greedy_join"></a>make_greedy_join  
 オプションの `greedy multitype_join` や `Scheduler`、および&2; つ以上の入力ソースから `ScheduleGroup` メッセージング ブロックを構築します。  
  
```
template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>,greedy> make_greedy_join(
    Scheduler& _PScheduler,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>, greedy> make_greedy_join(
    ScheduleGroup& _PScheduleGroup,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>, greedy> make_greedy_join(
    T1 _Item1,
    T2 _Items,
    Ts... _Items);
```  
  
### <a name="parameters"></a>パラメーター  
 `T1`  
 1 番目のソースのメッセージ ブロックの型。  
  
 `T2`  
 2 番目のソースのメッセージ ブロックの型。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。  
  
 `_Item1`  
 1 番目のソース。  
  
 `_Item2`  
 2 番目のソース。  
  
 `_Items`  
 その他のソース。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="return-value"></a>戻り値  
 2 個またはそれ以上の入力ソースを持つ `greedy multitype_join` メッセージ ブロック。  
  
##  <a name="make_join"></a>make_join  
 オプションの `non_greedy multitype_join` や `Scheduler`、および&2; つ以上の入力ソースから `ScheduleGroup` メッセージング ブロックを構築します。  
  
```
template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> 
    make_join(
 Scheduler& _PScheduler,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> make_join(
 ScheduleGroup& _PScheduleGroup,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> make_join(
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);
```  
  
### <a name="parameters"></a>パラメーター  
 `T1`  
 1 番目のソースのメッセージ ブロックの型。  
  
 `T2`  
 2 番目のソースのメッセージ ブロックの型。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。  
  
 `_Item1`  
 1 番目のソース。  
  
 `_Item2`  
 2 番目のソース。  
  
 `_Items`  
 その他のソース。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="return-value"></a>戻り値  
 2 個またはそれ以上の入力ソースを持つ `non_greedy multitype_join` メッセージ ブロック。  
  
##  <a name="make_task"></a>make_task  
 `task_handle` オブジェクトを作成するためのファクトリ メソッドです。  
  
```
template <class _Function>
task_handle<_Function> make_task(const _Function& _Func);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 によって表される処理を実行するときに呼び出される関数オブジェクトの型、`task_handle`オブジェクトです。  
  
 `_Func`  
 によって表される処理を実行するときに呼び出される関数、`task_handle`オブジェクトです。 ラムダ ファンクタ、関数へのポインターまたはシグネチャを持つ関数呼び出し演算子のバージョンをサポートするオブジェクト`void operator()()`します。  
  
### <a name="return-value"></a>戻り値  
 `task_handle` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 この関数は作成する必要がある場合、`task_handle`ラムダ式でオブジェクトをラムダ ファンクタの実際の型を知らなくてもオブジェクトを作成することができます。  
  
##  <a name="parallel_buffered_sort"></a>parallel_buffered_sort  
 指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って、並列に配置します。 この関数は、比較ベースで不安定なインプレース並べ替えという点で `std::sort` と意味が同じです。ただし、`O(n)` 追加スペースが必要で、並べ替えている要素を既定で初期化する必要があります。  
  
```
template<typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator,
    typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator,
    typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Random_iterator`  
 入力範囲の反復子の型。  
  
 `_Allocator`  
 C++ 標準ライブラリの互換性のあるメモリ アロケーターの型。  
  
 `_Function`  
 バイナリの比較子の型。  
  
 `_Begin`  
 並べ替えられる範囲内の最初の要素の位置を示すランダム アクセス反復子。  
  
 `_End`  
 並べ替えられる範囲内の最後の要素の&1; つ後ろの位置を示すランダム アクセス反復子。  
  
 `_Alloc`  
 C++ 標準ライブラリの互換性のあるメモリ アロケーターのインスタンス。  
  
 `_Func`  
 順序の一連の要素によって満たされる比較条件を定義するユーザー定義の述語関数オブジェクト。 二項述語は&2; つの引数を受け取り、条件が満たされている場合は `true`、満たされていない場合は `false` を返します。 この比較子関数は、シーケンスからの要素のペアで厳密弱順序を強制する必要があります。  
  
 `_Chunk_size`  
 並列実行用に&2; つに分割されますチャンクの最小サイズ。  
  
### <a name="remarks"></a>コメント  
 すべてのオーバー ロードを必要と`n * sizeof(T)`追加スペースが、`n`で並べ替えられます要素の数と`T`要素の型は、です。 ほとんどの場合 parallel_buffered_sort は表示するパフォーマンスが向上経由で[parallel_sort](concurrency-namespace-functions.md)、使用可能なメモリがある場合は parallel_sort 経由で使用する必要があります。  
  
 二項比較演算子を指定しない場合`std::less`、演算子を提供する要素の型を必要とすると、既定として使用される`operator<()`します。  
  
 アロケーターの型またはインスタンス、C++ 標準ライブラリのメモリ アロケーターを指定しない場合`std::allocator<T>`バッファーを割り当てるために使用します。  
  
 このアルゴリズムでは、入力の範囲を&2; つのチャンクに分割し、続けて各チャンクを並列で実行するための&2; つのサブ チャンクに分割します。 省略可能な引数`_Chunk_size`サイズのチャンクを処理する必要があります、アルゴリズムに示すために使用できます<>`_Chunk_size`逐次的にします。  
  
##  <a name="parallel_for"></a>parallel_for  
 `parallel_for` は、一定の範囲のインデックスを反復処理し、各反復処理で、ユーザーが指定した関数を並列で実行します。  
  
```
template <typename _Index_type, typename _Function, typename _Partitioner>
void parallel_for(
    _Index_type first,
    _Index_type last,
    _Index_type _Step,
    const _Function& _Func,
    _Partitioner&& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    _Index_type _Step,
    const _Function& _Func);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const auto_partitioner& _Part = auto_partitioner());

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const static_partitioner& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const simple_partitioner& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    affinity_partitioner& _Part);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index_type`  
 イテレーションの使用されているインデックスの型。  
  
 `_Function`  
 各反復処理で実行される関数の型。  
  
 `_Partitioner`  
 指定された範囲を分割するために使用しているパーティショナーの型。  
  
 `first`  
 イテレーションに含まれる最初のインデックス。  
  
 `last`  
 過去のイテレーションに含まれる最後のインデックスのいずれかのインデックス。  
  
 `_Step`  
 反復処理するときにステップする値`first`に`last`します。 ステップは、正の値である必要があります。 [invalid_argument](../../../standard-library/invalid-argument-class.md)ステップが 1 未満の場合にスローされます。  
  
 `_Func`  
 各反復処理で実行される関数。 ラムダ式、関数ポインター、またはシグネチャを持つ関数呼び出し演算子のバージョンをサポートするオブジェクト`void operator()(``_Index_type``)`します。  
  
 `_Part`  
 パーティショナーのオブジェクトへの参照。 引数には、いずれかを指定できます`const` [auto_partitioner](auto-partitioner-class.md)`&`、 `const` [static_partitioner](static-partitioner-class.md)`&`、 `const` [simple_partitioner](simple-partitioner-class.md) `&`または[affinity_partitioner](affinity-partitioner-class.md) `&`場合、 [affinity_partitioner](affinity-partitioner-class.md)オブジェクトを使用して、参照は、アルゴリズムは、将来的にループを再利用の状態を保存するため、const でない左辺値参照にする必要があります。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[並列アルゴリズム](../../../parallel/concrt/parallel-algorithms.md)します。  
  
##  <a name="parallel_for_each"></a>parallel_for_each  
 `parallel_for_each` は、指定された関数を範囲内の各要素に並列で適用します。 意味的には `for_each` 名前空間の `std` 関数と同等ですが、要素に対する反復処理が並列で行われる点、および反復処理の順序が指定されていない点が異なります。 引数 `_Func` は、`operator()(T)` の形式の関数呼び出し演算子をサポートしている必要があります (`T` パラメーターは反復処理するコンテナーの項目の種類を示します)。  
  
```
template <typename _Iterator, typename _Function>
void parallel_for_each(
    _Iterator first,
    _Iterator last,
    const _Function& _Func);

template <typename _Iterator, typename _Function, typename _Partitioner>
void parallel_for_each(
    _Iterator first,
    _Iterator last,
    const _Function& _Func,
    _Partitioner&& _Part);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Iterator`  
 コンテナーを反復処理に使用されている反復子の型。  
  
 `_Function`  
 範囲内の各要素に適用される関数の型。  
  
 `_Partitioner`  
 `first`  
 並列反復処理に含まれる最初の要素の位置を示す反復子。  
  
 `last`  
 並列反復処理に含まれる最後の要素の後ろのいずれかの位置を示す反復子。  
  
 `_Func`  
 範囲内の各要素に適用されるユーザー定義関数オブジェクト。  
  
 `_Part`  
 パーティショナーのオブジェクトへの参照。 引数には、いずれかを指定できます`const` [auto_partitioner](auto-partitioner-class.md)`&`、 `const` [static_partitioner](static-partitioner-class.md)`&`、 `const` [simple_partitioner](simple-partitioner-class.md) `&`または[affinity_partitioner](affinity-partitioner-class.md) `&`場合、 [affinity_partitioner](affinity-partitioner-class.md)オブジェクトを使用して、参照は、アルゴリズムは、将来的にループを再利用の状態を保存するため、const でない左辺値参照にする必要があります。  
  
### <a name="remarks"></a>コメント  
 [auto_partitioner](auto-partitioner-class.md)明示的なパーティショナーなしのオーバー ロードが適用されます。  
  
 サポートしていないランダムな反復子にアクセスするだけの[auto_partitioner](auto-partitioner-class.md)はサポートされています。  
  
 詳細については、次を参照してください。[並列アルゴリズム](../../../parallel/concrt/parallel-algorithms.md)します。  
  
##  <a name="parallel_invoke"></a>parallel_invoke  
 パラメーターとして渡された関数オブジェクトを並列実行し、実行が完了するまでブロックします。 各関数オブジェクトは、ラムダ式、関数へのポインター、またはシグネチャ `void operator()()` を持つ関数呼び出し演算子をサポートするオブジェクトになります。  
  
```
template <typename _Function1, typename _Function2>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2);

template <typename _Function1, typename _Function2, typename _Function3>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8,
    typename _Function9>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8,
    const _Function9& _Func9);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8,
    typename _Function9,
    typename _Function10>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8,
    const _Function9& _Func9,
    const _Function10& _Func10);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function1`  
 並列実行される最初の関数オブジェクトの型。  
  
 `_Function2`  
 並列実行される&2; 番目の関数オブジェクトの型。  
  
 `_Function3`  
 並列実行できる&3; つ目の関数オブジェクトの型。  
  
 `_Function4`  
 並列実行できる&4; 番目の関数オブジェクトの型。  
  
 `_Function5`  
 並列で実行する&5; 番目の関数オブジェクトの型。  
  
 `_Function6`  
 並列実行できる&6; つ目の関数オブジェクトの型。  
  
 `_Function7`  
 並列実行される&7; 番目の関数オブジェクトの型。  
  
 `_Function8`  
 並列実行される&8; 番目の関数オブジェクトの型。  
  
 `_Function9`  
 並列実行できる&9; 番目の関数オブジェクトの型。  
  
 `_Function10`  
 並列実行されるには、10 番目の関数オブジェクトの型。  
  
 `_Func1`  
 並列実行される最初の関数オブジェクト。  
  
 `_Func2`  
 並列実行される&2; つ目の関数オブジェクト。  
  
 `_Func3`  
 並列実行できる&3; つ目の関数オブジェクト。  
  
 `_Func4`  
 並列実行できる&4; 番目の関数オブジェクト。  
  
 `_Func5`  
 並列で実行する&5; 番目の関数オブジェクト。  
  
 `_Func6`  
 並列実行できる&6; つ目の関数オブジェクト。  
  
 `_Func7`  
 並列実行される&7; 番目の関数オブジェクト。  
  
 `_Func8`  
 並列実行される&8; 番目の関数オブジェクト。  
  
 `_Func9`  
 並列実行できる&9; 番目の関数オブジェクト。  
  
 `_Func10`  
 並列実行される&10; 番目の関数オブジェクト。  
  
### <a name="remarks"></a>コメント  
 パラメーターが呼び出し元のコンテキストでインラインを実行できるようの&1; つ以上の関数オブジェクトを指定することに注意してください。  
  
 この関数にパラメーターとして渡された関数オブジェクトの&1; つ以上は、例外をスローする場合、ランタイムは、選択した場合のような例外が&1; つを選択しへの呼び出しから伝達`parallel_invoke`します。  
  
 詳細については、次を参照してください。[並列アルゴリズム](../../../parallel/concrt/parallel-algorithms.md)します。  
  
##  <a name="parallel_radixsort"></a>parallel_radixsort  
 基数並べ替えアルゴリズムを使用して、指定された範囲の要素を降順以外の順序で配置します。 これは安定した並べ替え関数で、符号なし整数 (キーなど) に分類されるように要素を投影する投射関数を必要とします。 並べ替えられる要素には既定の初期化が必要です。  
  
```
template<typename _Random_iterator>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator, typename _Random_iterator>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator, typename _Random_iterator>
inline void parallel_radixsort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator, typename _Function>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);

template<typename _Allocator, typename _Random_iterator,
    typename _Function>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_radixsort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Random_iterator`  
 入力範囲の反復子の型。  
  
 `_Allocator`  
 C++ 標準ライブラリの互換性のあるメモリ アロケーターの型。  
  
 `_Function`  
 射影関数の型。  
  
 `_Begin`  
 並べ替えられる範囲内の最初の要素の位置を示すランダム アクセス反復子。  
  
 `_End`  
 並べ替えられる範囲内の最後の要素の&1; つ後ろの位置を示すランダム アクセス反復子。  
  
 `_Alloc`  
 C++ 標準ライブラリの互換性のあるメモリ アロケーターのインスタンス。  
  
 `_Proj_func`  
 要素を整数値に変換するユーザー定義射影関数オブジェクト。  
  
 `_Chunk_size`  
 並列実行用に&2; つに分割されますチャンクの最小サイズ。  
  
### <a name="remarks"></a>コメント  
 すべてのオーバー ロードを必要と`n * sizeof(T)`追加スペースが、`n`で並べ替えられます要素の数と`T`要素の型は、です。 シグネチャを持つ単項プロジェクション ファンクタ`I _Proj_func(T)`、要素が指定されるとキーを返すために必要な`T`要素の型と`I`符号なし整数のような型は、です。  
  
 射影関数を指定しない場合、単に要素が返されます既定射影関数は、整数型で使用されます。 関数は、要素が射影関数がない場合は整数型ではない場合はコンパイルに失敗します。  
  
 アロケーターの型またはインスタンス、C++ 標準ライブラリのメモリ アロケーターを指定しない場合`std::allocator<T>`バッファーを割り当てるために使用します。  
  
 このアルゴリズムでは、入力の範囲を&2; つのチャンクに分割し、続けて各チャンクを並列で実行するための&2; つのサブ チャンクに分割します。 省略可能な引数`_Chunk_size`サイズのチャンクを処理する必要があります、アルゴリズムに示すために使用できます<>`_Chunk_size`逐次的にします。  
  
##  <a name="parallel_reduce"></a>parallel_reduce  
 連続する部分的な合計を計算することで、指定された範囲のすべての要素の合計を計算します。または、指定された二項演算を使用して取得した、合計以外の連続する部分的な結果を並列で計算します。 `parallel_reduce` は `std::accumulate` と意味が同じです。ただし、結合のための二項演算と、初期値ではなく ID 値が必要です。  
  
```
template<typename _Forward_iterator>
inline typename std::iterator_traits<_Forward_iterator>::value_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const typename std::iterator_traits<_Forward_iterator>::value_type& _Identity);

template<typename _Forward_iterator, typename _Sym_reduce_fun>
inline typename std::iterator_traits<_Forward_iterator>::value_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const typename std::iterator_traits<_Forward_iterator>::value_type& _Identity,
    _Sym_reduce_fun _Sym_fun);

template<typename _Reduce_type,
    typename _Forward_iterator,
    typename _Range_reduce_fun,
    typename _Sym_reduce_fun>
inline _Reduce_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const _Reduce_type& _Identity,
    const _Range_reduce_fun& _Range_fun,
    const _Sym_reduce_fun& _Sym_fun);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Forward_iterator`  
 入力範囲の反復子の型。  
  
 `_Sym_reduce_fun`  
 対称削減関数の型。 これは、関数の型のシグネチャを持つ必要があります`_Reduce_type _Sym_fun(_Reduce_type, _Reduce_type)`_Reduce_type が同じ id の種類と削減の結果の型として、します。 3 番目のオーバー ロードの出力の種類と一貫してあります`_Range_reduce_fun`します。  
  
 `_Reduce_type`  
 入力を軽減するのには、入力要素の型から異なる可能性がある型。 戻り値と id 値は、この型がされます。  
  
 `_Range_reduce_fun`  
 範囲の削減関数の型。 これは、関数の型のシグネチャを持つ必要があります`_Reduce_type _Range_fun(_Forward_iterator, _Forward_iterator, _Reduce_type)`id の種類と削減の結果の型と同じ _Reduce_type であります。  
  
 `_Begin`  
 入力反復子の範囲の最初の要素をアドレス指定が低下します。  
  
 `_End`  
 縮小される範囲内で最後の要素の次の&1; つの位置にある要素を示す入力反復子。  
  
 `_Identity`  
 Id 値`_Identity`減少の結果の型と同じ型のさらに、`value_type`番目と&2; 番目のオーバー ロードの反復子のです。 3 番目のオーバー ロードでは、id 値は、減少の結果の型と同じ型である必要がありますが、異なっていてもかまいません、`value_type`の反復子。 適切な値を持つ必要がありますように範囲リダクション演算子`_Range_fun`型の&1; つの要素の範囲に適用すると、 `value_type` id 値の型からの値の型キャストのような動作と`value_type`id 型にします。  
  
 `_Sym_fun`  
 減少した&1; 秒間に使用される対称関数。 詳細については、「解説」を参照してください。  
  
 `_Range_fun`  
 削減の最初のフェーズで使用される関数。 詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 減少の結果です。  
  
### <a name="remarks"></a>コメント  
 並列リダクションを実行するのには、関数は、基になるスケジューラに使用できるワーカーの数に基づいてチャンクに、範囲を分割します。 減少し、2 つのフェーズで行わ、最初のフェーズは、各チャンクでの削減を実行し、2 番目のフェーズは、各チャンクから部分的な結果の間でのリダクションを実行します。  
  
 最初のオーバー ロードが必要とする反復子の`value_type`、 `T`id 値の種類と削減の結果の型と同じにする。 要素型 T は、演算子を提供する必要があります`T T::operator + (T)`各チャンク内の要素を削減します。 同じ演算子は、2 番目のフェーズで使用されます。  
  
 2 番目のオーバー ロードも必要とする反復子の`value_type`と同じ id 値の種類と削減の結果型にします。 指定された二項演算子`_Sym_fun`された最初のフェーズの初期値として id 値の両方の縮小フェーズで使用します。  
  
 3 番目のオーバー ロードでは、id 値の種類同じでなければなりません削減の結果型が反復子の`value_type`両方に異なる可能性があります。 範囲の削減関数`_Range_fun`として初期値、および二項関数の id 値を持つ最初のフェーズで使用される`_Sym_reduce_fun`が&2; 番目のフェーズで結果をサブフォルダーに適用します。  
  
##  <a name="parallel_sort"></a>parallel_sort  
 指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って、並列に配置します。 この関数は、比較ベースで不安定なインプレース並べ替えという点で `std::sort` と意味が同じです。  
  
```
template<typename _Random_iterator>
inline void parallel_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator,typename _Function>
inline void parallel_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Random_iterator`  
 入力範囲の反復子の型。  
  
 `_Function`  
 二項比較ファンクタの型。  
  
 `_Begin`  
 並べ替えられる範囲内の最初の要素の位置を示すランダム アクセス反復子。  
  
 `_End`  
 並べ替えられる範囲内の最後の要素の&1; つ後ろの位置を示すランダム アクセス反復子。  
  
 `_Func`  
 順序の一連の要素によって満たされる比較条件を定義するユーザー定義の述語関数オブジェクト。 二項述語は&2; つの引数を受け取り、条件が満たされている場合は `true`、満たされていない場合は `false` を返します。 この比較子関数は、シーケンスからの要素のペアで厳密弱順序を強制する必要があります。  
  
 `_Chunk_size`  
 並列実行用に&2; つに分割されますチャンクの最小サイズ。  
  
### <a name="remarks"></a>コメント  
 最初のオーバー ロードを使用して、バイナリの比較子`std::less`します。  
  
 2 つ目は、使用をオーバー ロードされた署名する必要のある指定された二項比較演算子`bool _Func(T, T)`、`T`入力範囲の要素の型は、です。  
  
 このアルゴリズムでは、入力の範囲を&2; つのチャンクに分割し、続けて各チャンクを並列で実行するための&2; つのサブ チャンクに分割します。 省略可能な引数`_Chunk_size`サイズのチャンクを処理する必要があります、アルゴリズムに示すために使用できます<>`_Chunk_size`逐次的にします。  
  
##  <a name="parallel_transform"></a>parallel_transform  
 指定された関数オブジェクトをソース範囲内の各要素、または&2; つのソース範囲内の要素のペアに適用し、関数オブジェクトの戻り値をコピー先の範囲に並列でコピーします。 この関数は、意味的には `std::transform` と同じです。  
  
```
template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const auto_partitioner& _Part = auto_partitioner());

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const static_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const simple_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    affinity_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Input_iterator2,
    typename _Output_iterator,
    typename _Binary_operator,
    typename _Partitioner>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Input_iterator2
 first2,
    _Output_iterator _Result,
    const _Binary_operator& _Binary_op,
    _Partitioner&& _Part);

template <typename _Input_iterator1,
    typename _Input_iterator2,
    typename _Output_iterator,
    typename _Binary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Input_iterator2
 first2,
    _Output_iterator _Result,
    const _Binary_operator& _Binary_op);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Input_iterator1`  
 最初のページとだけ入力反復子の型。  
  
 `_Output_iterator`  
 出力反復子の型。  
  
 `_Unary_operator`  
 入力範囲内の各要素に実行される、単項ファンクタの型。  
  
 `_Input_iterator2`  
 2 番目の入力反復子の型。  
  
 `_Binary_operator`  
 2 つのソース範囲の要素に対して実行ペアワイズ バイナリ ファンクタの型。  
  
 `_Partitioner`  
 `first1`  
 最初のページまたは処理されるソース範囲のみでの最初の要素の位置を示す入力反復子。  
  
 `last1`  
 1 つの後ろの位置、最後の要素の最初のページまたは処理されるソース範囲のみを示す入力反復子。  
  
 `_Result`  
 ターゲット範囲の最初の要素の位置を示す出力反復子。  
  
 `_Unary_op`  
 ソース範囲内の各要素に適用されるユーザー定義の単項関数オブジェクト。  
  
 `_Part`  
 パーティショナーのオブジェクトへの参照。 引数には、いずれかを指定できます`const` [auto_partitioner](auto-partitioner-class.md)`&`、 `const` [static_partitioner](static-partitioner-class.md)`&`、 `const` [simple_partitioner](simple-partitioner-class.md) `&`または[affinity_partitioner](affinity-partitioner-class.md) `&`場合、 [affinity_partitioner](affinity-partitioner-class.md)オブジェクトを使用して、参照は、アルゴリズムは、将来的にループを再利用の状態を保存するため、const でない左辺値参照にする必要があります。  
  
 `first2`  
 操作する&2; 番目のソース範囲内の最初の要素の位置を示す入力反復子。  
  
 `_Binary_op`  
 ペアワイズ、2 つのソース範囲への前方の順序で適用されているユーザー定義の二項関数オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 関数オブジェクトで変換された出力要素を受け取るターゲット範囲の最後の要素の&1; つ後ろの位置を示す出力反復子。  
  
### <a name="remarks"></a>コメント  
 [auto_partitioner](auto-partitioner-class.md)明示的なパーティショナー引数なしのオーバー ロードが適用されます。  
  
 サポートしていないランダムな反復子にアクセスするだけの[auto_partitioner](auto-partitioner-class.md)はサポートされています。  
  
 引数を受け取るオーバー ロード`_Unary_op`単項ファンクタを入力の範囲内の各要素に適用することによって、入力の範囲を出力の範囲に変換します。 `_Unary_op`シグネチャを持つ関数呼び出し演算子をサポートする必要があります`operator()(T)`、`T`は反復範囲の値の型。  
  
 引数を受け取るオーバー ロード`_Binary_op`最初の入力の範囲と&2; 番目の入力の範囲から&1; つの要素から&1; つの要素のバイナリ ファンクタを適用することによって、2 つの入力範囲を出力の範囲に変換します。 `_Binary_op`シグネチャを持つ関数呼び出し演算子をサポートする必要があります`operator()(T, U)`、 `T`、`U`は&2; つの入力反復子の値の型。  
  
 詳細については、次を参照してください。[並列アルゴリズム](../../../parallel/concrt/parallel-algorithms.md)します。  
  
##  <a name="receive"></a>表示されます。  
 receive の一般的な実装です。これにより、コンテキストで&1; つのソースからのデータを待機し、受け取った値をフィルター処理できます。  
  
```
template <class T>
T receive(
    _Inout_ ISource<T>* _Src,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    _Inout_ ISource<T>* _Src,
    typename ITarget<T>::filter_method const& _Filter_proc,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    ISource<T>& _Src,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    ISource<T>& _Src,
    typename ITarget<T>::filter_method const& _Filter_proc,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 ペイロードの型。  
  
 `_Src`  
 ポインターまたはデータが予想される元のソースへの参照。  
  
 `_Timeout`  
 ミリ秒単位でデータには、このメソッドが必要があります最大時間。  
  
 `_Filter_proc`  
 メッセージを受け入れられる必要があるかどうかを決定するフィルター関数。  
  
### <a name="return-value"></a>戻り値  
 ペイロードの種類のソースからの値です。  
  
### <a name="remarks"></a>コメント  
 場合、パラメーター`_Timeout`定数以外の値を持つ`COOPERATIVE_TIMEOUT_INFINITE`、例外[operation_timed_out](operation-timed-out-class.md)が、一定の時間には、メッセージを受信する前に有効期限が切れる場合にスローされます。 使用する必要があります長さ&0; のタイムアウトを設定する場合、 [try_receive](concurrency-namespace-functions.md)関数を呼び出すのではなく`receive`のタイムアウトで`0`(ゼロ)、方が効率的であり、タイムアウト例外をスローしません。  
  
 詳細については、次を参照してください。[メッセージを渡す関数](../../../parallel/concrt/message-passing-functions.md)します。  
  
##  <a name="run_with_cancellation_token"></a>run_with_cancellation_token  
 関数オブジェクトを、指定されたキャンセル トークンのコンテキストですばやく同期的に実行します。  
  
```
template<typename _Function>
void run_with_cancellation_token(
    const _Function& _Func,
    cancellation_token _Ct);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 呼び出される関数オブジェクトの型。  
  
 `_Func`  
 実行される関数オブジェクト。 このオブジェクトは、void(void) のシグネチャを持つ関数呼び出し演算子をサポートする必要があります。  
  
 `_Ct`  
 関数オブジェクトの暗黙的な取り消しを制御するキャンセル トークン。 使用`cancellation_token::none()`関数は親タスク グループが取り消されることからの暗黙的なキャンセルの存在する可能性を実行する場合。  
  
### <a name="remarks"></a>コメント  
 関数オブジェクトでは、任意の割り込みポイントがあるときにトリガーされる、`cancellation_token`は取り消されます。 明示的なトークン`_Ct`切り分けることがこの`_Func`別のトークンまたはトークンを設定せずに親がある場合、親キャンセルからします。  
  
##  <a name="send"></a>送信  
 ターゲットがメッセージを受け入れるか拒否するまで待機する同期送信操作です。  
  
```
template <class T>
bool send(_Inout_ ITarget<T>* _Trg, const T& _Data);

template <class T>
bool send(ITarget<T>& _Trg, const T& _Data);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 ペイロードの型。  
  
 `_Trg`  
 ポインターまたはデータの送付先となるターゲットへの参照。  
  
 `_Data`  
 送信されるデータへの参照。  
  
### <a name="return-value"></a>戻り値  
 `true`メッセージが受け入れられた場合`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[メッセージを渡す関数](../../../parallel/concrt/message-passing-functions.md)します。  
  
##  <a name="set_ambient_scheduler"></a>set_ambient_scheduler  
  
```
inline void set_ambient_scheduler(std::shared_ptr<::Concurrency::scheduler_interface> _Scheduler);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Scheduler`  
  
##  <a name="set_task_execution_resources"></a>set_task_execution_resources  
 同時実行ランタイムの内部ワーカー スレッドが使用する実行リソースを、指定された関係セットに制限します。  
  
 このメソッドの呼び出しは、リソース マネージャーの作成前、または&2; つのリソース マネージャーの有効期間の間のみ有効です。 これは、呼び出し時にリソース マネージャーが存在しない限り複数回呼び出すことができます。 関係の制限が設定されたら、次の有効な `set_task_execution_resources` メソッド呼び出しまで保持されます。  
  
 指定された関係マスクは、プロセス関係マスクのサブセットである必要はありません。 プロセス関係は必要に応じて更新されます。  
  
```
void __cdecl set_task_execution_resources(
    DWORD_PTR _ProcessAffinityMask);

void __cdecl set_task_execution_resources(
    unsigned short count,
    PGROUP_AFFINITY _PGroupAffinity);
```  
  
### <a name="parameters"></a>パラメーター  
 `_ProcessAffinityMask`  
 同時実行ランタイムのワーカー スレッドができないようにするには、affinity mask です。 現在のプロセッサ グループのサブセットに同時実行ランタイムを制限する場合にのみ、64 個のハードウェア スレッドより多くのシステムでこのメソッドを使用します。 一般に、64 個のハードウェア スレッドより多くのマシンでの関係を制限する、パラメーターとしてのアフィニティ グループの配列を受け取るメソッドのバージョンを使用する必要があります。  
  
 `count`  
 数`GROUP_AFFINITY`パラメーターで指定された配列内のエントリ`_PGroupAffinity`します。  
  
 `_PGroupAffinity`  
 配列`GROUP_AFFINITY`エントリです。  
  
### <a name="remarks"></a>コメント  
 メソッドがスローされます、 [invalid_operation](invalid-operation-class.md)リソース マネージャーでは、メソッドが呼び出された時に存在する場合に例外と[invalid_argument](../../../standard-library/invalid-argument-class.md)アフィニティは、リソースの空のセットで結果を指定した場合に例外です。  
  
 グループ アフィニティの配列をパラメーターとして受け取るメソッドのバージョンは、Windows 7 のバージョンのオペレーティング システムで使用される以降でのみ必要があります。 それ以外の場合、 [invalid_operation](invalid-operation-class.md)例外がスローされます。  
  
 このメソッドが呼び出された後に、プロセスの関係をプログラムで変更する場合は、リソース マネージャーに制限は、類似性を再評価するのには発生しません。 そのため、アフィニティを処理するすべての変更は、このメソッドを呼び出す前に行う必要があります。  
  
##  <a name="swap"></a>  swap  
 2 つの `concurrent_vector` オブジェクトの要素を交換します。  
  
```
template<typename T, class _Ax>
inline void swap(
    concurrent_vector<T, _Ax>& _A,
    concurrent_vector<T, _Ax>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納された要素のデータ型。  
  
 `_Ax`  
 同時実行ベクターのアロケーターの型。  
  
 `_A`  
 要素は、同時実行ベクターのものと交換するが、同時実行ベクター`_B`します。  
  
 `_B`  
 同時実行ベクターを交換する要素を提供するか、要素と交換される、同時実行ベクターのベクトル`_A`します。  
  
### <a name="remarks"></a>コメント  
 コンテナー クラスの特殊なアルゴリズム テンプレート関数は、`concurrent_vector`メンバー関数を実行する`_A`です。 [concurrent_vector::swap](concurrent-vector-class.md#swap)( `_B`)。 これらは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン`template <class T> void swap(T&, T&)`アルゴリズムでクラスでは、割り当て、低速な処理です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
 このメソッドは同時実行セーフではありません。 他のスレッドが実行しているないに対して同時実行ベクターのいずれかの操作をこのメソッドを呼び出すとを確認する必要があります。  
  
##  <a name="task_from_exception"></a>task_from_exception  
  
```
template<typename _TaskType, typename _ExType>
task<_TaskType> task_from_exception(
    _ExType _Exception,
    const task_options& _TaskOptions = task_options());
```  
  
### <a name="parameters"></a>パラメーター  
 `_TaskType`  
 `_ExType`  
 `_Exception`  
 `_TaskOptions`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="task_from_result"></a>task_from_result  
  
```
template<typename T>
task<T> task_from_result(
    T _Param,
    const task_options& _TaskOptions = task_options());

inline task<bool> task_from_result(ool _Param);

inline task<void> task_from_result(
    const task_options& _TaskOptions = task_options());
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 `_Param`  
 `_TaskOptions`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="trace_agents_register_name"></a>Trace_agents_register_name  
 指定された名前を、ETW トレースのメッセージ ブロックまたはエージェントに関連付けます。  
  
```
template <class T>
void Trace_agents_register_name(
    _Inout_ T* _PObject,
    _In_z_ const wchar_t* _Name);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 オブジェクトの型。 これは通常、メッセージ ブロックまたはエージェントです。  
  
 `_PObject`  
 メッセージ ブロックまたはトレースに名前が、エージェントへのポインター。  
  
 `_Name`  
 特定のオブジェクトの名前。  
  
##  <a name="try_receive"></a>try_receive  
 try-receive の一般的な実装です。これにより、コンテキストで&1; つのソースに対してのみデータの検索を実行し、受け取った値をフィルター処理できます。 データが準備されていない場合、メソッドは false を返します。  
  
``` 
template <class T>
bool try_receive(_Inout_ ISource<T>* _Src, T& _value);

template <class T>
bool try_receive(
    _Inout_ ISource<T>* _Src,
    T& _value,
    typename ITarget<T>::filter_method const& _Filter_proc);

template <class T>
bool try_receive(ISource<T>& _Src, T& _value);

template <class T>
bool try_receive(
    ISource<T>& _Src,
    T& _value,
    typename ITarget<T>::filter_method const& _Filter_proc);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 ペイロードの種類  
  
 `_Src`  
 ポインターまたはデータが予想される元のソースへの参照。  
  
 `_value`  
 結果を配置する場所への参照。  
  
 `_Filter_proc`  
 メッセージを受け入れられる必要があるかどうかを決定するフィルター関数。  
  
### <a name="return-value"></a>戻り値  
 A`bool`にペイロードが格納されたかどうかを示すを値`_value`です。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[メッセージを渡す関数](../../../parallel/concrt/message-passing-functions.md)します。  
  
##  <a name="wait"></a>待機  
 指定した時間だけ現在のコンテキストを停止します。  
  
```
void __cdecl wait(unsigned int _Milliseconds);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Milliseconds`  
 現在のコンテキストを停止するミリ秒数。 場合、`_Milliseconds`パラメーターが値に設定されている`0`、現在のコンテキストで実行を続行する前に実行可能なその他のコンテキストを得られます。  
  
### <a name="remarks"></a>コメント  
 このメソッドは同時実行ランタイム スケジューラのコンテキストで呼び出されると、スケジューラは基になるリソース上で実行する別のコンテキストを検索します。 スケジューラは本質的に協調的であるために、このコンテキストは、指定されたミリ秒数後に正確に再開できません。 スケジューラが、スケジューラに協調的に譲渡はないその他のタスクの実行でビジー状態の場合は、待機時間が確実なできません。  
  
##  <a name="when_all"></a>when_all  
 引数として指定されたすべてのタスクが正常に完了したときに正常に完了するタスクを作成します。  
  
```
template <typename _Iterator>
auto when_all(
    _Iterator _Begin,
    _Iterator _End,
    const task_options& _TaskOptions = task_options()) -> 
    decltype (details::_WhenAllImpl<typename std::iterator_traits<_Iterator>::value_type::result_type,
    _Iterator>::_Perform(_TaskOptions, _Begin,  _End));
```   
  
### <a name="parameters"></a>パラメーター  
 `_Iterator`  
 入力反復子の型。  
  
 `_Begin`  
 結果のタスクに組み込まれる要素範囲内にある最初の要素の位置。  
  
 `_End`  
 結果のタスクに組み込まれる要素範囲外にある最初の要素の位置。  
  
 `_TaskOptions`  
  
### <a name="return-value"></a>戻り値  
 入力したすべてのタスクが正常に完了したときに正常に完了するタスク。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::vector<T>>` になります。 入力したタスクの種類が `void` である場合、出力のタスクも `task<void>` になります。  
  
### <a name="remarks"></a>コメント  
 `when_all` は、その結果、`task` を生成する、非ブロッキング関数です。 異なり[task::wait](task-class.md#wait)でこの関数の呼び出しは安全では、 [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] ASTA (アプリケーション STA) スレッド上のアプリケーションです。  
  
 タスクのいずれかが取り消されたり、例外をスロー、返されるタスクは早期に完了、取り消し状態にして、例外場合は&1; つは、またはするスローされた場合を呼び出す場合[task::get](task-class.md#get)または`task::wait`タスクにします。  
  
 詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。  
  
##  <a name="when_any"></a>when_any  
 引数として指定されたいずれかのタスクが正常に完了したときに正常に完了するタスクを作成します。  
  
```
template<typename _Iterator>
auto when_any(
    _Iterator _Begin,
    _Iterator _End,
    const task_options& _TaskOptions = task_options()) 
    -> decltype (
        details::_WhenAnyImpl<
            typename std::iterator_traits<_Iterator>::value_type::result_type,
            _Iterator>::_Perform(_TaskOptions, _Begin, _End));

template<typename _Iterator>
auto when_any(
    _Iterator _Begin,
    _Iterator _End,
    cancellation_token _CancellationToken) 
       -> decltype (
           details::_WhenAnyImpl<
               typename std::iterator_traits<_Iterator>::value_type::result_type,
               _Iterator>::_Perform(_CancellationToken._GetImplValue(), _Begin, _End));
```   
  
### <a name="parameters"></a>パラメーター  
 `_Iterator`  
 入力反復子の型。  
  
 `_Begin`  
 結果のタスクに組み込まれる要素範囲内にある最初の要素の位置。  
  
 `_End`  
 結果のタスクに組み込まれる要素範囲外にある最初の要素の位置。  
  
 `_TaskOptions`  
 `_CancellationToken`  
 返されたタスクの取り消しを制御するキャンセル トークン。 キャンセル トークンを指定しない場合、結果のタスクは、完了の原因となったタスクのキャンセル トークンを受け取ります。  
  
### <a name="return-value"></a>戻り値  
 入力したタスクのいずれかが正常に完了したときに正常に完了するタスク。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::pair<T, size_t>>>` になります。ここでは、pair の最初の要素は完了したタスクの結果であり、2 番目の要素は完了したタスクのインデックスです。 入力したタスクの種類が `void` である場合、出力は `task<size_t>` になります。この場合、結果は完了したタスクのインデックスです。  
  
### <a name="remarks"></a>コメント  
 `when_any` は、その結果、`task` を生成する、非ブロッキング関数です。 異なり[task::wait](task-class.md#wait)でこの関数の呼び出しは安全では、 [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] ASTA (アプリケーション STA) スレッド上のアプリケーションです。  
  
 詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

