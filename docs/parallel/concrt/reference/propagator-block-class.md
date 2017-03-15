---
title: "propagator_block クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::propagator_block
dev_langs:
- C++
helpviewer_keywords:
- propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: b53577fc187d699f50b4095518e9bc3562dcc7f3
ms.lasthandoff: 02/24/2017

---
# <a name="propagatorblock-class"></a>propagator_block クラス
`propagator_block` クラスは、ソースでもありターゲットでもあるメッセージ ブロックの抽象基底クラスです。 `source_block` クラスと `target_block` クラスの両方の機能が組み合わされています。  
  
## <a name="syntax"></a>構文  
  
```
template<class _TargetLinkRegistry, class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class propagator_block : public source_block<_TargetLinkRegistry,
    _MessageProcessorType>,
 public ITarget<typename _SourceLinkRegistry::type::source_type>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `_TargetLinkRegistry`  
 ターゲット リンクの保持に使用されるリンク レジストリ。  
  
 `_SourceLinkRegistry`  
 送信元のリンクの保持に使用されるリンク レジストリ。  
  
 `_MessageProcessorType`  
 メッセージ処理のプロセッサの種類。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`source_iterator`|反復子の型、`source_link_manager`この`propagator_block`します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[propagator_block コンス トラクター](#ctor)|`propagator_block` オブジェクトを構築します。|  
|[~ propagator_block デストラクター](#dtor)|`propagator_block` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[propagate メソッド](#propagate)|このターゲット ブロックに、ソース ブロックからメッセージを非同期的に渡します。|  
|[send メソッド](#send)|このブロックにメッセージを同期的に開始します。 によって呼び出される、`ISource`ブロックします。 この関数が完了したら、メッセージは既にブロックに伝達が。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[decline_incoming_messages メソッド](#decline_incoming_messages)|ブロックに新しいメッセージを拒否することを示します。|  
|[initialize_source_and_target メソッド](#initialize_source_and_target)|ベース オブジェクトを初期化します。 具体的には、`message_processor`オブジェクトを初期化する必要があります。|  
|[link_source メソッド](#link_source)|これに指定されたソース ブロックをリンク`propagator_block`オブジェクトです。|  
|[process_input_messages メソッド](#process_input_messages)|入力メッセージを処理します。 これは、伝達子ブロック source_block から派生するのに便利です (オーバーライド[source_block::process_input_messages](source-block-class.md#process_input_messages))。|  
|[propagate_message メソッド](#propagate_message)|派生クラスでオーバーライドされると、このメソッドは非同期的に渡しますからのメッセージ、`ISource`このブロック`propagator_block`オブジェクトです。 によって呼び出される、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[register_filter メソッド](#register_filter)|すべての受信メッセージで呼び出されるフィルター メソッドを登録します。|  
|[remove_network_links メソッド](#remove_network_links)|これからのすべてのソースとターゲット ネットワーク リンクの削除`propagator_block`オブジェクトです。|  
|[send_message メソッド](#send_message)|このメソッドがからのメッセージを同期的には派生クラスでオーバーライドされると、`ISource`このブロック`propagator_block`オブジェクトです。 によって呼び出される、`send`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[unlink_source メソッド](#unlink_source)|これから指定されたソース ブロックのリンクを解除`propagator_block`オブジェクトです。|  
|[unlink_sources メソッド](#unlink_sources)|これからのすべてのソース ブロックのリンクを解除`propagator_block`オブジェクトです。 (上書き[itarget::unlink_sources](itarget-class.md#unlink_sources))。|  
  
## <a name="remarks"></a>コメント  
 多重継承を避けるために、`propagator_block`クラスから継承、`source_block`クラスと`ITarget`抽象クラスです。 機能のほとんどの`target_block`クラスがここでレプリケートします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 `propagator_block`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namedeclineincomingmessagesa-declineincomingmessages"></a><a name="decline_incoming_messages"></a>decline_incoming_messages 

 ブロックに新しいメッセージを拒否することを示します。  
  
```
void decline_incoming_messages();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、破棄が進行中は、新しいメッセージが却下されたことを確認するデストラクターが呼び出されます。  
  
##  <a name="a-nameinitializesourceandtargeta-initializesourceandtarget"></a><a name="initialize_source_and_target"></a>initialize_source_and_target 

 ベース オブジェクトを初期化します。 具体的には、`message_processor`オブジェクトを初期化する必要があります。  
  
```
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PScheduler`  
 タスクのスケジュール設定に使用するスケジューラー。  
  
 `_PScheduleGroup`  
 タスクのスケジューリングに使用するスケジュール グループです。  
  
##  <a name="a-namelinksourcea-linksource"></a><a name="link_source"></a>link_source 

 これに指定されたソース ブロックをリンク`propagator_block`オブジェクトです。  
  
```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PSource`  
 ポインター、`ISource`をリンクできるはブロックされます。  
  
##  <a name="a-nameprocessinputmessagesa-processinputmessages"></a><a name="process_input_messages"></a>process_input_messages 

 入力メッセージを処理します。 これは、伝達子ブロック source_block から派生するのに便利です。  
  
```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
  
##  <a name="a-namepropagatea-propagate"></a><a name="propagate"></a>伝達 

 このターゲット ブロックに、ソース ブロックからメッセージを非同期的に渡します。  
  
```
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)の関係を決定するターゲットを示す値。  
  
### <a name="remarks"></a>コメント  
 `propagate`リンクのソース ブロックからのターゲット ブロックにメソッドが呼び出されます。 1 つは、既にキューにない場合、メッセージを処理する非同期タスクまたは実行をキューに入れます。  
  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターは`NULL`です。  
  
##  <a name="a-namepropagatemessagea-propagatemessage"></a><a name="propagate_message"></a>propagate_message 

 派生クラスでオーバーライドされると、このメソッドは非同期的に渡しますからのメッセージ、`ISource`このブロック`propagator_block`オブジェクトです。 によって呼び出される、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)の関係を決定するターゲットを示す値。  
  
##  <a name="a-namectora-propagatorblock"></a><a name="ctor"></a>propagator_block 

 `propagator_block` オブジェクトを構築します。  
  
```
propagator_block();
```  
  
##  <a name="a-namedtora-propagatorblock"></a><a name="dtor"></a>~ propagator_block 

 `propagator_block` オブジェクトを破棄します。  
  
```
virtual ~propagator_block();
```  
  
##  <a name="a-nameregisterfiltera-registerfilter"></a><a name="register_filter"></a>register_filter 

 すべての受信メッセージで呼び出されるフィルター メソッドを登録します。  
  
```
void register_filter(filter_method const& _Filter);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Filter`  
 Filter メソッドです。  
  
##  <a name="a-nameremovenetworklinksa-removenetworklinks"></a><a name="remove_network_links"></a>remove_network_links 

 これからのすべてのソースとターゲット ネットワーク リンクの削除`propagator_block`オブジェクトです。  
  
```
void remove_network_links();
```  
  
##  <a name="a-namesenda-send"></a><a name="send"></a>送信 

 このブロックにメッセージを同期的に開始します。 によって呼び出される、`ISource`ブロックします。 この関数が完了したら、メッセージは既にブロックに伝達が。  
  
```
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)の関係を決定するターゲットを示す値。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターは`NULL`です。  
  
##  <a name="a-namesendmessagea-sendmessage"></a><a name="send_message"></a>send_message 

 このメソッドがからのメッセージを同期的には派生クラスでオーバーライドされると、`ISource`このブロック`propagator_block`オブジェクトです。 によって呼び出される、`send`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)の関係を決定するターゲットを示す値。  
  
### <a name="remarks"></a>コメント  
 既定では、このブロックが返す`declined`派生クラスによってオーバーライドされない限りです。  
  
##  <a name="a-nameunlinksourcea-unlinksource"></a><a name="unlink_source"></a>unlink_source 

 これから指定されたソース ブロックのリンクを解除`propagator_block`オブジェクトです。  
  
```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PSource`  
 ポインター、`ISource`リンクを解除するのには、ブロックします。  
  
##  <a name="a-nameunlinksourcesa-unlinksources"></a><a name="unlink_sources"></a>unlink_sources 

 これからのすべてのソース ブロックのリンクを解除`propagator_block`オブジェクトです。  
  
```
virtual void unlink_sources();
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [source_block クラス](source-block-class.md)   
 [ITarget クラス](itarget-class.md)

