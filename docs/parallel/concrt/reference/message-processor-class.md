---
title: "message_processor クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::message_processor
dev_langs:
- C++
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
caps.latest.revision: 16
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
ms.openlocfilehash: 98f1c1072916c4cf3670e40ce0c6ddd1a17f1b63
ms.lasthandoff: 02/24/2017

---
# <a name="messageprocessor-class"></a>message_processor クラス
`message_processor` クラスは、`message` オブジェクトを処理するための抽象基底クラスです。 メッセージの順序は保証されません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class message_processor;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 メッセージ内のペイロードのデータ型は、この`message_processor`オブジェクトです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`type`|型の別名`T`します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[async_send メソッド](#async_send)|派生クラスでオーバーライドされると、非同期的にブロックにメッセージを配置します。|  
|[sync_send メソッド](#sync_send)|派生クラスでオーバーライドされると、同期的にブロックにメッセージを配置します。|  
|[wait メソッド](#wait)|派生クラスでオーバーライドされると、すべての非同期操作が完了するを待機します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[process_incoming_message メソッド](#process_incoming_message)|派生クラスでオーバーライドされた場合は、ブロックにメッセージの転送処理を実行します。 新しいメッセージが追加され、キューが空にすることが検出するたびに&1; 回呼び出されます。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `message_processor`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-nameasyncsenda-asyncsend"></a><a name="async_send"></a>async_send 

 派生クラスでオーバーライドされると、非同期的にブロックにメッセージを配置します。  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Msg`  
 A`message`非同期的に送信するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 プロセッサの実装では、このメソッドをオーバーライドする必要があります。  
  
##  <a name="a-nameprocessincomingmessagea-processincomingmessage"></a><a name="process_incoming_message"></a>process_incoming_message 

 派生クラスでオーバーライドされた場合は、ブロックにメッセージの転送処理を実行します。 新しいメッセージが追加され、キューが空にすることが検出するたびに&1; 回呼び出されます。  
  
```
virtual void process_incoming_message() = 0;
```  
  
### <a name="remarks"></a>コメント  
 メッセージ ブロックの実装では、このメソッドをオーバーライドする必要があります。  
  
##  <a name="a-namesyncsenda-syncsend"></a><a name="sync_send"></a>sync_send 

 派生クラスでオーバーライドされると、同期的にブロックにメッセージを配置します。  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Msg`  
 A`message`同期的に送信するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 プロセッサの実装では、このメソッドをオーバーライドする必要があります。  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>待機 

 派生クラスでオーバーライドされると、すべての非同期操作が完了するを待機します。  
  
```
virtual void wait() = 0;
```  
  
### <a name="remarks"></a>コメント  
 プロセッサの実装では、このメソッドをオーバーライドする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [ordered_message_processor クラス](ordered-message-processor-class.md)

