---
title: "overwrite_buffer クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::overwrite_buffer
dev_langs:
- C++
helpviewer_keywords:
- overwrite_buffer class
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
caps.latest.revision: 22
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
ms.openlocfilehash: 02a4968ef88d8a6181a4d5412f894dce100ba7b3
ms.lasthandoff: 02/24/2017

---
# <a name="overwritebuffer-class"></a>overwrite_buffer クラス
`overwrite_buffer` メッセージング ブロックは、一度に&1; つのメッセージを格納することができる、複数のターゲットと複数のソースを持つ順序付けられた `propagator_block` です。 新しいメッセージが与えられると、それまで格納されていたメッセージは上書きされます。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 メッセージのペイロードの種類が格納され、バッファーによって反映されます。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[overwrite_buffer コンス トラクター](#ctor)|オーバーロードされます。 構築、`overwrite_buffer`メッセージング ブロックします。|  
|[~ overwrite_buffer デストラクター](#dtor)|破棄、`overwrite_buffer`メッセージング ブロックします。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[has_value メソッド](#has_value)|チェックするかどうかこの`overwrite_buffer`メッセージング ブロックはまだ値。|  
|[メソッドの値](#value)|格納されているメッセージの現在のペイロードへの参照を取得、`overwrite_buffer`メッセージング ブロックします。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept_message メソッド](#accept_message)|これによって提供されたメッセージを受け入れ`overwrite_buffer`メッセージング ブロック、呼び出し元に、メッセージのコピーを取得します。|  
|[consume_message メソッド](#consume_message)|によって以前に提供メッセージを使用して、`overwrite_buffer`メッセージング ブロックし、呼び出し元に、メッセージのコピーを返す、ターゲットによって予約されています。|  
|[link_target_notification メソッド](#link_target_notification)|新しいターゲットがこれにリンクされていることを通知するコールバック`overwrite_buffer`メッセージング ブロックします。|  
|[propagate_message メソッド](#propagate_message)|メッセージを非同期的に渡す、`ISource`このブロック`overwrite_buffer`メッセージング ブロックします。 によって呼び出される、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[propagate_to_any_targets メソッド](#propagate_to_any_targets)|場所、`message``_PMessage`この`overwrite_buffer`ブロックのメッセージングおよびすべてのリンクのターゲットに提供しています。|  
|[release_message メソッド](#release_message)|以前のメッセージの予約を解放します。 (上書き[source_block::release_message](source-block-class.md#release_message))。|  
|[reserve_message メソッド](#reserve_message)|これによって以前に提供メッセージを予約`overwrite_buffer`メッセージング ブロックします。 (上書き[source_block::reserve_message](source-block-class.md#reserve_message))。|  
|[resume_propagation メソッド](#resume_propagation)|伝達は、予約が解放された後に再開します。 (上書き[source_block::resume_propagation](source-block-class.md#resume_propagation))。|  
|[send_message メソッド](#send_message)|メッセージを同期的に渡す、`ISource`このブロック`overwrite_buffer`メッセージング ブロックします。 によって呼び出される、`send`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[supports_anonymous_source メソッド](#supports_anonymous_source)|上書き、`supports_anonymous_source`を示すこのブロックがリンクされていないソースによって提供されたメッセージを受け取ることができます。 (上書き[itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source))。|  
  
## <a name="remarks"></a>コメント  
 `overwrite_buffer`メッセージング ブロックは、ターゲットのそれぞれに、格納されているメッセージのコピーを伝達します。  
  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `overwrite_buffer`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-nameacceptmessagea-acceptmessage"></a><a name="accept_message"></a>accept_message 

 これによって提供されたメッセージを受け入れ`overwrite_buffer`メッセージング ブロック、呼び出し元に、メッセージのコピーを取得します。  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`オブジェクトの呼び出し元が今すぐの所有権を持っています。  
  
### <a name="remarks"></a>コメント  
 `overwrite_buffer`現在保持しているメッセージの所有権を譲渡するのではなく、メッセージング ブロックのターゲットにメッセージのコピーを返します。  
  
##  <a name="a-nameconsumemessagea-consumemessage"></a><a name="consume_message"></a>consume_message 

 によって以前に提供メッセージを使用して、`overwrite_buffer`メッセージング ブロックし、呼び出し元に、メッセージのコピーを返す、ターゲットによって予約されています。  
  
```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`読み取り中のオブジェクトします。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`オブジェクトの呼び出し元が今すぐの所有権を持っています。  
  
### <a name="remarks"></a>コメント  
 ような`accept`への呼び出し前に必ず、`reserve`です。  
  
##  <a name="a-namehasvaluea-hasvalue"></a><a name="has_value"></a>has_value 

 チェックするかどうかこの`overwrite_buffer`メッセージング ブロックはまだ値。  
  
```
bool has_value() const;
```  
  
### <a name="return-value"></a>戻り値  
 `true`ブロックは、値を受け取っている場合`false`それ以外の場合。  
  
##  <a name="a-namelinktargetnotificationa-linktargetnotification"></a><a name="link_target_notification"></a>link_target_notification 

 新しいターゲットがこれにリンクされていることを通知するコールバック`overwrite_buffer`メッセージング ブロックします。  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 新しくリンクされたターゲットへのポインター。  
  
##  <a name="a-namedtora-overwritebuffer"></a><a name="dtor"></a>~ overwrite_buffer 

 破棄、`overwrite_buffer`メッセージング ブロックします。  
  
```
~overwrite_buffer();
```  
  
##  <a name="a-namectora-overwritebuffer"></a><a name="ctor"></a>overwrite_buffer 

 構築、`overwrite_buffer`メッセージング ブロックします。  
  
```
overwrite_buffer();

overwrite_buffer(
    filter_method const& _Filter);

overwrite_buffer(
    Scheduler& _PScheduler);

overwrite_buffer(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Filter`  
 提供されたメッセージを受け入れられる必要があるかどうかを決定するフィルター関数。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `overwrite_buffer` オブジェクト。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `overwrite_buffer` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="remarks"></a>コメント  
 `_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。  
  
 種類`filter_method`シグネチャを持つファンクターは、`bool (T const &)`によりが呼び出される、`overwrite_buffer`メッセージング ブロックを提供されたメッセージを受け入れる必要があるかどうかを判断します。  
  
##  <a name="a-namepropagatemessagea-propagatemessage"></a><a name="propagate_message"></a>propagate_message 

 メッセージを非同期的に渡す、`ISource`このブロック`overwrite_buffer`メッセージング ブロックします。 によって呼び出される、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```
virtual message_status propagate_message(
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
  
##  <a name="a-namepropagatetoanytargetsa-propagatetoanytargets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 場所、`message``_PMessage`この`overwrite_buffer`ブロックのメッセージングおよびすべてのリンクのターゲットに提供しています。  
  
```
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 ポインター、`message`オブジェクトがこの`overwrite_buffer`の所有権を取得します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、現在のメッセージを上書き、`overwrite_buffer`新しく承認済みのメッセージと共に`_PMessage`します。  
  
##  <a name="a-namesendmessagea-sendmessage"></a><a name="send_message"></a>send_message 

 メッセージを同期的に渡す、`ISource`このブロック`overwrite_buffer`メッセージング ブロックします。 によって呼び出される、`send`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```
virtual message_status send_message(
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
  
##  <a name="a-namesupportsanonymoussourcea-supportsanonymoussource"></a><a name="supports_anonymous_source"></a>supports_anonymous_source 

 上書き、`supports_anonymous_source`を示すこのブロックがリンクされていないソースによって提供されたメッセージを受け取ることができます。  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>戻り値  
 `true`ブロックは延期しないために、メッセージを提供します。  
  
##  <a name="a-namereleasemessagea-releasemessage"></a><a name="release_message"></a>release_message 

 以前のメッセージの予約を解放します。  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`リリースされているオブジェクトします。  
  
##  <a name="a-namereservemessagea-reservemessage"></a><a name="reserve_message"></a>reserve_message 

 これによって以前に提供メッセージを予約`overwrite_buffer`メッセージング ブロックします。  
  
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
  
##  <a name="a-nameresumepropagationa-resumepropagation"></a><a name="resume_propagation"></a>resume_propagation 

 伝達は、予約が解放された後に再開します。  
  
```
virtual void resume_propagation();
```  
  
##  <a name="a-namevaluea-value"></a><a name="value"></a>値 

 格納されているメッセージの現在のペイロードへの参照を取得、`overwrite_buffer`メッセージング ブロックします。  
  
```
T value();
```  
  
### <a name="return-value"></a>戻り値  
 現在格納されているメッセージのペイロード。  
  
### <a name="remarks"></a>コメント  
 格納された値、`overwrite_buffer`このメソッドが戻る後すぐに変更する可能性があります。 このメソッドは、メッセージが現在格納されていない場合、メッセージが到着するまで待機は、`overwrite_buffer`です。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [unbounded_buffer クラス](unbounded-buffer-class.md)   
 [single_assignment クラス](single-assignment-class.md)

