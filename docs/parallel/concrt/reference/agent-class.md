---
title: "agent クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agent
- AGENTS/concurrency::agent
- AGENTS/concurrency::agent::agent
- AGENTS/concurrency::agent::cancel
- AGENTS/concurrency::agent::start
- AGENTS/concurrency::agent::status
- AGENTS/concurrency::agent::status_port
- AGENTS/concurrency::agent::wait
- AGENTS/concurrency::agent::wait_for_all
- AGENTS/concurrency::agent::wait_for_one
- AGENTS/concurrency::agent::done
- AGENTS/concurrency::agent::run
dev_langs:
- C++
helpviewer_keywords:
- agent class
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 1e6e23e742137bffd9035ecf69ecc32d199ca0c5
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="agent-class"></a>agent クラス
すべての独立エージェントの基底クラスとして使用されるクラスです。 他のエージェントに状態が表示されないようにしたり、メッセージ渡しでやり取りしたりする目的で使用されます。  
  
## <a name="syntax"></a>構文  
  
```
class agent;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[エージェント](#ctor)|オーバーロードされます。 エージェントを構築します。|  
|[~ agent デストラクター](#dtor)|エージェントを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[キャンセル](#cancel)|いずれかからのエージェントの移動、`agent_created`または`agent_runnable`状態を`agent_canceled`状態です。|  
|[start](#start)|エージェントの移動、`agent_created`状態から、`agent_runnable`状態、および実行をスケジュールします。|  
|[status](#status)|エージェントからのステータス情報の同期ソースです。|  
|[status_port](#status_port)|非同期エージェントから状態情報源です。|  
|[待機](#wait)|エージェント タスクが完了するまで待機します。|  
|[wait_for_all](#wait_for_all)|すべてのタスクの実行に指定されたエージェントを待ちます。|  
|[wait_for_one](#wait_for_one)|いずれかの指定されたエージェント タスクが完了するまで待機します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[完成です](#done)|エージェントを移動、`agent_done`状態、エージェントが完了したことを示します。|  
|[run](#run)|エージェントの主要なタスクを表します。 `run`派生クラスでオーバーライドされる必要があり、実行する、エージェントを指定が開始された後です。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期エージェント](../../../parallel/concrt/asynchronous-agents.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `agent`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>エージェント 

 エージェントを構築します。  
  
```
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PScheduler`  
 `Scheduler`オブジェクト内のエージェントの実行タスクのスケジュールを設定します。  
  
 `_PGroup`  
 `ScheduleGroup`オブジェクト内のエージェントの実行タスクのスケジュールを設定します。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="remarks"></a>コメント  
 指定しない場合、ランタイムは、既定のスケジューラを使用して、`_PScheduler`または`_PGroup`パラメーター。  
  
##  <a name="dtor"></a>~ エージェント 

 エージェントを破棄します。  
  
```
virtual ~agent();
```  
  
### <a name="remarks"></a>コメント  
 終了状態にない場合、エージェントを破棄するとエラーには (どちらか`agent_done`または`agent_canceled`)。 エージェントから継承するクラスのデストラクターで終了状態に到達するを待機してこれを回避する、`agent`クラスです。  
  
##  <a name="cancel"></a>キャンセル 

 いずれかからのエージェントの移動、`agent_created`または`agent_runnable`状態を`agent_canceled`状態です。  
  
```
bool cancel();
```  
  
### <a name="return-value"></a>戻り値  
 `true`エージェントが取り消された場合`false`それ以外の場合。 エージェントは、既にの実行が開始またはが既に完了した場合、キャンセルできません。  
  
##  <a name="done"></a>完成です 

 エージェントを移動、`agent_done`状態、エージェントが完了したことを示します。  
  
```
bool done();
```  
  
### <a name="return-value"></a>戻り値  
 `true`エージェントを移動する場合、`agent_done`状態、`false`それ以外の場合。 取り消されたエージェントに移動することはできません、`agent_done`状態です。  
  
### <a name="remarks"></a>コメント  
 最後に、このメソッドを呼び出す必要があります、`run`エージェントの実行がわかっている場合、メソッドが完了します。  
  
##  <a name="run"></a>実行します。 

 エージェントの主要なタスクを表します。 `run`派生クラスでオーバーライドされる必要があり、実行する、エージェントを指定が開始された後です。  
  
```
virtual void run() = 0;
```  
  
### <a name="remarks"></a>コメント  
 エージェントの状態は`agent_started`右このメソッドが呼び出される前にします。 メソッドを呼び出す必要があります`done`してエージェントを戻る前に適切な状態にし、例外をスローしないことがあります。  
  
##  <a name="start"></a>開始 

 エージェントの移動、`agent_created`状態から、`agent_runnable`状態、および実行をスケジュールします。  
  
```
bool start();
```  
  
### <a name="return-value"></a>戻り値  
 `true`エージェントが正常に開始された場合`false`それ以外の場合。 取り消されたエージェントを開始することはできません。  
  
##  <a name="status"></a>状態 

 エージェントからのステータス情報の同期ソースです。  
  
```
agent_status status();
```  
  
### <a name="return-value"></a>戻り値  
 エージェントの現在の状態を返します。 注: この返される状態が返された直後に変更可能性があります。  
  
##  <a name="status_port"></a>status_port 

 非同期エージェントから状態情報源です。  
  
```
ISource<agent_status>* status_port();
```  
  
### <a name="return-value"></a>戻り値  
 エージェントの現在の状態に関するメッセージを送信できるメッセージのソースを返します。  
  
##  <a name="wait"></a>待機 

 エージェント タスクが完了するまで待機します。  
  
```
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PAgent`  
 待機するエージェントへのポインター。  
  
 `_Timeout`  
 ミリ秒単位の待機する最大時間。  
  
### <a name="return-value"></a>戻り値  
 `agent_status`待機が完了すると、エージェントのです。 指定できます`agent_canceled`または`agent_done`です。  
  
### <a name="remarks"></a>コメント  
 エージェントに入ったときに、エージェント タスクが完了した、`agent_canceled`または`agent_done`状態です。  
  
 場合、パラメーター`_Timeout`定数以外の値を持つ`COOPERATIVE_TIMEOUT_INFINITE`、例外[operation_timed_out](operation-timed-out-class.md)が、一定の時間には、エージェントがそのタスクを完了する前に有効期限が切れる場合にスローされます。  
  
##  <a name="wait_for_all"></a>wait_for_all 

 すべてのタスクの実行に指定されたエージェントを待ちます。  
  
```
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>パラメーター  
 `count`  
 エージェントのポインター、配列内の数`_PAgents`します。  
  
 `_PAgents`  
 待機するエージェントへのポインターの配列。  
  
 `_PStatus`  
 エージェントの状態の配列へのポインター。 各状態の値は、メソッドが戻るときに、対応するエージェントの状態を表します。  
  
 `_Timeout`  
 ミリ秒単位の待機する最大時間。  
  
### <a name="remarks"></a>コメント  
 エージェントに入ったときに、エージェント タスクが完了した、`agent_canceled`または`agent_done`状態です。  
  
 場合、パラメーター`_Timeout`定数以外の値を持つ`COOPERATIVE_TIMEOUT_INFINITE`、例外[operation_timed_out](operation-timed-out-class.md)が、一定の時間には、エージェントがそのタスクを完了する前に有効期限が切れる場合にスローされます。  
  
##  <a name="wait_for_one"></a>wait_for_one 

 いずれかの指定されたエージェント タスクが完了するまで待機します。  
  
```
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>パラメーター  
 `count`  
 エージェントのポインター、配列内の数`_PAgents`します。  
  
 `_PAgents`  
 待機するエージェントへのポインターの配列。  
  
 `_Status`  
 エージェントの状態を格納する変数への参照。  
  
 `_Index`  
 エージェントのインデックスを格納する変数への参照。  
  
 `_Timeout`  
 ミリ秒単位の待機する最大時間。  
  
### <a name="remarks"></a>コメント  
 エージェントに入ったときに、エージェント タスクが完了した、`agent_canceled`または`agent_done`状態です。  
  
 場合、パラメーター`_Timeout`定数以外の値を持つ`COOPERATIVE_TIMEOUT_INFINITE`、例外[operation_timed_out](operation-timed-out-class.md)が、一定の時間には、エージェントがそのタスクを完了する前に有効期限が切れる場合にスローされます。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

