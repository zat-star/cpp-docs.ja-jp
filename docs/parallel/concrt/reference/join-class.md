---
title: "クラスの結合 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- join
- AGENTS/concurrency::join
- AGENTS/concurrency::join::join
- AGENTS/concurrency::join::accept_message
- AGENTS/concurrency::join::consume_message
- AGENTS/concurrency::join::link_target_notification
- AGENTS/concurrency::join::propagate_message
- AGENTS/concurrency::join::propagate_to_any_targets
- AGENTS/concurrency::join::release_message
- AGENTS/concurrency::join::reserve_message
- AGENTS/concurrency::join::resume_propagation
dev_langs:
- C++
helpviewer_keywords:
- join class
ms.assetid: d2217119-70a1-40b6-809f-c1c13a571c3f
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 7847f1d8611c65e698ed5d47c3c20ef02ce048ff
ms.lasthandoff: 03/17/2017

---
# <a name="join-class"></a>join クラス
`join` メッセージング ブロックは、単一のターゲットと複数のソースを持つ順序付けられた `propagator_block` であり、各ソースから、種類が `T` であるメッセージを結合します。  
  
## <a name="syntax"></a>構文  
  
```
template<class T,
    join_type _Jtype = non_greedy>
class join : public propagator_block<single_link_registry<ITarget<std::vector<T>>>,
    multi_link_registry<ISource<T>>>;
```   
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 メッセージのペイロードの種類は、参加していて、ブロックによって反映されます。  
  
 `_Jtype`  
 種類の`join`ブロックか、これは`greedy`または`non_greedy`  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[結合](#ctor)|オーバーロードされます。 構築、`join`メッセージング ブロックします。|  
|[~ join デストラクター](#dtor)|破棄、`join`ブロックします。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept_message](#accept_message)|これによって提供されたメッセージを受け入れ`join`メッセージング ブロック、呼び出し元に所有権を移譲します。|  
|[consume_message](#consume_message)|によって以前に提供メッセージを使用して、`join`メッセージング ブロックされ、呼び出し元に所有権を移動するターゲットが予約されます。|  
|[link_target_notification](#link_target_notification)|新しいターゲットがこれにリンクされていることを通知するコールバック`join`メッセージング ブロックします。|  
|[propagate_message](#propagate_message)|メッセージを非同期的に渡す、`ISource`このブロック`join`メッセージング ブロックします。 によって呼び出される、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[propagate_to_any_targets](#propagate_to_any_targets)|これらがすべて伝達されるときに、メッセージは、各ソースから入力メッセージを含む出力メッセージを構築します。 各ターゲットをこの出力メッセージを送信します。|  
|[release_message](#release_message)|以前のメッセージの予約を解放します。 (上書き[source_block::release_message](source-block-class.md#release_message))。|  
|[reserve_message](#reserve_message)|これによって以前に提供メッセージを予約`join`メッセージング ブロックします。 (上書き[source_block::reserve_message](source-block-class.md#reserve_message))。|  
|[resume_propagation](#resume_propagation)|伝達は、予約が解放された後に再開します。 (上書き[source_block::resume_propagation](source-block-class.md#resume_propagation))。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `join`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="accept_message"></a>accept_message 

 これによって提供されたメッセージを受け入れ`join`メッセージング ブロック、呼び出し元に所有権を移譲します。  
  
```
virtual message<_OutputType>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`オブジェクトの呼び出し元が今すぐの所有権を持っています。  
  
##  <a name="consume_message"></a>consume_message 

 によって以前に提供メッセージを使用して、`join`メッセージング ブロックされ、呼び出し元に所有権を移動するターゲットが予約されます。  
  
```
virtual message<_OutputType>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`オブジェクトの読み取り中です。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`オブジェクトの呼び出し元が今すぐの所有権を持っています。  
  
### <a name="remarks"></a>コメント  
 ような`accept`への呼び出し前に必ず、`reserve`です。  
  
##  <a name="ctor"></a>結合 

 構築、`join`メッセージング ブロックします。  
  
```
join(
    size_t _NumInputs);

join(
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>パラメーター  
 `_NumInputs`  
 この数の入力`join`ブロックが許可されます。  
  
 `_Filter`  
 提供されたメッセージを受け入れられる必要があるかどうかを決定するフィルター関数。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `join` オブジェクト。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `join` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="remarks"></a>コメント  
 `_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。  
  
 種類`filter_method`シグネチャを持つファンクターは、`bool (T const &)`によりが呼び出される、`join`メッセージング ブロックを提供されたメッセージを受け入れる必要があるかどうかを判断します。  
  
##  <a name="dtor"></a>~ 結合 

 破棄、`join`ブロックします。  
  
```
~join();
```  
  
##  <a name="link_target_notification"></a>link_target_notification 

 新しいターゲットがこれにリンクされていることを通知するコールバック`join`メッセージング ブロックします。  
  
```
virtual void link_target_notification(_Inout_ ITarget<std::vector<T>> *);
```  
  
##  <a name="propagate_message"></a>propagate_message 

 メッセージを非同期的に渡す、`ISource`このブロック`join`メッセージング ブロックします。 によって呼び出される、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```
message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)の関係を決定するターゲットを示す値。  
  
##  <a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 これらがすべて伝達されるときに、メッセージは、各ソースから入力メッセージを含む出力メッセージを構築します。 各ターゲットをこの出力メッセージを送信します。  
  
```
void propagate_to_any_targets(_Inout_opt_ message<_OutputType> *);
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

 これによって以前に提供メッセージを予約`join`メッセージング ブロックします。  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 `true`場合は、メッセージが正常に予約された、`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 後に`reserve`と呼ばれる場合は、返された場合`true`か、`consume`または`release`か、実行するか、メッセージの所有権を解放呼び出す必要があります。  
  
##  <a name="resume_propagation"></a>resume_propagation 

 伝達は、予約が解放された後に再開します。  
  
```
virtual void resume_propagation();
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [choice クラス](choice-class.md)   
 [multitype_join クラス](multitype-join-class.md)

