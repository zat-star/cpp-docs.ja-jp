---
title: "unbounded_buffer クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unbounded_buffer
- AGENTS/concurrency::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::dequeue
- AGENTS/concurrency::unbounded_buffer::enqueue
- AGENTS/concurrency::unbounded_buffer::accept_message
- AGENTS/concurrency::unbounded_buffer::consume_message
- AGENTS/concurrency::unbounded_buffer::link_target_notification
- AGENTS/concurrency::unbounded_buffer::process_input_messages
- AGENTS/concurrency::unbounded_buffer::propagate_message
- AGENTS/concurrency::unbounded_buffer::propagate_output_messages
- AGENTS/concurrency::unbounded_buffer::release_message
- AGENTS/concurrency::unbounded_buffer::reserve_message
- AGENTS/concurrency::unbounded_buffer::resume_propagation
- AGENTS/concurrency::unbounded_buffer::send_message
- AGENTS/concurrency::unbounded_buffer::supports_anonymous_source
dev_langs:
- C++
ms.assetid: 6b1a939a-1819-4385-b1d8-708f83d4ec47
caps.latest.revision: 6
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
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 9a9c44985b1e9475b8760d835e2a8fd45361ea5a
ms.lasthandoff: 03/17/2017

---


`unbounded_buffer` メッセージング ブロックは、メッセージを無制限に格納することができる、複数のターゲットと複数のソースを持つ順序付けられた `propagator_block` です。  
  
## <a name="syntax"></a>構文  
  
```  
template<  
   class             _Type  
>  
class unbounded_buffer : public propagator_block<multi_link_registry<ITarget<            _Type>>, multi_link_registry<ISource<            _Type>>>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Type`  
 メッセージのペイロードの種類が格納され、バッファーによって反映されます。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[unbounded_buffer](#ctor)|オーバーロードされます。 構築、`unbounded_buffer`メッセージング ブロックします。|  
|[~ unbounded_buffer デストラクター](#dtor)|破棄、`unbounded_buffer`メッセージング ブロックします。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[キューから削除します。](#dequeue)|項目を削除、`unbounded_buffer`メッセージング ブロックします。|  
|[キューへの登録](#enqueue)|項目を追加、`unbounded_buffer`メッセージング ブロックします。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept_message](#accept_message)|これによって提供されたメッセージを受け入れ`unbounded_buffer`メッセージング ブロック、呼び出し元に所有権を移譲します。|  
|[consume_message](#consume_message)|によって以前に提供メッセージを使用して、`unbounded_buffer`メッセージング ブロックされ、呼び出し元に所有権を移動するターゲットが予約されます。|  
|[link_target_notification](#link_target_notification)|新しいターゲットがこれにリンクされていることを通知するコールバック`unbounded_buffer`メッセージング ブロックします。|  
|[process_input_messages](#process_input_messages)|場所、`message``_PMessage`この`unbounded_buffer`メッセージング ブロックと、すべてのリンクのターゲットにそれを提供しようとします。|  
|[propagate_message](#propagate_message)|メッセージを非同期的に渡す、`ISource`このブロック`unbounded_buffer`メッセージング ブロックします。 によって呼び出される、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[propagate_output_messages](#propagate_output_messages)|場所、`message``_PMessage`この`unbounded_buffer`メッセージング ブロックと、すべてのリンクのターゲットにそれを提供しようとします。 (上書き[source_block::propagate_output_messages](source-block-class.md#propagate_output_messages))。|  
|[release_message](#release_message)|以前のメッセージの予約を解放します。 (上書き[source_block::release_message](source-block-class.md#release_message))。|  
|[reserve_message](#reserve_message)|これによって以前に提供メッセージを予約`unbounded_buffer`メッセージング ブロックします。 (上書き[source_block::reserve_message](source-block-class.md#reserve_message))。|  
|[resume_propagation](#resume_propagation)|伝達は、予約が解放された後に再開します。 (上書き[source_block::resume_propagation](source-block-class.md#resume_propagation))。|  
|[send_message](#send_message)|メッセージを同期的に渡す、`ISource`このブロック`unbounded_buffer`メッセージング ブロックします。 によって呼び出される、`send`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[supports_anonymous_source](#supports_anonymous_source)|上書き、`supports_anonymous_source`を示すこのブロックがリンクされていないソースによって提供されたメッセージを受け取ることができます。 (上書き[itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source))。|  

 詳細については、次を参照してください。[非同期メッセージ ブロック](../asynchronous-message-blocks.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `unbounded_buffer`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="accept_message"></a>accept_message 

 これによって提供されたメッセージを受け入れ`unbounded_buffer`メッセージング ブロック、呼び出し元に所有権を移譲します。  
  
```  
virtual message<_Type> * accept_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`オブジェクトの呼び出し元が今すぐの所有権を持っています。  
  
##  <a name="consume_message"></a>consume_message 

 によって以前に提供メッセージを使用して、`unbounded_buffer`メッセージング ブロックされ、呼び出し元に所有権を移動するターゲットが予約されます。  
  
```  
virtual message<_Type> * consume_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`オブジェクトの読み取り中です。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`オブジェクトの呼び出し元が今すぐの所有権を持っています。  
  
### <a name="remarks"></a>コメント  
 ような`accept`への呼び出し前に必ず、`reserve`です。  
  
##  <a name="dequeue"></a>キューから削除します。 

 項目を削除、`unbounded_buffer`メッセージング ブロックします。  
  
```  
_Type dequeue();  
```  
  
### <a name="return-value"></a>戻り値  
 削除されたメッセージのペイロード、`unbounded_buffer`です。  
  
##  <a name="enqueue"></a>キューへの登録 

 項目を追加、`unbounded_buffer`メッセージング ブロックします。  
  
```  
bool enqueue(  
   _Type const&                 _Item  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Item`  
 追加する項目。  
  
### <a name="return-value"></a>戻り値  
 `true`項目が受け入れられた場合`false`それ以外の場合。  
  
##  <a name="link_target_notification"></a>link_target_notification 

 新しいターゲットがこれにリンクされていることを通知するコールバック`unbounded_buffer`メッセージング ブロックします。  
  
```  
virtual void link_target_notification(  
   _Inout_ ITarget<_Type> *                 _PTarget  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 新しくリンクされたターゲットへのポインター。  
  
##  <a name="propagate_message"></a>propagate_message 

 メッセージを非同期的に渡す、`ISource`このブロック`unbounded_buffer`メッセージング ブロックします。 によって呼び出される、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```  
virtual message_status propagate_message(  
   _Inout_ message<_Type> *                 _PMessage,  
   _Inout_ ISource<_Type> *                 _PSource  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md#message_status)の関係を決定するターゲットを示す値。  
  
##  <a name="propagate_output_messages"></a>propagate_output_messages 

 場所、`message``_PMessage`この`unbounded_buffer`メッセージング ブロックと、すべてのリンクのターゲットにそれを提供しようとします。  
  
```  
virtual void propagate_output_messages();  
```  
  
### <a name="remarks"></a>コメント  
 別のメッセージが既に事前のかどうか、 `unbounded_buffer`、前のメッセージを受け入れるか、使用するまで、リンクされたターゲットへの伝達は行われません。 最初のターゲットは正常にリンクされた`accept`または`consume`メッセージ所有権し、他のターゲットことができますし、メッセージが表示されません。  
  
##  <a name="process_input_messages"></a>process_input_messages 

 場所、`message``_PMessage`この`unbounded_buffer`メッセージング ブロックと、すべてのリンクのターゲットにそれを提供しようとします。  
  
```  
virtual void process_input_messages(  
   _Inout_ message<_Type> *                 _PMessage  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
  
##  <a name="release_message"></a>release_message 

 以前のメッセージの予約を解放します。  
  
```  
virtual void release_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`リリースされているオブジェクトします。  
  
##  <a name="reserve_message"></a>reserve_message 

 これによって以前に提供メッセージを予約`unbounded_buffer`メッセージング ブロックします。  
  
```  
virtual bool reserve_message(  
   runtime_object_identity                 _MsgId  
);  
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
  
##  <a name="send_message"></a>send_message 

 メッセージを同期的に渡す、`ISource`このブロック`unbounded_buffer`メッセージング ブロックします。 によって呼び出される、`send`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```  
virtual message_status send_message(  
   _Inout_ message<_Type> *                 _PMessage,  
   _Inout_ ISource<_Type> *                 _PSource  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md#message_status)の関係を決定するターゲットを示す値。  
  
##  <a name="supports_anonymous_source"></a>supports_anonymous_source 

 上書き、`supports_anonymous_source`を示すこのブロックがリンクされていないソースによって提供されたメッセージを受け取ることができます。  
  
```  
virtual bool supports_anonymous_source();  
```  
  
### <a name="return-value"></a>戻り値  
 `true`ブロックは延期しないために、メッセージを提供します。  
  
##  <a name="ctor"></a>unbounded_buffer 

 構築、`unbounded_buffer`メッセージング ブロックします。  
  
```  
unbounded_buffer();  
  
unbounded_buffer(  
   filter_method const&                 _Filter  
);  
  
unbounded_buffer(  
   Scheduler&                 _PScheduler  
);  
  
unbounded_buffer(  
   Scheduler&                 _PScheduler,  
   filter_method const&                 _Filter  
);  
  
unbounded_buffer(  
   ScheduleGroup&                 _PScheduleGroup  
);  
  
unbounded_buffer(  
   ScheduleGroup&                 _PScheduleGroup,  
   filter_method const&                 _Filter  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Filter`  
 提供されたメッセージを受け入れられる必要があるかどうかを決定するフィルター関数。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `unbounded_buffer` オブジェクト。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `unbounded_buffer` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="remarks"></a>コメント  
 `_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。  
  
 種類`filter_method`シグネチャを持つファンクターは、`bool (_Type const &)`によりが呼び出される、`unbounded_buffer`メッセージング ブロックを提供されたメッセージを受け入れる必要があるかどうかを判断します。  
  
##  <a name="dtor"></a>~ unbounded_buffer 

 破棄、`unbounded_buffer`メッセージング ブロックします。  
  
```  
~unbounded_buffer();  
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [overwrite_buffer クラス](overwrite-buffer-class.md)   
 [single_assignment クラス](single-assignment-class.md)



