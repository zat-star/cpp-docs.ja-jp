---
title: "task クラス (同時実行ランタイム) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppltasks/concurrency::task
dev_langs:
- C++
helpviewer_keywords:
- task class
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 7bbe0445c59279423665cd7df4eb5972f23ecf78
ms.lasthandoff: 02/24/2017

---
# <a name="task-class-concurrency-runtime"></a>task クラス (同時実行ランタイム)
並列パターン ライブラリ (PPL) `task` クラス。 `task` オブジェクトは、非同期的に、他のタスクと同時に実行できる処理、および同時実行ランタイムの並列アルゴリズムによって生成される並列処理を表します。 正常に終了した場合は、型 `_ResultType` の結果が生成されます。 型 `task<void>` のタスクでは結果が作成されません。 タスクは、他のタスクと関係なく待機および取り消しできます。 継続を使用する他のタスクと共に構成することもできます ( `then`)、および結合 ( `when_all`) と選択の幅 ( `when_any`) パターンです。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T>
class task;

template <>
class task<void>;

template<typename _ReturnType>
class task;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 `T`  
 `_ReturnType`  
 このタスクの結果の型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`result_type`|このクラスのオブジェクトによって生成される結果の型。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[タスク コンス トラクター](#ctor)|オーバーロードされます。 `task` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[get メソッド](#get)|オーバーロードされます。 このタスクによって生成された結果を返します。 タスクが終了状態にない場合、`get` への呼び出しは、そのタスクが完了するまで待機します。 このメソッドは、`result_type` が `void` に指定されたタスクで呼び出された場合は値を返しません。|  
|[is_apartment_aware メソッド](#is_apartment_aware)|タスクが Windows ランタイム `IAsyncInfo` インターフェイスをラップ解除するか、こうしたタスクの子であるかを決定します。|  
|[is_done メソッド](#is_done)|タスクが完了したかどうかを決定します。|  
|[スケジューラ メソッド](#scheduler)|このタスクのスケジューラを返します|  
|[then メソッド](#then)|オーバーロードされます。 継続タスクをこのタスクに追加します。|  
|[wait メソッド](#wait)|このタスクが終了状態になるまで待機します。 タスクの依存関係すべてが満たされ、バックグラウンド ワーカーによって実行用にまだ検出されていない場合、`wait` はタスクをインラインで実行できます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator! = 演算子](#operator_neq)|オーバーロードされます。 2 つの `task` オブジェクトが異なる内部タスクを表すかどうかを決定します。|  
|[operator = 演算子](#operator_eq)|オーバーロードされます。 ある `task` オブジェクトの内容を別のオブジェクトの内容で置き換えます。|  
|[operator = 演算子](#operator_eq_eq)|オーバーロードされます。 2 つの `task` オブジェクトが同じ内部タスクを表すかどうかを決定します。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `task`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppltasks.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namegeta-get"></a><a name="get"></a>取得 

 このタスクによって生成された結果を返します。 タスクが終了状態にない場合、`get` への呼び出しは、そのタスクが完了するまで待機します。 このメソッドは、`result_type` が `void` に指定されたタスクで呼び出された場合は値を返しません。  
  
```
_ReturnType get() const;

void get() const;
```  
  
### <a name="return-value"></a>戻り値  
 タスクの結果。  
  
### <a name="remarks"></a>コメント  
 タスクが取り消された場合の呼び出し`get`をスロー、 [task_canceled](task-canceled-class.md)例外です。 タスクで別の例外が発生したり、継続元タスクからこのタスクに例外が反映された場合、`get` の呼び出しは、その例外をスローします。  
  
> [!IMPORTANT]
>  [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)]アプリを呼び出す必要はありません[concurrency::task::wait](#wait)または`get`(`wait`呼び出し`get`) STA で実行されるコードで それ以外の場合、ランタイム[concurrency::invalid_operation](invalid-operation-class.md)のため、これらのメソッドは、現在のスレッドをブロックし、アプリが反応しなくなる可能性があります。 ただし、結果は直ちに使用できるため、タスク ベースの継続で継続元タスクの結果を受け取るために `get` メソッドを呼び出すことができます。  
  
##  <a name="a-nameisapartmentawarea-isapartmentaware"></a><a name="is_apartment_aware"></a>is_apartment_aware 

 タスクが Windows ランタイム `IAsyncInfo` インターフェイスをラップ解除するか、こうしたタスクの子であるかを決定します。  
  
```
bool is_apartment_aware() const;
```  
  
### <a name="return-value"></a>戻り値  
 タスクが `true` インターフェイスをラップ解除するか、こうしたタスクの子である場合は `IAsyncInfo` を返します。それ以外の場合は、`false` を返します。  
  
##  <a name="a-nameisdonea--taskisdone-method-concurrency-runtime"></a><a name="is_done"></a>task::is_done メソッド (同時実行ランタイム)  
 タスクが完了したかどうかを決定します。  
  
```
bool is_done() const;
```  
  
### <a name="return-value"></a>戻り値  
 タスクが完了した場合は true を返します。それ以外の場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 関数は、タスクが完了した場合または取り消された場合に true を返します (ユーザー例外の有無は問いません)。  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>operator! = 

 2 つの `task` オブジェクトが異なる内部タスクを表すかどうかを決定します。  
  
```
bool operator!= (const task<_ReturnType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが異なる基本タスクを参照する場合は `true` を返します。それ以外の場合は `false` を返します。  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>演算子 = 

 ある `task` オブジェクトの内容を別のオブジェクトの内容で置き換えます。  
  
```
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 ソース `task` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 `task` がスマート ポインターのように動作すると、コピーの代入の後では、この `task` オブジェクトは `_Other` が実行する実際のタスクと同じタスクを表します。  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>演算子 = = 

 2 つの `task` オブジェクトが同じ内部タスクを表すかどうかを決定します。  
  
```
bool operator== (const task<_ReturnType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが同じ基本タスクを参照する場合は `true` を返します。それ以外の場合は `false` を返します。  
  
##  <a name="a-nameschedulera--taskscheduler-method-concurrency-runtime"></a><a name="scheduler"></a>task::scheduler メソッド (同時実行ランタイム)  
 このタスクのスケジューラを返します  
  
```
scheduler_ptr scheduler() const;
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラへのポインター  
  
##  <a name="a-namectora-task"></a><a name="ctor"></a>タスク 

 `task` オブジェクトを構築します。  
  
```
task();

template<typename T>
__declspec(
    noinline) explicit task(T _Param);

template<typename T>
__declspec(
    noinline) explicit task(T _Param, const task_options& _TaskOptions);

task(
    const task& _Other);

task(
    task&& _Other);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 パラメーターの型。これに基づいてタスクが構築されます。  
  
 `_Param`  
 パラメーター。これに基づいてタスクが構築されます。 Windows ストア アプリでタスクを使用する場合、ラムダ、関数オブジェクト、`task_completion_event<result_type>` オブジェクト、または Windows::Foundation::IAsyncInfo を指定できます。 ラムダまたは関数オブジェクトは、`std::function<X(void)>` と同等の型にする必要があります。Windows ストア アプリの場合、この X には、型 `result_type` の変数、`task<result_type>`、または Windows::Foundation::IAsyncInfo を指定できます。  
  
 `_TaskOptions`  
 タスク オプションには、キャンセル トークン、スケジューラなどがあります。  
  
 `_Other`  
 ソース `task` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `task` の既定のコンストラクターは、タスクをコンテナー内で使用できるようにすることのみを目的としています。 構築された既定のタスクは、有効なタスクを割り当てるまで使用できません。 などのメソッド`get`、`wait`または`then`をスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外構築された既定のタスクで呼び出されるとします。  
  
 `task_completion_event` から作成されたタスクは、タスクの完了イベントが設定されたときに完了します (その後で継続がスケジュールされます)。  
  
 キャンセル トークンを使用するバージョンのコンストラクターは、トークンの取得元となる `cancellation_token_source` を使用して取り消すことができるタスクを作成します。 キャンセル トークンを使用せずに作成されたタスクは、取り消すことはできません。  
  
 `Windows::Foundation::IAsyncInfo` インターフェイスまたは `IAsyncInfo` インターフェイスを返すラムダから作成されたタスクは、取り込まれている Windows ランタイムの非同期操作または非同期アクションが完了すると、終了状態になります。 同様に、`task<result_type>` を返すラムダから作成されたタスクは、内側のタスクが終了状態になったとき (ラムダがその状態を返すときではありません)、終了状態になります。  
  
 `task` は、スマート ポインターのように動作し、安全に値渡しされます。 この task には、複数のスレッドからアクセスできます。ロックする必要はありません。  
  
 Windows::Foundation::IAsyncInfo インターフェイスまたはそのようなインターフェイスを返すラムダを使用するコンストラクターのオーバーロードは、Windows ストア アプリでのみ使用できます。  
  
 詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。  
  
##  <a name="a-namethena-then"></a><a name="then"></a>そうしたら 

 継続タスクをこのタスクに追加します。  
  
```
template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions = task_options()) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;
```   
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 このタスクによって呼び出される関数オブジェクトの型。  
  
 `_Func`  
 このタスクが完了したときに実行される継続関数。 この継続関数では、`result_type` または `task<result_type>` の変数を入力として使用する必要があります。`result_type` は、このタスクによって生成される結果の型です。  
  
 `_TaskOptions`  
 タスク オプションには、キャンセル トークン、スケジューラ、および継続コンテキストなどがあります。 既定では、これら 3 つのオプションは継続元タスクから継承されます。  
  
 `_CancellationToken`  
 継続タスクに関連付けるキャンセル トークン。 キャンセル トークンなしで作成された継続タスクは、その継続元タスクのトークンを継承します。  
  
 `_ContinuationContext`  
 継続を実行する状況を指定する変数。 この変数は、Windows ストア スタイルのアプリで使用する場合にのみ役立ちます。 詳細については、次を参照してください[task_continuation_context。](task-continuation-context-class.md)  
  
### <a name="return-value"></a>戻り値  
 新しく作成された継続タスク。 返されるタスクの結果の型は、`_Func` が返す値によって決まります。  
  
### <a name="remarks"></a>コメント  
 Windows::Foundation::IAsyncInfo インターフェイスを返すラムダまたはファンクタを使用する `then` のオーバーロードは、Windows ストア アプリでのみ使用できます。  
  
 タスクの継続を使用して、非同期操作を構成する方法の詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>待機 

 このタスクが終了状態になるまで待機します。 タスクの依存関係すべてが満たされ、バックグラウンド ワーカーによって実行用にまだ検出されていない場合、`wait` はタスクをインラインで実行できます。  
  
```
task_status wait() const;
```  
  
### <a name="return-value"></a>戻り値  
 `task_status` の値。`completed` または `canceled` に設定される可能性があります。 タスクの実行時に例外が発生したり、継続元タスクからこのタスクに例外が反映された場合、`wait` はその例外をスローします。  
  
### <a name="remarks"></a>コメント  
  
> [!IMPORTANT]
>  [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] アプリケーションでは、STA で実行されるコードで `wait` を呼び出さないでください。 それ以外の場合、ランタイム[concurrency::invalid_operation](invalid-operation-class.md)のため、このメソッドは、現在のスレッドをブロックし、アプリが反応しなくなる可能性があります。 ただし、呼び出すことができます、 [concurrency::task_canceled](#get)タスク ベースの継続で継続元タスクの結果を受信するメソッドです。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

