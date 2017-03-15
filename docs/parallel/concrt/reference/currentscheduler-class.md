---
title: "CurrentScheduler クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::CurrentScheduler
dev_langs:
- C++
helpviewer_keywords:
- CurrentScheduler class
ms.assetid: 31c20e0e-4cdf-49b4-8220-d726130aad2b
caps.latest.revision: 20
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
ms.openlocfilehash: 514f0abb6e317a7b133203a2f089d492a46ae4c4
ms.lasthandoff: 02/24/2017

---
# <a name="currentscheduler-class"></a>CurrentScheduler クラス
呼び出し元コンテキストに関連付けられている現在のスケジューラの抽象化を表します。  
  
## <a name="syntax"></a>構文  
  
```
class CurrentScheduler;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Create メソッド](#create)|動作は、新しいスケジューラが作成、`_Policy`パラメーターを呼び出し元のコンテキストに接続します。 新しく作成されたスケジューラには、呼び出し元のコンテキストの現在のスケジューラになります。|  
|[CreateScheduleGroup メソッド](#createschedulegroup)|オーバーロードされます。 呼び出し元のコンテキストに関連付けられているスケジューラ内で新しいスケジュール グループを作成します。 パラメーターを受け取るバージョンで`_Placement`する位置をそのパラメーターで指定した実行増えますを新しく作成されたスケジュール グループ内のタスクが発生します。|  
|[Detach メソッド](#detach)|呼び出し元のコンテキストから現在のスケジューラをデタッチし、いずれかが存在する場合は、現在のスケジューラと以前に接続されているスケジューラを復元します。 呼び出し元のコンテキストがいずれかを使用してコンテキストを以前にアタッチされているスケジューラで管理し、このメソッドから制御が戻た後、`CurrentScheduler::Create`または`Scheduler::Attach`メソッドです。|  
|[Get メソッド](#get)|現在のスケジューラとも呼ばれます呼び出し元のコンテキストに関連付けられているスケジューラへのポインターを返します。|  
|[GetNumberOfVirtualProcessors メソッド](#getnumberofvirtualprocessors)|呼び出し元のコンテキストに関連付けられているスケジューラの仮想プロセッサの現在の数を返します。|  
|[GetPolicy メソッド](#getpolicy)|現在のスケジューラを使用して作成されたポリシーのコピーを返します。|  
|[Id メソッド](#id)|現在のスケジューラの一意の識別子を返します。|  
|[IsAvailableLocation メソッド](#isavailablelocation)|指定された場所が現在のスケジューラで利用できるかどうかを決定します。|  
|[RegisterShutdownEvent メソッド](#registershutdownevent)|Windows イベント ハンドルが渡された原因、`_ShutdownEvent`パラメーターがシグナル状態になると、現在のコンテキストに関連付けられているスケジューラがシャット ダウンし、それ自体を破棄します。 イベントがシグナル状態に、スケジューラにスケジュールされていたすべての作業が完了しました。 このメソッドでは、複数のシャット ダウン イベントを登録できます。|  
|[ScheduleTask メソッド](#scheduletask)|オーバーロードされます。 呼び出し元のコンテキストに関連付けられているスケジューラ内での軽量タスクをスケジュールします。 軽量タスクは、ランタイムによって決定スケジュール グループに配置されます。 パラメーターを受け取るバージョンで`_Placement`タスクがある指定した場所に実行する増えます。|  
  
## <a name="remarks"></a>コメント  
 スケジューラが存在しない場合 (を参照してください[スケジューラ](scheduler-class.md)) 呼び出し元のコンテキスト内で多くのメソッドに関連付けられている、`CurrentScheduler`クラスは、プロセスの既定のスケジューラの添付ファイルになります。 このような呼び出し中に、プロセスの既定のスケジューラが作成されたことがも予想できます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CurrentScheduler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namecreatea-create"></a><a name="create"></a>作成します。 

 動作は、新しいスケジューラが作成、`_Policy`パラメーターを呼び出し元のコンテキストに接続します。 新しく作成されたスケジューラには、呼び出し元のコンテキストの現在のスケジューラになります。  
  
```
static void __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Policy`  
 スケジューラ ポリシーを新しく作成されたスケジューラの動作について説明します。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラの添付ファイルは、スケジューラで暗黙的に参照カウントを配置します。  
  
 スケジューラの作成後、`Create`メソッドを呼び出す必要があります、 [currentscheduler::detach](#detach)スケジューラがシャット ダウンを許可するために、将来のいつかメソッドです。  
  
 このメソッドが既に別のスケジューラにアタッチされているコンテキストから呼び出される場合は、既存のスケジューラが以前のスケジューラとして記録され、新しく作成されたスケジューラが、現在のスケジューラします。 呼び出すと、`CurrentScheduler::Detach`メソッドでは後で、以前のスケジューラは、現在のスケジューラとして復元されます。  
  
 このメソッドを含む、例外のさまざまな[scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)と[invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)します。  
  
##  <a name="a-namecreateschedulegroupa-createschedulegroup"></a><a name="createschedulegroup"></a>CreateScheduleGroup 

 呼び出し元のコンテキストに関連付けられているスケジューラ内で新しいスケジュール グループを作成します。 パラメーターを受け取るバージョンで`_Placement`する位置をそのパラメーターで指定した実行増えますを新しく作成されたスケジュール グループ内のタスクが発生します。  
  
```
static ScheduleGroup* __cdecl CreateScheduleGroup();

static ScheduleGroup* __cdecl CreateScheduleGroup(location& _Placement);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Placement`  
 スケジュール グループ内のタスクが実行に向けてバイアスする場所への参照。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたスケジュール グループへのポインター。 これは、`ScheduleGroup`に課せられた最初の参照カウントが付きます。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。  
  
 呼び出す必要があります、[リリース](schedulegroup-class.md#release)スケジューリングの作業が済んだら、スケジュール グループのメソッドです。 スケジューラは、スケジュールを破棄グループへのキューに置かれたすべての作業が完了します。  
  
 注このスケジューラを明示的に作成した場合は、そこから現在のコンテキストをデタッチすることにより、スケジューラの参照を解放する前に、内のグループのスケジュールへのすべての参照を解放する必要があります。  
  
##  <a name="a-namedetacha-detach"></a><a name="detach"></a>デタッチ 

 呼び出し元のコンテキストから現在のスケジューラをデタッチし、いずれかが存在する場合は、現在のスケジューラと以前に接続されているスケジューラを復元します。 呼び出し元のコンテキストがいずれかを使用してコンテキストを以前にアタッチされているスケジューラで管理し、このメソッドから制御が戻た後、`CurrentScheduler::Create`または`Scheduler::Attach`メソッドです。  
  
```
static void __cdecl Detach();
```  
  
### <a name="remarks"></a>コメント  
 `Detach`メソッドでは、スケジューラから、参照カウントを暗黙的に削除します。  
  
 呼び出し元のコンテキストにアタッチされているスケジューラがない場合は、このメソッドを呼び出すが、 [scheduler_not_attached](scheduler-not-attached-class.md)例外がスローされます。  
  
 コンテキストからこのメソッドを呼び出すには内部管理、スケジューラまたはメソッドを使用せずに添付されたコンテキストで、 [scheduler::attach](scheduler-class.md#attach)または[currentscheduler::create](#create)メソッドになります、 [improper_scheduler_detach](improper-scheduler-detach-class.md)例外がスローされます。  
  
##  <a name="a-namegeta-get"></a><a name="get"></a>取得 

 現在のスケジューラとも呼ばれます呼び出し元のコンテキストに関連付けられているスケジューラへのポインターを返します。  
  
```
static Scheduler* __cdecl Get();
```  
  
### <a name="return-value"></a>戻り値  
 (現在のスケジューラ) の呼び出し元のコンテキストに関連付けられているスケジューラへのポインター。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。 追加の参照は配置されない、`Scheduler`このメソッドによって返されるオブジェクト。  
  
##  <a name="a-namegetnumberofvirtualprocessorsa-getnumberofvirtualprocessors"></a><a name="getnumberofvirtualprocessors"></a>GetNumberOfVirtualProcessors 

 呼び出し元のコンテキストに関連付けられているスケジューラの仮想プロセッサの現在の数を返します。  
  
```
static unsigned int __cdecl GetNumberOfVirtualProcessors();
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラが呼び出し元のコンテキストでは、そのスケジューラの仮想プロセッサの現在の番号に関連付けられている場合それ以外の場合、値`-1`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、呼び出し元のコンテキストが、スケジューラに関連付けられていない場合、スケジューラの添付ファイルでは生成されません。  
  
 このメソッドからの戻り値は、呼び出し元のコンテキストに関連付けられているスケジューラの仮想プロセッサの数の瞬間的にサンプリングされます。 この値は、返される時点古いことができましています。  
  
##  <a name="a-namegetpolicya-getpolicy"></a><a name="getpolicy"></a>GetPolicy 

 現在のスケジューラを使用して作成されたポリシーのコピーを返します。  
  
```
static SchedulerPolicy __cdecl GetPolicy();
```  
  
### <a name="return-value"></a>戻り値  
 ポリシーのコピーを現在のスケジューラを使用して作成されました。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。  
  
##  <a name="a-nameida-id"></a><a name="id"></a>Id 

 現在のスケジューラの一意の識別子を返します。  
  
```
static unsigned int __cdecl Id();
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラが呼び出し元のコンテキストでは、そのスケジューラの一意の識別子と関連付けられている場合それ以外の場合、値`-1`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、呼び出し元のコンテキストが、スケジューラに関連付けられていない場合、スケジューラの添付ファイルでは生成されません。  
  
##  <a name="a-nameisavailablelocationa-isavailablelocation"></a><a name="isavailablelocation"></a>IsAvailableLocation 

 指定された場所が現在のスケジューラで利用できるかどうかを決定します。  
  
```
static bool __cdecl IsAvailableLocation(const location& _Placement);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Placement`  
 に関する現在のスケジューラをクエリする場所への参照。  
  
### <a name="return-value"></a>戻り値  
 場所がで指定するかどうかを示す値、`_Placement`引数は、現在のスケジューラに使用できます。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、呼び出し元のコンテキストが、スケジューラに関連付けられていない場合、スケジューラの添付ファイルでは生成されません。  
  
 戻り値は、指定の場所が使用できるかどうかを瞬間的にサンプリングであることに注意してください。 複数のスケジューラが存在する場合は、動的なリソースの管理は、追加または任意の時点でスケジューラからリソースを取り上げる倍にできます。 この場合は、特定の場所は、可用性に変更できます。  
  
##  <a name="a-nameregistershutdowneventa-registershutdownevent"></a><a name="registershutdownevent"></a>RegisterShutdownEvent 

 Windows イベント ハンドルが渡された原因、`_ShutdownEvent`パラメーターがシグナル状態になると、現在のコンテキストに関連付けられているスケジューラがシャット ダウンし、それ自体を破棄します。 イベントがシグナル状態に、スケジューラにスケジュールされていたすべての作業が完了しました。 このメソッドでは、複数のシャット ダウン イベントを登録できます。  
  
```
static void __cdecl RegisterShutdownEvent(HANDLE _ShutdownEvent);
```  
  
### <a name="parameters"></a>パラメーター  
 `_ShutdownEvent`  
 現在のコンテキストに関連付けられているスケジューラがシャット ダウンし、それ自体を破棄するときに、ランタイムによって通知される Windows イベント オブジェクトへのハンドル。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにアタッチされているスケジューラがない場合は、このメソッドを呼び出すが、 [scheduler_not_attached](scheduler-not-attached-class.md)例外がスローされます。  
  
##  <a name="a-namescheduletaska-scheduletask"></a><a name="scheduletask"></a>ScheduleTask 

 呼び出し元のコンテキストに関連付けられているスケジューラ内での軽量タスクをスケジュールします。 軽量タスクは、ランタイムによって決定スケジュール グループに配置されます。 パラメーターを受け取るバージョンで`_Placement`タスクがある指定した場所に実行する増えます。  
  
```
static void __cdecl ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data);

static void __cdecl ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data,
    location& _Placement);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Proc`  
 軽量タスクの本体を実行するために実行する関数へのポインター。  
  
 `_Data`  
 タスクの本体にパラメーターとして渡されるデータへの void ポインター。  
  
 `_Placement`  
 軽量タスクが実行に向けてバイアスする場所への参照。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [Scheduler クラス](scheduler-class.md)   
 [PolicyElementKey 列挙型](concurrency-namespace-enums.md)   
 [タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




