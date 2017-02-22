---
title: "multitype_join クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::multitype_join"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multitype_join クラス"
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# multitype_join クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`multitype_join` メッセージング ブロックは、複数のソースと単一のターゲットを持つメッセージング ブロックで、それぞれのソースから受け取った異なる種類のメッセージを 1 つに結合してターゲットに渡します。  
  
## <a name="syntax"></a>構文  
  
```  
template<
    typename T,  
    join_type _Jtype = non_greedy  
>  
class multitype_join: public ISource<typename _Unwrap<T>::type>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
  `tuple` メッセージのペイロードの種類が結合され、ブロックによって反映されます。  
  
 `_Jtype`  
 種類の `join` ブロックか、これは `greedy` または `non_greedy`  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`type`|型の別名 `T`します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[multitype_join::multitype_join コンス トラクター](#multitype_join__multitype_join_constructor)|オーバーロードされます。 `multitype_join` メッセージング ブロックを構築します。|  
|[multitype_join:: ~ multitype_join デストラクター](#multitype_join___dtormultitype_join_destructor)|破棄、 `multitype_join` メッセージング ブロックします。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[multitype_join::accept メソッド](#multitype_join__accept_method)|これによって提供されたメッセージを受け入れ `multitype_join` ブロック、呼び出し元に所有権を移譲します。|  
|[multitype_join::acquire_ref メソッド](#multitype_join__acquire_ref_method)|この参照カウントを取得し `multitype_join` メッセージング ブロックは、削除を禁止します。|  
|[multitype_join::consume メソッド](#multitype_join__consume_method)|によって以前に提供メッセージを使用して、 `multitype_join` メッセージング ブロックし、所有権を呼び出し元に移動するターゲットが正常に予約されています。|  
|[multitype_join::link_target メソッド](#multitype_join__link_target_method)|これにターゲット ブロックをリンク `multitype_join` メッセージング ブロックします。|  
|[multitype_join::release メソッド](#multitype_join__release_method)|以前に成功したメッセージの予約を解放します。|  
|[multitype_join::release_ref メソッド](#multitype_join__release_ref_method)|この参照カウントを解放 `multiple_join` メッセージング ブロックします。|  
|[multitype_join::reserve メソッド](#multitype_join__reserve_method)|これによって以前に提供メッセージを予約 `multitype_join` メッセージング ブロックします。|  
|[multitype_join::unlink_target メソッド](#multitype_join__unlink_target_method)|これから、ターゲット ブロックのリンクを解除 `multitype_join` メッセージング ブロックします。|  
|[multitype_join::unlink_targets メソッド](#multitype_join__unlink_targets_method)|これからすべてのターゲットのリンクを解除 `multitype_join` メッセージング ブロックします。 (上書き [Isource::unlink_targets](../../../parallel/concrt/reference/isource-class.md#isource__unlink_targets_method).)|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 `multitype_join`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namemultitypejoinacceptmethoda-multitypejoinaccept-method"></a><a name="multitype_join__accept_method"></a>  multitype_join::accept メソッド  
 これによって提供されたメッセージを受け入れ `multitype_join` ブロック、呼び出し元に所有権を移譲します。  
  
```  
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
  `runtime_object_identity` 、提供されているの `message` オブジェクトです。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、 `accept` メソッドです。  
  
### <a name="return-value"></a>戻り値  
 所有権が呼び出し元は、メッセージへのポインター。  
  
##  <a name="a-namemultitypejoinacquirerefmethoda-multitypejoinacquireref-method"></a><a name="multitype_join__acquire_ref_method"></a>  multitype_join::acquire_ref メソッド  
 この参照カウントを取得し `multitype_join` メッセージング ブロックは、削除を禁止します。  
  
```  
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出して、ターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、 `ITarget` 中にこのソースにリンクされているオブジェクト、 `link_target` メソッドです。  
  
##  <a name="a-namemultitypejoinconsumemethoda-multitypejoinconsume-method"></a><a name="multitype_join__consume_method"></a>  multitype_join::consume メソッド  
 によって以前に提供メッセージを使用して、 `multitype_join` メッセージング ブロックし、所有権を呼び出し元に移動するターゲットが正常に予約されています。  
  
```  
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
  `runtime_object_identity` 、予約済みの `message` オブジェクトです。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、 `consume` メソッドです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 `message` オブジェクトの呼び出し元が今すぐの所有権を持っています。  
  
### <a name="remarks"></a>コメント  
  `consume` メソッドは `accept`, への呼び出しで前に必ず必要がありますが、 `reserve` 返さ `true`します。  
  
##  <a name="a-namemultitypejoinlinktargetmethoda-multitypejoinlinktarget-method"></a><a name="multitype_join__link_target_method"></a>  multitype_join::link_target メソッド  
 これにターゲット ブロックをリンク `multitype_join` メッセージング ブロックします。  
  
```  
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、 `ITarget` リンク先のブロック `multitype_join` メッセージング ブロックします。  
  
##  <a name="a-namemultitypejoinmultitypejoinconstructora-multitypejoinmultitypejoin-constructor"></a><a name="multitype_join__multitype_join_constructor"></a>  multitype_join::multitype_join コンス トラクター  
 `multitype_join` メッセージング ブロックを構築します。  
  
```  
explicit multitype_join(
    T _Tuple);

 
multitype_join(
    Scheduler& _PScheduler,  
    T _Tuple);

 
multitype_join(
    ScheduleGroup& _PScheduleGroup,  
    T _Tuple);

 
multitype_join(
    multitype_join&& _Join);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Tuple`  
 この `tuple` メッセージング ブロックのソースの `multitype_join` です。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
 `_Join`  
 コピー元の `multitype_join` メッセージング ブロックです。 元のオブジェクトが孤立しており、これが移動コンストラクターになることに注意してください。  
  
### <a name="remarks"></a>コメント  
 `_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。  
  
 移動の構築はロックの状況では行われません。ということは、移動時に処理中の軽量タスクがないことを確認するのはユーザーの責任です。 そうしないと、例外または不整合な状態で、多数の競合が発生します。  
  
##  <a name="a-namemultitypejoindtormultitypejoindestructora-multitypejoinmultitypejoin-destructor"></a><a name="multitype_join___dtormultitype_join_destructor"></a>  multitype_join:: ~ multitype_join デストラクター  
 破棄、 `multitype_join` メッセージング ブロックします。  
  
```  
~multitype_join();
```  
  
##  <a name="a-namemultitypejoinreleasemethoda-multitypejoinrelease-method"></a><a name="multitype_join__release_method"></a>  multitype_join::release メソッド  
 以前に成功したメッセージの予約を解放します。  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
  `runtime_object_identity` の `message` リリースされているオブジェクトします。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、 `release` メソッドです。  
  
##  <a name="a-namemultitypejoinreleaserefmethoda-multitypejoinreleaseref-method"></a><a name="multitype_join__release_ref_method"></a>  multitype_join::release_ref メソッド  
 この参照カウントを解放 `multiple_join` メッセージング ブロックします。  
  
```  
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出して、ターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、 `ITarget` このソースからリンクが解除されるオブジェクト。 ターゲット ブロック用に予約されたリソースを解放できるは、ソース ブロックです。  
  
##  <a name="a-namemultitypejoinreservemethoda-multitypejoinreserve-method"></a><a name="multitype_join__reserve_method"></a>  multitype_join::reserve メソッド  
 これによって以前に提供メッセージを予約 `multitype_join` メッセージング ブロックします。  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
  `runtime_object_identity` の `message` 予約されているオブジェクトします。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、 `reserve` メソッドです。  
  
### <a name="return-value"></a>戻り値  
 `true` 場合は、メッセージが正常に予約された、 `false` それ以外の場合。 予約はエラーになるなど、さまざまな理由: メッセージが既にに予約されているまたはソースが、予約を拒否し、など、別のターゲットで受け入れられます。  
  
### <a name="remarks"></a>コメント  
 呼び出した後 `reserve`, 、成功した場合、いずれかを呼び出す必要があります `consume` または `release` かかるまたはそれぞれのメッセージを所有しているを断念するためにします。  
  
##  <a name="a-namemultitypejoinunlinktargetmethoda-multitypejoinunlinktarget-method"></a><a name="multitype_join__unlink_target_method"></a>  multitype_join::unlink_target メソッド  
 これから、ターゲット ブロックのリンクを解除 `multitype_join` メッセージング ブロックします。  
  
```  
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、 `ITarget` このリンクを解除するブロック `multitype_join` メッセージング ブロックします。  
  
##  <a name="a-namemultitypejoinunlinktargetsmethoda-multitypejoinunlinktargets-method"></a><a name="multitype_join__unlink_targets_method"></a>  multitype_join::unlink_targets メソッド  
 これからすべてのターゲットのリンクを解除 `multitype_join` メッセージング ブロックします。  
  
```  
virtual void unlink_targets();
```  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [choice クラス](../../../parallel/concrt/reference/choice-class.md)   
 [クラスを結合します。](../Topic/join%20Class.md)
