---
title: "ordered_message_processor クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ordered_message_processor
- AGENTS/concurrency::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::async_send
- AGENTS/concurrency::ordered_message_processor::initialize
- AGENTS/concurrency::ordered_message_processor::initialize_batched_processing
- AGENTS/concurrency::ordered_message_processor::sync_send
- AGENTS/concurrency::ordered_message_processor::wait
- AGENTS/concurrency::ordered_message_processor::process_incoming_message
dev_langs:
- C++
helpviewer_keywords:
- ordered_message_processor class
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
caps.latest.revision: 17
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
ms.openlocfilehash: 1c3147001db16b610992d2501ed12ad4bd001fc9
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="orderedmessageprocessor-class"></a>ordered_message_processor クラス
`ordered_message_processor` は、メッセージ ブロックがメッセージを受け取った順序で処理できるようにする `message_processor` です。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class ordered_message_processor : public message_processor<T>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 プロセッサによって処理されるメッセージのペイロードの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`type`|型の別名`T`します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ordered_message_processor](#ctor)|`ordered_message_processor` オブジェクトを構築します。|  
|[~ ordered_message_processor デストラクター](#dtor)|`ordered_message_processor` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[async_send](#async_send)|非同期的にメッセージをキューに登録しがまだ実行されている場合は、処理タスクを開始します。 (上書き[message_processor::async_send](message-processor-class.md#async_send))。|  
|[初期化します。](#initialize)|初期化、`ordered_message_processor`適切なコールバック関数、スケジューラ、およびスケジュール グループを持つオブジェクト。|  
|[initialize_batched_processing](#initialize_batched_processing)|バッチ処理されるメッセージの処理を初期化します。|  
|[sync_send](#sync_send)|同期的にメッセージをキューに登録しがまだ実行されている場合は、処理タスクを開始します。 (上書き[message_processor::sync_send](message-processor-class.md#sync_send))。|  
|[待機](#wait)|すべてのタスクの非同期処理がブロックを破棄する前に完了するのに時間があることを確認するメッセージ ブロックのデストラクターで使用されるプロセッサ固有のスピン待ちします。 (上書き[message_processor::wait](message-processor-class.md#wait))。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[process_incoming_message](#process_incoming_message)|非同期的に呼び出される処理関数です。 メッセージをデキューし、それらの処理を開始します。 (上書き[message_processor::process_incoming_message](message-processor-class.md#process_incoming_message))。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [message_processor](message-processor-class.md)  
  
 `ordered_message_processor`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="async_send"></a>async_send 

 非同期的にメッセージをキューに登録しがまだ実行されている場合は、処理タスクを開始します。  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Msg`  
 メッセージへのポインター。  
  
##  <a name="initialize"></a>初期化します。 

 初期化、`ordered_message_processor`適切なコールバック関数、スケジューラ、およびスケジュール グループを持つオブジェクト。  
  
```
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PScheduler`  
 軽量タスクをスケジュールするために使用するスケジューラへのポインター。  
  
 `_PScheduleGroup`  
 軽量タスクをスケジュールするために使用するスケジュール グループへのポインター。  
  
 `_Handler`  
 コールバック時に呼び出されるハンドラー ファンクタ。  
  
##  <a name="initialize_batched_processing"></a>initialize_batched_processing 

 バッチ処理されるメッセージの処理を初期化します。  
  
```
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Processor`  
 コールバック時に呼び出されるプロセッサ ファンクタ。  
  
 `_Propagator`  
 伝達子ファンクタ コールバック中に呼び出されます。  
  
##  <a name="ctor"></a>ordered_message_processor 

 `ordered_message_processor` オブジェクトを構築します。  
  
```
ordered_message_processor();
```  
  
### <a name="remarks"></a>コメント  
 これは、`ordered_message_processor`まで同期または非同期のハンドラーをスケジュールできませんが、`initialize`関数が呼び出されます。  
  
##  <a name="dtor"></a>~ ordered_message_processor 

 `ordered_message_processor` オブジェクトを破棄します。  
  
```
virtual ~ordered_message_processor();
```  
  
### <a name="remarks"></a>コメント  
 プロセッサを破棄する前にすべての未解決の非同期操作を待機します。  
  
##  <a name="process_incoming_message"></a>process_incoming_message 

 非同期的に呼び出される処理関数です。 メッセージをデキューし、それらの処理を開始します。  
  
```
virtual void process_incoming_message();
```  
  
##  <a name="sync_send"></a>sync_send 

 同期的にメッセージをキューに登録しがまだ実行されている場合は、処理タスクを開始します。  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Msg`  
 メッセージへのポインター。  
  
##  <a name="wait"></a>待機 

 すべてのタスクの非同期処理がブロックを破棄する前に完了するのに時間があることを確認するメッセージ ブロックのデストラクターで使用されるプロセッサ固有のスピン待ちします。  
  
```
virtual void wait();
```  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

