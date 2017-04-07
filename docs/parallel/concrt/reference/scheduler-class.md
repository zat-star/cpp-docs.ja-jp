---
title: "Scheduler クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Scheduler
- CONCRT/concurrency::Scheduler
- CONCRT/concurrency::Scheduler::Scheduler
- CONCRT/concurrency::Scheduler::Attach
- CONCRT/concurrency::Scheduler::Create
- CONCRT/concurrency::Scheduler::CreateScheduleGroup
- CONCRT/concurrency::Scheduler::GetNumberOfVirtualProcessors
- CONCRT/concurrency::Scheduler::GetPolicy
- CONCRT/concurrency::Scheduler::Id
- CONCRT/concurrency::Scheduler::IsAvailableLocation
- CONCRT/concurrency::Scheduler::Reference
- CONCRT/concurrency::Scheduler::RegisterShutdownEvent
- CONCRT/concurrency::Scheduler::Release
- CONCRT/concurrency::Scheduler::ResetDefaultSchedulerPolicy
- CONCRT/concurrency::Scheduler::ScheduleTask
- CONCRT/concurrency::Scheduler::SetDefaultSchedulerPolicy
dev_langs:
- C++
helpviewer_keywords:
- Scheduler class
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
caps.latest.revision: 19
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: cc39a524e9a65aeab0c84fb43f5b38ddd892923e
ms.lasthandoff: 03/17/2017

---
# <a name="scheduler-class"></a>Scheduler クラス
同時実行ランタイム スケジューラの抽象化を表します。  
  
## <a name="syntax"></a>構文  
  
```
class Scheduler;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[スケジューラ](#ctor)|オブジェクト、`Scheduler`クラスは、ファクトリ メソッドを使用して作成された専用ことができます。 または暗黙的にします。|  
|[~ Scheduler デストラクター](#dtor)|オブジェクト、`Scheduler`に対するすべての外部参照が存在しないとき、クラスは暗黙的に破棄されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[添付](#attach)|呼び出し元のコンテキストにスケジューラをアタッチします。 このメソッドから制御が戻た後は、呼び出し元のコンテキストは、スケジューラによって管理され、スケジューラが、現在のスケジューラになります。|  
|[作成します。](#create)|動作は、新しいスケジューラが作成、`_Policy`パラメーター、スケジューラの最初の参照を配置し、ポインターを返します。|  
|[CreateScheduleGroup](#createschedulegroup)|オーバーロードされます。 スケジューラ内で新しいスケジュール グループを作成します。 パラメーターを受け取るバージョンで`_Placement`する位置をそのパラメーターで指定した実行増えますを新しく作成されたスケジュール グループ内のタスクが発生します。|  
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|スケジューラの仮想プロセッサの現在の数を返します。|  
|[GetPolicy](#getpolicy)|スケジューラの作成に使用されたポリシーのコピーを返します。|  
|[Id](#id)|スケジューラの一意の識別子を返します。|  
|[IsAvailableLocation](#isavailablelocation)|指定された場所が、スケジューラで利用できるかどうかを決定します。|  
|[参照](#reference)|スケジューラの参照カウントをインクリメントします。|  
|[RegisterShutdownEvent](#registershutdownevent)|Windows イベント ハンドルが渡された原因、`_Event`シグナル状態になるスケジューラがシャット ダウンし、それ自体を破棄するときのパラメーターです。 イベントがシグナル状態に、スケジューラにスケジュールされていたすべての作業が完了しました。 このメソッドでは、複数のシャット ダウン イベントを登録できます。|  
|[Release](#release)|スケジュールの参照カウントをデクリメントします。|  
|[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)|既定のスケジューラ ポリシーを実行時の既定値にリセットします。 既定のスケジューラが作成されると、次回実行時の既定のポリシー設定が使用されます。|  
|[ScheduleTask](#scheduletask)|オーバーロードされます。 スケジューラ内での軽量タスクをスケジュールします。 軽量タスクは、ランタイムによって決定スケジュール グループに配置されます。 パラメーターを受け取るバージョンで`_Placement`タスクがある指定した場所に実行する増えます。|  
|[SetDefaultSchedulerPolicy](#setdefaultschedulerpolicy)|既定のスケジューラの作成に使用するユーザー定義のポリシーを使用します。 プロセス内で既定のスケジューラが存在しない場合にのみ、このメソッドを呼び出すことができます。 既定のポリシーを設定すると、それまで保持するか、次の有効な呼び出し、`SetDefaultSchedulerPolicy`または[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)メソッドです。|  
  
## <a name="remarks"></a>コメント  
 作業を実行キューに登録されて、アプリケーションで、同時実行ランタイム スケジューラが、スレッドなどのオペレーティング システムの実行コンテキストにマップされる実行コンテキストを使用します。 いつでもスケジューラの同時実行レベルはリソース マネージャーによって許可された仮想プロセッサの数に等しくなります。 仮想プロセッサとは、処理リソースを抽象化したものであり、基になるシステムのハードウェア スレッドに対応しています。 指定された時点に&1; つの仮想プロセッサで実行できるスケジューラ コンテキストは&1; つのみです。  
  
 同時実行ランタイムでは、1 つのプロセスを並列処理を実行する既定のスケジューラを作成します。 さらに、独自のスケジューラ インスタンスを作成でき、このクラスを使用して操作できます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Scheduler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="attach"></a>アタッチ 

 呼び出し元のコンテキストにスケジューラをアタッチします。 このメソッドから制御が戻た後は、呼び出し元のコンテキストは、スケジューラによって管理され、スケジューラが、現在のスケジューラになります。  
  
```
virtual void Attach() = 0;
```  
  
### <a name="remarks"></a>コメント  
 スケジューラでの参照を配置するスケジューラを暗黙的にアタッチします。  
  
 ある時点で、将来的に呼び出す必要があります、 [currentscheduler::detach](currentscheduler-class.md#detach)スケジューラがシャット ダウンを許可するためのメソッドです。  
  
 このメソッドが既に別のスケジューラにアタッチされているコンテキストから呼び出される場合は、既存のスケジューラが以前のスケジューラとして記録され、新しく作成されたスケジューラが、現在のスケジューラします。 呼び出すと、`CurrentScheduler::Detach`メソッドでは後で、以前のスケジューラは、現在のスケジューラとして復元されます。  
  
 このメソッドをスローする[improper_scheduler_attach](improper-scheduler-attach-class.md)このスケジューラは、現在のスケジューラで呼び出し元のコンテキストの場合に例外です。  
  
##  <a name="create"></a>作成します。 

 動作は、新しいスケジューラが作成、`_Policy`パラメーター、スケジューラの最初の参照を配置し、ポインターを返します。  
  
```
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Policy`  
 スケジューラ ポリシーを新しく作成されたスケジューラの動作について説明します。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたスケジューラへのポインター。 これは、`Scheduler`に課せられた最初の参照カウントが付きます。  
  
### <a name="remarks"></a>コメント  
 スケジューラの作成後、`Create`メソッドを呼び出す必要があります、`Release`最初の参照カウントを削除して、スケジューラがシャット ダウンを許可するために、将来のいつかメソッドです。  
  
 このメソッドで作成されたスケジューラは、呼び出し元のコンテキストにアタッチされていません。 使用してコンテキストに関連付けることができます、[アタッチ](#attach)メソッドです。  
  
 このメソッドを含む、例外のさまざまな[scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)と[invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)します。  
  
##  <a name="createschedulegroup"></a>CreateScheduleGroup 

 スケジューラ内で新しいスケジュール グループを作成します。 パラメーターを受け取るバージョンで`_Placement`する位置をそのパラメーターで指定した実行増えますを新しく作成されたスケジュール グループ内のタスクが発生します。  
  
```
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Placement`  
 ここで、スケジュール グループ内のタスクは増えますでを実行する場所への参照。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたスケジュール グループへのポインター。 これは、`ScheduleGroup`に課せられた最初の参照カウントが付きます。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります、[リリース](schedulegroup-class.md#release)スケジューリングの作業が済んだら、スケジュール グループのメソッドです。 スケジューラは、スケジュールを破棄グループへのキューに置かれたすべての作業が完了します。  
  
 注このスケジューラを明示的に作成した場合は、スケジューラの参照を解放する前に、内のグループのスケジュールへのすべての参照を解放する必要があります。  
  
##  <a name="getnumberofvirtualprocessors"></a>GetNumberOfVirtualProcessors 

 スケジューラの仮想プロセッサの現在の数を返します。  
  
```
virtual unsigned int GetNumberOfVirtualProcessors() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 現在のスケジューラの仮想プロセッサの数。  
  
##  <a name="getpolicy"></a>GetPolicy 

 スケジューラの作成に使用されたポリシーのコピーを返します。  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラの作成に使用されたポリシーのコピー。  
  
##  <a name="id"></a>Id 

 スケジューラの一意の識別子を返します。  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラの一意の識別子。  
  
##  <a name="isavailablelocation"></a>IsAvailableLocation 

 指定された場所が、スケジューラで利用できるかどうかを決定します。  
  
```
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Placement`  
 スケジューラのクエリを実行する場所への参照。  
  
### <a name="return-value"></a>戻り値  
 場所がで指定するかどうかを示す値、`_Placement`引数は、スケジューラを使用できます。  
  
### <a name="remarks"></a>コメント  
 戻り値は、指定の場所が使用できるかどうかを瞬間的にサンプリングであることに注意してください。 複数のスケジューラが存在する場合は、動的なリソースの管理は、追加または任意の時点でスケジューラからリソースを取り上げる倍にできます。 この場合は、特定の場所は、可用性に変更できます。  
  
##  <a name="reference"></a>参照 

 スケジューラの参照カウントをインクリメントします。  
  
```
virtual unsigned int Reference() = 0 ;
```  
  
### <a name="return-value"></a>戻り値  
 新たにインクリメントされた参照カウントします。  
  
### <a name="remarks"></a>コメント  
 これは通常、コンポジションのスケジューラの有効期間管理に使用されます。 参照数を&0; にスケジューラが、スケジューラがシャット ダウンされるとデストラクション自体は結局のところ、スケジューラで作業が完了しました。  
  
 メソッドがスローされます、 [improper_scheduler_reference](improper-scheduler-reference-class.md)例外の場合は、参照カウントを呼び出す前に、`Reference`メソッドは&0; で、スケジューラが所有していないコンテキストから呼び出しが実行されました。  
  
##  <a name="registershutdownevent"></a>RegisterShutdownEvent 

 Windows イベント ハンドルが渡された原因、`_Event`シグナル状態になるスケジューラがシャット ダウンし、それ自体を破棄するときのパラメーターです。 イベントがシグナル状態に、スケジューラにスケジュールされていたすべての作業が完了しました。 このメソッドでは、複数のシャット ダウン イベントを登録できます。  
  
```
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Event`  
 スケジューラがシャット ダウンし、それ自体を破棄するときに、ランタイムによって通知される Windows イベント オブジェクトへのハンドル。  
  
##  <a name="release"></a>リリース 

 スケジュールの参照カウントをデクリメントします。  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 新たにデクリメントされた参照カウントします。  
  
### <a name="remarks"></a>コメント  
 これは通常、コンポジションのスケジューラの有効期間管理に使用されます。 参照数を&0; にスケジューラが、スケジューラがシャット ダウンされるとデストラクション自体は結局のところ、スケジューラで作業が完了しました。  
  
##  <a name="resetdefaultschedulerpolicy"></a>ResetDefaultSchedulerPolicy 

 既定のスケジューラ ポリシーを実行時の既定値にリセットします。 既定のスケジューラが作成されると、次回実行時の既定のポリシー設定が使用されます。  
  
```
static void __cdecl ResetDefaultSchedulerPolicy();
```  
  
### <a name="remarks"></a>コメント  
 プロセス内で、既定のスケジューラが存在する間、このメソッドを呼び出すことができます。 既存の既定のスケジューラのポリシーは影響しません。 ただし、既定のスケジューラがシャット ダウンすると、新しい既定値が、後の時点で作成された、新しいスケジューラは、実行時の既定のポリシー設定を使用します。  
  
##  <a name="ctor"></a>スケジューラ 

 オブジェクト、`Scheduler`クラスは、ファクトリ メソッドを使用して作成された専用ことができます。 または暗黙的にします。  
  
```
Scheduler();
```  
  
### <a name="remarks"></a>コメント  
 プロセスの既定のスケジューラが、多くの呼び出し元のコンテキストにアタッチされているスケジューラを必要とするランタイム関数を使用するとき暗黙的に作成されます。 内のメソッド、`CurrentScheduler`クラスと、PPL とエージェントの各層の機能は通常暗黙的な添付ファイルを実行します。  
  
 いずれかで明示的にスケジューラを作成することも、`CurrentScheduler::Create`メソッドまたは`Scheduler::Create`メソッドです。  
  
##  <a name="dtor"></a>~ スケジューラ 

 オブジェクト、`Scheduler`に対するすべての外部参照が存在しないとき、クラスは暗黙的に破棄されます。  
  
```
virtual ~Scheduler();
```  
  
##  <a name="scheduletask"></a>ScheduleTask 

 スケジューラ内での軽量タスクをスケジュールします。 軽量タスクは、ランタイムによって決定スケジュール グループに配置されます。 パラメーターを受け取るバージョンで`_Placement`タスクがある指定した場所に実行する増えます。  
  
```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;

virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data,
    location& _Placement) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Proc`  
 軽量タスクの本体を実行するために実行する関数へのポインター。  
  
 `_Data`  
 タスクの本体にパラメーターとして渡されるデータへの void ポインター。  
  
 `_Placement`  
 軽量タスクが実行に向けてバイアスする場所への参照。  
  
##  <a name="setdefaultschedulerpolicy"></a>SetDefaultSchedulerPolicy 

 既定のスケジューラの作成に使用するユーザー定義のポリシーを使用します。 プロセス内で既定のスケジューラが存在しない場合にのみ、このメソッドを呼び出すことができます。 既定のポリシーを設定すると、それまで保持するか、次の有効な呼び出し、`SetDefaultSchedulerPolicy`または[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)メソッドです。  
  
```
static void __cdecl SetDefaultSchedulerPolicy(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Policy`  
 既定のスケジューラ ポリシーとして設定するポリシー。  
  
### <a name="remarks"></a>コメント  
 場合、`SetDefaultSchedulerPolicy`プロセス内で、既定のスケジューラが既に存在する場合、メソッドが呼び出された、ランタイムは、スロー、 [default_scheduler_exists](default-scheduler-exists-class.md)例外です。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [Scheduler クラス](scheduler-class.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




