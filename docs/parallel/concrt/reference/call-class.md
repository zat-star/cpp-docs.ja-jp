---
title: "クラスを呼び出します |。Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- call
- AGENTS/concurrency::call
- AGENTS/concurrency::call::call
- AGENTS/concurrency::call::process_input_messages
- AGENTS/concurrency::call::process_message
- AGENTS/concurrency::call::propagate_message
- AGENTS/concurrency::call::send_message
- AGENTS/concurrency::call::supports_anonymous_source
dev_langs:
- C++
helpviewer_keywords:
- call class
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 894540410e2768be1cb679b5108fc8c694ca02d3
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="call-class"></a>call クラス
`call` メッセージング ブロックは、複数のソースを持つ、順序付けられた `target_block` であり、メッセージを受け取ったときに指定された関数を呼び出します。  
  
## <a name="syntax"></a>構文  
  
```
template<class T, class _FunctorType = std::function<void(T const&)>>
class call : public target_block<multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 メッセージのペイロードの種類は、このブロックに伝達されます。  
  
 `_FunctorType`  
 このブロックが受け入れることができる関数のシグネチャ。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[呼び出し](#ctor)|オーバーロードされます。 構築、`call`メッセージング ブロックします。|  
|[~ call デストラクター](#dtor)|破棄、`call`メッセージング ブロックします。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[process_input_messages](#process_input_messages)|入力メッセージには、呼び出し関数を実行します。|  
|[process_message](#process_message)|これで受け取られたメッセージを処理`call`メッセージング ブロックします。|  
|[propagate_message](#propagate_message)|メッセージを非同期的に渡す、`ISource`このブロック`call`メッセージング ブロックします。 によって呼び出される、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[send_message](#send_message)|メッセージを同期的に渡す、`ISource`このブロック`call`メッセージング ブロックします。 によって呼び出される、`send`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[supports_anonymous_source](#supports_anonymous_source)|上書き、`supports_anonymous_source`を示すこのブロックがリンクされていないソースによって提供されたメッセージを受け取ることができます。 (上書き[itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source))。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ITarget](itarget-class.md)  
  
 [target_block](target-block-class.md)  
  
 `call`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>呼び出し 

 構築、`call`メッセージング ブロックします。  
  
```
call(
    _Call_method const& _Func);

call(
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Func`  
 許容されるメッセージごとに呼び出される関数。  
  
 `_Filter`  
 提供されたメッセージを受け入れられる必要があるかどうかを決定するフィルター関数。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `call` オブジェクト。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `call` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="remarks"></a>コメント  
 `_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。  
  
 種類`_Call_method`シグネチャを持つファンクターは、`void (T const &)`によりが呼び出される、`call`メッセージング ブロック、メッセージを処理します。  
  
 種類`filter_method`シグネチャを持つファンクターは、`bool (T const &)`によりが呼び出される、`call`メッセージング ブロックを提供されたメッセージを受け入れる必要があるかどうかを判断します。  
  
##  <a name="dtor"></a>~ を呼び出す 

 破棄、`call`メッセージング ブロックします。  
  
```
~call();
```  
  
##  <a name="process_input_messages"></a>process_input_messages 

 入力メッセージには、呼び出し関数を実行します。  
  
```
virtual void process_input_messages(_Inout_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
  
##  <a name="process_message"></a>process_message 

 これで受け取られたメッセージを処理`call`メッセージング ブロックします。  
  
```
virtual void process_message(_Inout_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 処理されるメッセージへのポインター。  
  
##  <a name="propagate_message"></a>propagate_message 

 メッセージを非同期的に渡す、`ISource`このブロック`call`メッセージング ブロックします。 によって呼び出される、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。  
  
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
  
##  <a name="send_message"></a>send_message 

 メッセージを同期的に渡す、`ISource`このブロック`call`メッセージング ブロックします。 によって呼び出される、`send`メソッドは、ソース ブロックによって呼び出されるとします。  
  
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
  
##  <a name="supports_anonymous_source"></a>supports_anonymous_source 

 上書き、`supports_anonymous_source`を示すこのブロックがリンクされていないソースによって提供されたメッセージを受け取ることができます。  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>戻り値  
 `true`ブロックは延期しないために、メッセージを提供します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [transformer クラス](transformer-class.md)

