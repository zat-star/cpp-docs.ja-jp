---
title: "timer クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- timer
- AGENTS/concurrency::timer
- AGENTS/concurrency::timer::timer
- AGENTS/concurrency::timer::pause
- AGENTS/concurrency::timer::start
- AGENTS/concurrency::timer::stop
- AGENTS/concurrency::timer::accept_message
- AGENTS/concurrency::timer::consume_message
- AGENTS/concurrency::timer::link_target_notification
- AGENTS/concurrency::timer::propagate_to_any_targets
- AGENTS/concurrency::timer::release_message
- AGENTS/concurrency::timer::reserve_message
- AGENTS/concurrency::timer::resume_propagation
dev_langs:
- C++
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
caps.latest.revision: 21
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
ms.openlocfilehash: d6dfdc1b03ac2d15aa575c16cbe86968f565c1c1
ms.lasthandoff: 03/17/2017

---
# <a name="timer-class"></a>timer クラス
`timer` メッセージング ブロックは単一のターゲットを持つ `source_block` であり、指定された時間の経過後か、特定の間隔で、メッセージをターゲットに送信することができます。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 このブロックの出力メッセージのペイロードの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[タイマー](#ctor)|オーバーロードされます。 構築、`timer`メッセージング ブロックを指定した間隔の後に、指定したメッセージを起動します。|  
|[~ timer デストラクター](#dtor)|破棄、`timer`メッセージング ブロックします。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[一時停止します。](#pause)|停止、`timer`メッセージング ブロックします。 繰り返し場合`timer`ブロックをメッセージングを再起動すると、それに続く`start()`を呼び出します。 – 非繰り返しタイマーの場合、これは、同じ効果として、`stop`呼び出します。|  
|[start](#start)|開始、`timer`メッセージング ブロックします。 これまでのミリ秒数の指定が呼び出されると、指定した値が反映されますとダウン ストリーム、`message`です。|  
|[停止します。](#stop)|停止、`timer`メッセージング ブロックします。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept_message](#accept_message)|これによって提供されたメッセージを受け入れ`timer`メッセージング ブロック、呼び出し元に所有権を移譲します。|  
|[consume_message](#consume_message)|によって以前に提供メッセージを使用して、`timer`所有権を呼び出し元に移動するターゲットによって予約されているとします。|  
|[link_target_notification](#link_target_notification)|新しいターゲットがこれにリンクされていることを通知するコールバック`timer`メッセージング ブロックします。|  
|[propagate_to_any_targets](#propagate_to_any_targets)|によって生成されたメッセージを提供しようとする、`timer`すべてのリンクのターゲットをブロックします。|  
|[release_message](#release_message)|以前のメッセージの予約を解放します。 (上書き[source_block::release_message](source-block-class.md#release_message))。|  
|[reserve_message](#reserve_message)|これによって以前に提供メッセージを予約`timer`メッセージング ブロックします。 (上書き[source_block::reserve_message](source-block-class.md#reserve_message))。|  
|[resume_propagation](#resume_propagation)|伝達は、予約が解放された後に再開します。 (上書き[source_block::resume_propagation](source-block-class.md#resume_propagation))。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](isource-class.md)  
  
 [source_block](source-block-class.md)  
  
 `timer`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="accept_message"></a>accept_message 

 これによって提供されたメッセージを受け入れ`timer`メッセージング ブロック、呼び出し元に所有権を移譲します。  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`オブジェクトの呼び出し元が今すぐの所有権を持っています。  
  
##  <a name="consume_message"></a>consume_message 

 によって以前に提供メッセージを使用して、`timer`所有権を呼び出し元に移動するターゲットによって予約されているとします。  
  
```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`オブジェクトの読み取り中です。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`オブジェクトの呼び出し元が今すぐの所有権を持っています。  
  
### <a name="remarks"></a>コメント  
 ような`accept`への呼び出し前に必ず、`reserve`です。  
  
##  <a name="link_target_notification"></a>link_target_notification 

 新しいターゲットがこれにリンクされていることを通知するコールバック`timer`メッセージング ブロックします。  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 新しくリンクされたターゲットへのポインター。  
  
##  <a name="pause"></a>一時停止します。 

 停止、`timer`メッセージング ブロックします。 繰り返し場合`timer`ブロックをメッセージングを再起動すると、それに続く`start()`を呼び出します。 – 非繰り返しタイマーの場合、これは、同じ効果として、`stop`呼び出します。  
  
```
void pause();
```  
  
##  <a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 によって生成されたメッセージを提供しようとする、`timer`すべてのリンクのターゲットをブロックします。  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```  
  
##  <a name="release_message"></a>release_message 

 以前のメッセージの予約を解放します。  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`リリースされているオブジェクトします。  
  
##  <a name="reserve_message"></a>reserve_message 

 これによって以前に提供メッセージを予約`timer`メッセージング ブロックします。  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`予約されているオブジェクトします。  
  
### <a name="return-value"></a>戻り値  
 `true`場合は、メッセージが正常に予約された、`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 後に`reserve`と呼ばれる場合は、返された場合`true`か、`consume`または`release`か、実行するか、メッセージの所有権を解放呼び出す必要があります。  
  
##  <a name="resume_propagation"></a>resume_propagation 

 伝達は、予約が解放された後に再開します。  
  
```
virtual void resume_propagation();
```  
  
##  <a name="start"></a>開始 

 開始、`timer`メッセージング ブロックします。 これまでのミリ秒数の指定が呼び出されると、指定した値が反映されますとダウン ストリーム、`message`です。  
  
```
void start();
```  
  
##  <a name="stop"></a>停止します。 

 停止、`timer`メッセージング ブロックします。  
  
```
void stop();
```  
  
##  <a name="ctor"></a>タイマー 

 構築、`timer`メッセージング ブロックを指定した間隔の後に、指定したメッセージを起動します。  
  
```
timer(
    unsigned int _Ms,
    T const& value,
    ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    Scheduler& _Scheduler,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    ScheduleGroup& _ScheduleGroup,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Ms`  
 ダウン ストリームに反映されるまで、指定されたメッセージの開始の呼び出し後までの経過時間 (ミリ秒) の数。  
  
 `value`  
 タイマーが経過すると下流伝達される値です。  
  
 `_PTarget`  
 タイマーからメッセージを伝達するターゲット。  
  
 `_Repeating`  
 True の場合、タイマーが定期的に起動されることを示します。 各`_Ms`(ミリ秒)。  
  
 `_Scheduler`  
 `Scheduler`オブジェクトの反映タスクを`timer`メッセージング ブロックがスケジュールされているがスケジュールされています。  
  
 `_ScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `timer` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="remarks"></a>コメント  
 指定しない場合、ランタイムは、既定のスケジューラを使用して、`_Scheduler`または`_ScheduleGroup`パラメーター。  
  
##  <a name="dtor"></a>~ タイマー 

 破棄、`timer`メッセージング ブロックします。  
  
```
~timer();
```  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

