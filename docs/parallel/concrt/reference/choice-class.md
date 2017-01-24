---
title: "choice クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::choice"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "choice クラス"
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# choice クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`choice` メッセージング ブロックは、複数のソースと単一のターゲットを持つブロックであり、一連のソースとの制御フローの相互作用を表します。 choice ブロックは、複数のソースのいずれかがメッセージを生成するのを待ち、そのメッセージを生成したソースのインデックスを伝達します。  
  
## <a name="syntax"></a>構文  
  
```  
template<
    class T  
>  
class choice: public ISource<size_t>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 A `tuple`-ベースの入力ソースのペイロードを表す型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`type`|型の別名 `T`します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[choice::choice コンス トラクター](#choice__choice_constructor)|オーバーロードされます。 `choice` メッセージング ブロックを構築します。|  
|[choice:: ~ choice デストラクター](#choice___dtorchoice_destructor)|破棄、 `choice` メッセージング ブロックします。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[choice::accept メソッド](#choice__accept_method)|これによって提供されたメッセージを受け入れ `choice` ブロック、呼び出し元に所有権を移譲します。|  
|[choice::acquire_ref メソッド](#choice__acquire_ref_method)|この参照カウントを取得し `choice` メッセージング ブロックは、削除を禁止します。|  
|[choice::consume メソッド](#choice__consume_method)|これによって以前に提供メッセージを使用して `choice` メッセージング ブロックし、所有権を呼び出し元に移動するターゲットが正常に予約されています。|  
|[choice::has_value メソッド](#choice__has_value_method)|チェックするかどうかこの `choice` 値を持つメッセージング ブロックがまだに初期化します。|  
|[choice::index メソッド](#choice__index_method)|インデックスを返す、 `tuple` によって選択された要素を表す、 `choice` メッセージング ブロックします。|  
|[choice::link_target メソッド](#choice__link_target_method)|これにターゲット ブロックをリンク `choice` メッセージング ブロックします。|  
|[choice::release メソッド](#choice__release_method)|以前に成功したメッセージの予約を解放します。|  
|[choice::release_ref メソッド](#choice__release_ref_method)|この参照カウントを解放 `choice` メッセージング ブロックします。|  
|[choice::reserve メソッド](#choice__reserve_method)|これによって以前に提供メッセージを予約 `choice` メッセージング ブロックします。|  
|[choice::unlink_target メソッド](#choice__unlink_target_method)|これから、ターゲット ブロックのリンクを解除 `choice` メッセージング ブロックします。|  
|[choice::unlink_targets メソッド](#choice__unlink_targets_method)|これからすべてのターゲットのリンクを解除 `choice` メッセージング ブロックします。 (上書き [Isource::unlink_targets](../../../parallel/concrt/reference/isource-class.md#isource__unlink_targets_method).)|  
|[choice::value メソッド](#choice__value_method)|によって選択されたインデックスを持つメッセージを取得、 `choice` メッセージング ブロックします。|  
  
## <a name="remarks"></a>コメント  
 Choice ブロックでは受信メッセージの 1 つだけが使用します。  
  
 詳細については、次を参照してください。 [非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 `choice`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namechoiceacceptmethoda-choiceaccept-method"></a><a name="choice__accept_method"></a>  choice::accept メソッド  
 これによって提供されたメッセージを受け入れ `choice` ブロック、呼び出し元に所有権を移譲します。  
  
```  
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
  `runtime_object_identity` 、提供されているの `message` オブジェクトです。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、 `accept` メソッドです。  
  
### <a name="return-value"></a>戻り値  
 所有権が呼び出し元は、メッセージへのポインター。  
  
##  <a name="a-namechoiceacquirerefmethoda-choiceacquireref-method"></a><a name="choice__acquire_ref_method"></a>  choice::acquire_ref メソッド  
 この参照カウントを取得し `choice` メッセージング ブロックは、削除を禁止します。  
  
```  
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出して、ターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、 `ITarget` 中にこのソースにリンクされているオブジェクト、 `link_target` メソッドです。  
  
##  <a name="a-namechoicechoiceconstructora-choicechoice-constructor"></a><a name="choice__choice_constructor"></a>  choice::choice コンス トラクター  
 `choice` メッセージング ブロックを構築します。  
  
```  
explicit choice(
    T _Tuple);

 
choice(
    Scheduler& _PScheduler,  
    T _Tuple);

 
choice(
    ScheduleGroup& _PScheduleGroup,  
    T _Tuple);

 
choice(
    choice&& _Choice);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Tuple`  
 選択肢のソースの `tuple` です。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `choice` オブジェクト。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `choice` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
 `_Choice`  
 コピー元の `choice` メッセージング ブロックです。 元のオブジェクトが孤立しており、これが移動コンストラクターになることに注意してください。  
  
### <a name="remarks"></a>コメント  
 `_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。  
  
 移動の構築はロックの状況では行われません。ということは、移動時に処理中の軽量タスクがないことを確認するのはユーザーの責任です。 そうしないと、例外または不整合な状態で、多数の競合が発生します。  
  
##  <a name="a-namechoicedtorchoicedestructora-choicechoice-destructor"></a><a name="choice___dtorchoice_destructor"></a>  choice:: ~ choice デストラクター  
 破棄、 `choice` メッセージング ブロックします。  
  
```  
~choice();
```  
  
##  <a name="a-namechoiceconsumemethoda-choiceconsume-method"></a><a name="choice__consume_method"></a>  choice::consume メソッド  
 これによって以前に提供メッセージを使用して `choice` メッセージング ブロックし、所有権を呼び出し元に移動するターゲットが正常に予約されています。  
  
```  
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
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
  
##  <a name="a-namechoicehasvaluemethoda-choicehasvalue-method"></a><a name="choice__has_value_method"></a>  choice::has_value メソッド  
 チェックするかどうかこの `choice` 値を持つメッセージング ブロックがまだに初期化します。  
  
```  
bool has_value() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 `true` ブロックは、値を受け取っている場合 `false` それ以外の場合。  
  
##  <a name="a-namechoiceindexmethoda-choiceindex-method"></a><a name="choice__index_method"></a>  choice::index メソッド  
 インデックスを返す、 `tuple` によって選択された要素を表す、 `choice` メッセージング ブロックします。  
  
```  
size_t index();
```  
  
### <a name="return-value"></a>戻り値  
 メッセージのインデックス。  
  
### <a name="remarks"></a>コメント  
 使用して、メッセージ ペイロードを抽出する、 `get` メソッドです。  
  
##  <a name="a-namechoicelinktargetmethoda-choicelinktarget-method"></a><a name="choice__link_target_method"></a>  choice::link_target メソッド  
 これにターゲット ブロックをリンク `choice` メッセージング ブロックします。  
  
```  
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、 `ITarget` リンク先のブロック `choice` メッセージング ブロックします。  
  
##  <a name="a-namechoicereleasemethoda-choicerelease-method"></a><a name="choice__release_method"></a>  choice::release メソッド  
 以前に成功したメッセージの予約を解放します。  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
  `runtime_object_identity` の `message` リリースされているオブジェクトします。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、 `release` メソッドです。  
  
##  <a name="a-namechoicereleaserefmethoda-choicereleaseref-method"></a><a name="choice__release_ref_method"></a>  choice::release_ref メソッド  
 この参照カウントを解放 `choice` メッセージング ブロックします。  
  
```  
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出して、ターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、 `ITarget` このソースからリンクが解除されるオブジェクト。 ターゲット ブロック用に予約されたリソースを解放できるは、ソース ブロックです。  
  
##  <a name="a-namechoicereservemethoda-choicereserve-method"></a><a name="choice__reserve_method"></a>  choice::reserve メソッド  
 これによって以前に提供メッセージを予約 `choice` メッセージング ブロックします。  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
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
  
##  <a name="a-namechoiceunlinktargetmethoda-choiceunlinktarget-method"></a><a name="choice__unlink_target_method"></a>  choice::unlink_target メソッド  
 これから、ターゲット ブロックのリンクを解除 `choice` メッセージング ブロックします。  
  
```  
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、 `ITarget` このリンクを解除するブロック `choice` メッセージング ブロックします。  
  
##  <a name="a-namechoiceunlinktargetsmethoda-choiceunlinktargets-method"></a><a name="choice__unlink_targets_method"></a>  choice::unlink_targets メソッド  
 これからすべてのターゲットのリンクを解除 `choice` メッセージング ブロックします。  
  
```  
virtual void unlink_targets();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドがあるため、デストラクターから呼び出される必要はありません、内部のデストラクター `single_assignment` ブロックが正常に解除されます。  
  
##  <a name="a-namechoicevaluemethoda-choicevalue-method"></a><a name="choice__value_method"></a>  choice::value メソッド  
 によって選択されたインデックスを持つメッセージを取得、 `choice` メッセージング ブロックします。  
  
```  
template <
    typename _Payload_type  
>  
_Payload_type const& value();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Payload_type`  
 メッセージ ペイロードの種類。  
  
### <a name="return-value"></a>戻り値  
 メッセージのペイロード。  
  
### <a name="remarks"></a>コメント  
  `choice` メッセージング ブロックは、さまざまなペイロードの種類の入力を行うことができます、取得時に、ペイロードの種類を指定する必要があります。 結果に基づいて型を指定できます、 `index` メソッドです。  
  
## <a name="see-also"></a>「  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [クラスを結合します。](../Topic/join%20Class.md)   
 [single_assignment クラス](../../../parallel/concrt/reference/single-assignment-class.md)
