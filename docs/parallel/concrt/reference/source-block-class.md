---
title: "source_block クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::source_block
dev_langs:
- C++
helpviewer_keywords:
- source_block class
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
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
ms.openlocfilehash: 7d459d03153e95b779b8f8b19d2a68602b33acf8
ms.lasthandoff: 02/24/2017

---
# <a name="sourceblock-class"></a>source_block クラス
`source_block` クラスは、ソースのみのブロックの抽象基底クラスです。 このクラスには、基本的なリンク管理機能および一般的なエラー チェック機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```
template<class _TargetLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `_TargetLinkRegistry`  
 ターゲット リンクの保持に使用するレジストリをリンクします。  
  
 `_MessageProcessorType`  
 メッセージ処理のプロセッサの種類。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`target_iterator`|接続されているターゲットを参照する反復子。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[source_block コンス トラクター](#ctor)|`source_block` オブジェクトを構築します。|  
|[~ source_block デストラクター](#dtor)|`source_block` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept メソッド](#accept)|これによって提供されたメッセージを受け入れ`source_block`所有権を呼び出し元に移動するオブジェクト。|  
|[acquire_ref メソッド](#acquire_ref)|この参照カウントを取得し`source_block`オブジェクトが削除されないようにします。|  
|[consume メソッド](#consume)|これによって以前に提供メッセージを使用して`source_block`オブジェクトし、呼び出し側に所有権を移動するターゲットが正常に予約します。|  
|[link_target メソッド](#link_target)|これにターゲット ブロックをリンク`source_block`オブジェクトです。|  
|[release メソッド](#release)|以前に成功したメッセージの予約を解放します。|  
|[release_ref メソッド](#release_ref)|この参照カウントを解放`source_block`オブジェクトです。|  
|[reserve メソッド](#reserve)|これによって以前に提供メッセージを予約`source_block`オブジェクトです。|  
|[unlink_target メソッド](#unlink_target)|これから、ターゲット ブロックのリンクを解除`source_block`オブジェクトです。|  
|[unlink_targets メソッド](#unlink_targets)|これからのすべてのターゲット ブロックのリンクを解除`source_block`オブジェクトです。 (上書き[isource::unlink_targets](isource-class.md#unlink_targets))。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept_message メソッド](#accept_message)|派生クラスでオーバーライドされると、ソースによって提供されたメッセージを受け入れます。 メッセージ ブロックは、検証するには、このメソッドをオーバーライドする必要があります、`_MsgId`メッセージが返されます。|  
|[async_send メソッド](#async_send)|非同期的にメッセージをキューに配置しがまだ実行されている場合、伝達のタスクを開始|  
|[consume_message メソッド](#consume_message)|派生クラスでオーバーライドされた場合は、以前に予約されたメッセージを消費します。|  
|[enable_batched_processing メソッド](#enable_batched_processing)|有効では、このブロックの処理をバッチ処理されます。|  
|[initialize_source メソッド](#initialize_source)|初期化、`message_propagator`この`source_block`します。|  
|[link_target_notification メソッド](#link_target_notification)|新しいターゲットがこれにリンクされていることを通知するコールバック`source_block`オブジェクトです。|  
|[process_input_messages メソッド](#process_input_messages)|入力メッセージを処理します。 これは、伝達子ブロック source_block から派生するのに便利です。|  
|[propagate_output_messages メソッド](#propagate_output_messages)|ターゲットにメッセージを伝達します。|  
|[propagate_to_any_targets メソッド](#propagate_to_any_targets)|派生クラスでオーバーライドされた場合は、一部またはすべてのリンクのターゲットに指定したメッセージを伝達します。 これは、メッセージ ブロックの主要な伝達ルーチンです。|  
|[release_message メソッド](#release_message)|派生クラスでオーバーライドされた場合は、以前のメッセージの予約を解放します。|  
|[remove_targets メソッド](#remove_targets)|このソース ブロックのすべての送信先のリンクを削除します。 これは、デストラクターから呼び出される必要があります。|  
|[reserve_message メソッド](#reserve_message)|派生クラスでオーバーライドされた場合は、これによって以前に提供メッセージを予約`source_block`オブジェクトです。|  
|[resume_propagation メソッド](#resume_propagation)|派生クラスでオーバーライドされると、予約が解放された後に、伝達を再開します。|  
|[sync_send メソッド](#sync_send)|同期的にメッセージをキューに登録しがまだ実行されている場合は、伝達のタスクを開始します。|  
|[unlink_target_notification メソッド](#unlink_target_notification)|ターゲットがこれからリンクされていることを通知するコールバック`source_block`オブジェクトです。|  
|[wait_for_outstanding_async_sends メソッド](#wait_for_outstanding_async_sends)|すべての非同期伝達が完了するまで待機します。 この伝達子に固有のスピン待機は、すべての非同期伝達にブロックを破棄する前に完了するのに時間があることを確認するメッセージ ブロックのデストラクターで使用されます。|  
  
## <a name="remarks"></a>コメント  
 メッセージ ブロックは、リンクの管理とこのクラスによって提供される同期を活用するには、このブロックから派生する必要があります。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](isource-class.md)  
  
 `source_block`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-nameaccepta-accept"></a><a name="accept"></a>そのまま使用します。 

 これによって提供されたメッセージを受け入れ`source_block`所有権を呼び出し元に移動するオブジェクト。  
  
```
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクトです。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`accept`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`オブジェクトの呼び出し元が今すぐの所有権を持っています。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合、パラメーター`_PTarget`は`NULL`です。  
  
 `accept`メソッドは、メッセージは、これによって提供されているときに、ターゲットによって呼び出されます。`ISource`ブロックします。 返されるメッセージ ポインターに渡されたものと異なる場合があります、`propagate`のメソッド、`ITarget`ブロック、メッセージのコピーを作成してこのソースと判断した場合。  
  
##  <a name="a-nameacceptmessagea-acceptmessage"></a><a name="accept_message"></a>accept_message 

 派生クラスでオーバーライドされると、ソースによって提供されたメッセージを受け入れます。 メッセージ ブロックは、検証するには、このメソッドをオーバーライドする必要があります、`_MsgId`メッセージが返されます。  
  
```
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 ランタイム オブジェクトの id、`message`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 所有権が呼び出し元は、メッセージへのポインター。  
  
### <a name="remarks"></a>コメント  
 所有権を転送するには、元のメッセージ ポインターを返す必要があります。 所有権を維持するためにメッセージ ペイロードのコピーが作成され、返される必要があります。  
  
##  <a name="a-nameacquirerefa-acquireref"></a><a name="acquire_ref"></a>acquire_ref 

 この参照カウントを取得し`source_block`オブジェクトが削除されないようにします。  
  
```
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`中にこのソースにリンクされているオブジェクト、`link_target`メソッドです。  
  
##  <a name="a-nameasyncsenda-asyncsend"></a><a name="async_send"></a>async_send 

 非同期的にメッセージをキューに配置しがまだ実行されている場合、伝達のタスクを開始  
  
```
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Msg`  
 ポインター、`message`オブジェクトを非同期的に送信します。  
  
##  <a name="a-nameconsumea-consume"></a><a name="consume"></a>使用します。 

 これによって以前に提供メッセージを使用して`source_block`オブジェクトし、呼び出し側に所有権を移動するターゲットが正常に予約します。  
  
```
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、予約済みの`message`オブジェクトです。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`consume`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`オブジェクトの呼び出し元が今すぐの所有権を持っています。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合、パラメーター`_PTarget`は`NULL`です。  
  
 メソッドをスロー、 [bad_target](bad-target-class.md)例外場合、パラメーター`_PTarget`と呼ばれる対象を表さない`reserve`します。  
  
 `consume`メソッドは`accept`への呼び出しで前に必ず必要がありますが、`reserve`返さ`true`します。  
  
##  <a name="a-nameconsumemessagea-consumemessage"></a><a name="consume_message"></a>consume_message 

 派生クラスでオーバーライドされた場合は、以前に予約されたメッセージを消費します。  
  
```
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`オブジェクトの読み取り中です。  
  
### <a name="return-value"></a>戻り値  
 所有権が呼び出し元は、メッセージへのポインター。  
  
### <a name="remarks"></a>コメント  
 ような`accept`への呼び出し前に必ず、`reserve`です。  
  
##  <a name="a-nameenablebatchedprocessinga-enablebatchedprocessing"></a><a name="enable_batched_processing"></a>enable_batched_processing 

 有効では、このブロックの処理をバッチ処理されます。  
  
```
void enable_batched_processing();
```  
  
##  <a name="a-nameinitializesourcea-initializesource"></a><a name="initialize_source"></a>initialize_source 

 初期化、`message_propagator`この`source_block`します。  
  
```
void initialize_source(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PScheduler`  
 タスクのスケジュール設定に使用するスケジューラー。  
  
 `_PScheduleGroup`  
 タスクのスケジューリングに使用するスケジュール グループです。  
  
##  <a name="a-namelinktargeta-linktarget"></a><a name="link_target"></a>link_target 

 これにターゲット ブロックをリンク`source_block`オブジェクトです。  
  
```
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、`ITarget`リンク先のブロック`source_block`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合、パラメーター`_PTarget`は`NULL`です。  
  
##  <a name="a-namelinktargetnotificationa-linktargetnotification"></a><a name="link_target_notification"></a>link_target_notification 

 新しいターゲットがこれにリンクされていることを通知するコールバック`source_block`オブジェクトです。  
  
```
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```  
  
##  <a name="a-nameprocessinputmessagesa-processinputmessages"></a><a name="process_input_messages"></a>process_input_messages 

 入力メッセージを処理します。 これは、伝達子ブロック source_block から派生するのに便利です。  
  
```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
  
##  <a name="a-namepropagateoutputmessagesa-propagateoutputmessages"></a><a name="propagate_output_messages"></a>propagate_output_messages 

 ターゲットにメッセージを伝達します。  
  
```
virtual void propagate_output_messages();
```  
  
##  <a name="a-namepropagatetoanytargetsa-propagatetoanytargets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 派生クラスでオーバーライドされた場合は、一部またはすべてのリンクのターゲットに指定したメッセージを伝達します。 これは、メッセージ ブロックの主要な伝達ルーチンです。  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 反映されるまで、そのメッセージへのポインター。  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>リリース 

 以前に成功したメッセージの予約を解放します。  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、予約済みの`message`オブジェクトです。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`release`メソッドです。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合、パラメーター`_PTarget`は`NULL`です。  
  
 メソッドをスロー、 [bad_target](bad-target-class.md)例外場合、パラメーター`_PTarget`と呼ばれる対象を表さない`reserve`します。  
  
##  <a name="a-namereleasemessagea-releasemessage"></a><a name="release_message"></a>release_message 

 派生クラスでオーバーライドされた場合は、以前のメッセージの予約を解放します。  
  
```
virtual void release_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`リリースされているオブジェクトします。  
  
##  <a name="a-namereleaserefa-releaseref"></a><a name="release_ref"></a>release_ref 

 この参照カウントを解放`source_block`オブジェクトです。  
  
```
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出して、ターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`このソースからリンクが解除されるオブジェクト。 ターゲット ブロック用に予約されたリソースを解放できるは、ソース ブロックです。  
  
##  <a name="a-nameremovetargetsa-removetargets"></a><a name="remove_targets"></a>remove_targets 

 このソース ブロックのすべての送信先のリンクを削除します。 これは、デストラクターから呼び出される必要があります。  
  
```
void remove_targets();
```  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>予約 

 これによって以前に提供メッセージを予約`source_block`オブジェクトです。  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクトです。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`reserve`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 `true`場合は、メッセージが正常に予約された、`false`それ以外の場合。 予約はエラーになるなど、さまざまな理由: メッセージが既にに予約されているまたはソースが、予約を拒否し、など、別のターゲットで受け入れられます。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合、パラメーター`_PTarget`は`NULL`です。  
  
 呼び出した後`reserve`、成功した場合、いずれかを呼び出す必要があります`consume`または`release`かかるまたはそれぞれのメッセージを所有しているを断念するためにします。  
  
##  <a name="a-namereservemessagea-reservemessage"></a><a name="reserve_message"></a>reserve_message 

 派生クラスでオーバーライドされた場合は、これによって以前に提供メッセージを予約`source_block`オブジェクトです。  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`予約されているオブジェクトします。  
  
### <a name="return-value"></a>戻り値  
 `true`場合は、メッセージが正常に予約された、`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 後に`reserve`と呼ばれる場合は、返された場合`true`か、`consume`または`release`か、実行するか、メッセージの所有権を解放呼び出す必要があります。  
  
##  <a name="a-nameresumepropagationa-resumepropagation"></a><a name="resume_propagation"></a>resume_propagation 

 派生クラスでオーバーライドされると、予約が解放された後に、伝達を再開します。  
  
```
virtual void resume_propagation() = 0;
```  
  
##  <a name="a-namectora-sourceblock"></a><a name="ctor"></a>source_block 

 `source_block` オブジェクトを構築します。  
  
```
source_block();
```  
  
##  <a name="a-namedtora-sourceblock"></a><a name="dtor"></a>~ source_block 

 `source_block` オブジェクトを破棄します。  
  
```
virtual ~source_block();
```  
  
##  <a name="a-namesyncsenda-syncsend"></a><a name="sync_send"></a>sync_send 

 同期的にメッセージをキューに登録しがまだ実行されている場合は、伝達のタスクを開始します。  
  
```
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Msg`  
 ポインター、`message`オブジェクトを同期的に送信します。  
  
##  <a name="a-nameunlinktargeta-unlinktarget"></a><a name="unlink_target"></a>unlink_target 

 これから、ターゲット ブロックのリンクを解除`source_block`オブジェクトです。  
  
```
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、`ITarget`このリンクを解除するブロック`source_block`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合、パラメーター`_PTarget`は`NULL`です。  
  
##  <a name="a-nameunlinktargetnotificationa-unlinktargetnotification"></a><a name="unlink_target_notification"></a>unlink_target_notification 

 ターゲットがこれからリンクされていることを通知するコールバック`source_block`オブジェクトです。  
  
```
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 `ITarget`リンクされたブロックします。  
  
##  <a name="a-nameunlinktargetsa-unlinktargets"></a><a name="unlink_targets"></a>unlink_targets 

 これからのすべてのターゲット ブロックのリンクを解除`source_block`オブジェクトです。  
  
```
virtual void unlink_targets();
```  
  
##  <a name="a-namewaitforoutstandingasyncsendsa-waitforoutstandingasyncsends"></a><a name="wait_for_outstanding_async_sends"></a>wait_for_outstanding_async_sends 

 すべての非同期伝達が完了するまで待機します。 この伝達子に固有のスピン待機は、すべての非同期伝達にブロックを破棄する前に完了するのに時間があることを確認するメッセージ ブロックのデストラクターで使用されます。  
  
```
void wait_for_outstanding_async_sends();
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [ISource クラス](isource-class.md)

