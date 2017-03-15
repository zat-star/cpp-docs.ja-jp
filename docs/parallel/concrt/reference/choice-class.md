---
title: "choice クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::choice
dev_langs:
- C++
helpviewer_keywords:
- choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
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
ms.openlocfilehash: 1ee8fe2197a41ad2abc14e24c372f808bdbc16d0
ms.lasthandoff: 02/24/2017

---
# <a name="choice-class"></a>choice クラス
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
|`type`|型の別名`T`します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[コンス トラクターの選択](#ctor)|オーバーロードされます。 `choice` メッセージング ブロックを構築します。|  
|[~ choice デストラクター](#dtor)|破棄、`choice`メッセージング ブロックします。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept メソッド](#accept)|これによって提供されたメッセージを受け入れ`choice`ブロック、呼び出し元に所有権を移譲します。|  
|[acquire_ref メソッド](#acquire_ref)|この参照カウントを取得し`choice`メッセージング ブロックは、削除を禁止します。|  
|[consume メソッド](#consume)|これによって以前に提供メッセージを使用して`choice`メッセージング ブロックし、所有権を呼び出し元に移動するターゲットが正常に予約されています。|  
|[has_value メソッド](#has_value)|チェックするかどうかこの`choice`値を持つメッセージング ブロックがまだに初期化します。|  
|[インデックス メソッド](#index)|インデックスを返す、`tuple`によって選択された要素を表す、`choice`メッセージング ブロックします。|  
|[link_target メソッド](#link_target)|これにターゲット ブロックをリンク`choice`メッセージング ブロックします。|  
|[release メソッド](#release)|以前に成功したメッセージの予約を解放します。|  
|[release_ref メソッド](#release_ref)|この参照カウントを解放`choice`メッセージング ブロックします。|  
|[reserve メソッド](#reserve)|これによって以前に提供メッセージを予約`choice`メッセージング ブロックします。|  
|[unlink_target メソッド](#unlink_target)|これから、ターゲット ブロックのリンクを解除`choice`メッセージング ブロックします。|  
|[unlink_targets メソッド](#unlink_targets)|これからすべてのターゲットのリンクを解除`choice`メッセージング ブロックします。 (上書き[isource::unlink_targets](isource-class.md#unlink_targets))。|  
|[メソッドの値](#value)|によって選択されたインデックスを持つメッセージを取得、`choice`メッセージング ブロックします。|  
  
## <a name="remarks"></a>コメント  
 Choice ブロックでは受信メッセージの&1; つだけが使用します。  
  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](isource-class.md)  
  
 `choice`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-nameaccepta-accept"></a><a name="accept"></a>そのまま使用します。 

 これによって提供されたメッセージを受け入れ`choice`ブロック、呼び出し元に所有権を移譲します。  
  
```  
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクトです。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`accept`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 所有権が呼び出し元は、メッセージへのポインター。  
  
##  <a name="a-nameacquirerefa-acquireref"></a><a name="acquire_ref"></a>acquire_ref 

 この参照カウントを取得し`choice`メッセージング ブロックは、削除を禁止します。  
  
```  
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出して、ターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`中にこのソースにリンクされているオブジェクト、`link_target`メソッドです。  
  
##  <a name="a-namectora-choice"></a><a name="ctor"></a>選択肢 

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
  
##  <a name="a-namedtora-choice"></a><a name="dtor"></a>~ の選択 

 破棄、`choice`メッセージング ブロックします。  
  
```  
~choice();
```  
  
##  <a name="a-nameconsumea-consume"></a><a name="consume"></a>使用します。 

 これによって以前に提供メッセージを使用して`choice`メッセージング ブロックし、所有権を呼び出し元に移動するターゲットが正常に予約されています。  
  
```  
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、予約済みの`message`オブジェクトです。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`consume`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`オブジェクトの呼び出し元が今すぐの所有権を持っています。  
  
### <a name="remarks"></a>コメント  
 `consume`メソッドは`accept`への呼び出しで前に必ず必要がありますが、`reserve`返さ`true`します。  
  
##  <a name="a-namehasvaluea-hasvalue"></a><a name="has_value"></a>has_value 

 チェックするかどうかこの`choice`値を持つメッセージング ブロックがまだに初期化します。  
  
```  
bool has_value() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 `true`ブロックは、値を受け取っている場合`false`それ以外の場合。  
  
##  <a name="a-nameindexa-index"></a><a name="index"></a>インデックス 

 インデックスを返す、`tuple`によって選択された要素を表す、`choice`メッセージング ブロックします。  
  
```  
size_t index();
```  
  
### <a name="return-value"></a>戻り値  
 メッセージのインデックス。  
  
### <a name="remarks"></a>コメント  
 使用して、メッセージ ペイロードを抽出する、`get`メソッドです。  
  
##  <a name="a-namelinktargeta-linktarget"></a><a name="link_target"></a>link_target 

 これにターゲット ブロックをリンク`choice`メッセージング ブロックします。  
  
```  
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、`ITarget`リンク先のブロック`choice`メッセージング ブロックします。  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>リリース 

 以前に成功したメッセージの予約を解放します。  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`リリースされているオブジェクトします。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`release`メソッドです。  
  
##  <a name="a-namereleaserefa-releaseref"></a><a name="release_ref"></a>release_ref 

 この参照カウントを解放`choice`メッセージング ブロックします。  
  
```  
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出して、ターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`このソースからリンクが解除されるオブジェクト。 ターゲット ブロック用に予約されたリソースを解放できるは、ソース ブロックです。  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>予約 

 これによって以前に提供メッセージを予約`choice`メッセージング ブロックします。  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`予約されているオブジェクトします。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`reserve`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 `true`場合は、メッセージが正常に予約された、`false`それ以外の場合。 予約はエラーになるなど、さまざまな理由: メッセージが既にに予約されているまたはソースが、予約を拒否し、など、別のターゲットで受け入れられます。  
  
### <a name="remarks"></a>コメント  
 呼び出した後`reserve`、成功した場合、いずれかを呼び出す必要があります`consume`または`release`かかるまたはそれぞれのメッセージを所有しているを断念するためにします。  
  
##  <a name="a-nameunlinktargeta-unlinktarget"></a><a name="unlink_target"></a>unlink_target 

 これから、ターゲット ブロックのリンクを解除`choice`メッセージング ブロックします。  
  
```  
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、`ITarget`このリンクを解除するブロック`choice`メッセージング ブロックします。  
  
##  <a name="a-nameunlinktargetsa-unlinktargets"></a><a name="unlink_targets"></a>unlink_targets 

 これからすべてのターゲットのリンクを解除`choice`メッセージング ブロックします。  
  
```  
virtual void unlink_targets();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドがあるため、デストラクターから呼び出される必要はありません、内部のデストラクター`single_assignment`ブロックが正常に解除されます。  
  
##  <a name="a-namevaluea-value"></a><a name="value"></a>値 

 によって選択されたインデックスを持つメッセージを取得、`choice`メッセージング ブロックします。  
  
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
 `choice`メッセージング ブロックは、さまざまなペイロードの種類の入力を行うことができます、取得時に、ペイロードの種類を指定する必要があります。 結果に基づいて型を指定できます、`index`メソッドです。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [クラスを結合します。](join-class.md)   
 [single_assignment クラス](single-assignment-class.md)

