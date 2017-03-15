---
title: "ISource クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::ISource
dev_langs:
- C++
helpviewer_keywords:
- ISource class
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
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
ms.openlocfilehash: db3ba296a96b2e77c0ae7d9be3d0a499fe2e7f76
ms.lasthandoff: 02/24/2017

---
# <a name="isource-class"></a>ISource クラス
`ISource` クラスは、すべてのソース ブロック用のインターフェイスです。 ソース ブロックは、メッセージを `ITarget` ブロックに伝達します。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class ISource;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 メッセージ内のペイロードのデータ型は、ソース ブロックから生成されます。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`source_type`|型の別名`T`します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[~ ISource デストラクター](#dtor)|`ISource` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept メソッド](#accept)|派生クラスでオーバーライドされた場合は、これによって提供されたメッセージを受け入れる`ISource`ブロック、呼び出し元に所有権を移譲します。|  
|[acquire_ref メソッド](#acquire_ref)|派生クラスでオーバーライドされた場合は、これに対する参照カウントを取得`ISource`ブロックを削除しないようにします。|  
|[consume メソッド](#consume)|派生クラスでオーバーライドされると、これによって以前に提供メッセージを使用して`ISource`をブロックし、所有権を呼び出し元に移動するターゲットが正常に予約されています。|  
|[link_target メソッド](#link_target)|派生クラスでオーバーライドされた場合は、これにターゲット ブロックをリンク`ISource`ブロックします。|  
|[release メソッド](#release)|派生クラスでオーバーライドされた場合は、以前に成功したメッセージの予約を解放します。|  
|[release_ref メソッド](#release_ref)|派生クラスでオーバーライドされた場合は、これに対する参照カウントを解放`ISource`ブロックします。|  
|[reserve メソッド](#reserve)|派生クラスでオーバーライドされた場合は、これによって以前に提供メッセージを予約`ISource`ブロックします。|  
|[unlink_target メソッド](#unlink_target)|派生クラスでオーバーライドされると、これから、ターゲット ブロックのリンクを解除`ISource`場合、ブロックをリンクできる以前検出します。|  
|[unlink_targets メソッド](#unlink_targets)|派生クラスでオーバーライドされると、これからのすべてのターゲット ブロックのリンクを解除`ISource`ブロックします。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ISource`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-nameaccepta-accept"></a><a name="accept"></a>そのまま使用します。 

 派生クラスでオーバーライドされた場合は、これによって提供されたメッセージを受け入れる`ISource`ブロック、呼び出し元に所有権を移譲します。  
  
```
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクトです。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`accept`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 所有権が呼び出し元は、メッセージへのポインター。  
  
### <a name="remarks"></a>コメント  
 `accept`メソッドは、メッセージは、これによって提供されているときに、ターゲットによって呼び出されます。`ISource`ブロックします。 返されるメッセージ ポインターに渡されたものと異なる場合があります、`propagate`のメソッド、`ITarget`ブロック、メッセージのコピーを作成してこのソースと判断した場合。  
  
##  <a name="a-nameacquirerefa-acquireref"></a><a name="acquire_ref"></a>acquire_ref 

 派生クラスでオーバーライドされた場合は、これに対する参照カウントを取得`ISource`ブロックを削除しないようにします。  
  
```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出して、ターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`中にこのソースにリンクされているオブジェクト、`link_target`メソッドです。  
  
##  <a name="a-nameconsumea-consume"></a><a name="consume"></a>使用します。 

 派生クラスでオーバーライドされると、これによって以前に提供メッセージを使用して`ISource`をブロックし、所有権を呼び出し元に移動するターゲットが正常に予約されています。  
  
```
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
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
  
##  <a name="a-namedtora-isource"></a><a name="dtor"></a>~ ISource 

 `ISource` オブジェクトを破棄します。  
  
```
virtual ~ISource();
```  
  
##  <a name="a-namelinktargeta-linktarget"></a><a name="link_target"></a>link_target 

 派生クラスでオーバーライドされた場合は、これにターゲット ブロックをリンク`ISource`ブロックします。  
  
```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 次のようにリンクされているターゲット ブロックへのポインター`ISource`ブロックします。  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>リリース 

 派生クラスでオーバーライドされた場合は、以前に成功したメッセージの予約を解放します。  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、予約済みの`message`オブジェクトです。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`release`メソッドです。  
  
##  <a name="a-namereleaserefa-releaseref"></a><a name="release_ref"></a>release_ref 

 派生クラスでオーバーライドされた場合は、これに対する参照カウントを解放`ISource`ブロックします。  
  
```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出して、ターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`このソースからリンクが解除されるオブジェクト。 ターゲット ブロック用に予約されたリソースを解放できるは、ソース ブロックです。  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>予約 

 派生クラスでオーバーライドされた場合は、これによって以前に提供メッセージを予約`ISource`ブロックします。  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクトです。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`reserve`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 `true`場合は、メッセージが正常に予約された、`false`それ以外の場合。 予約はエラーになるなど、さまざまな理由: メッセージが既にに予約されているまたはソースが、予約を拒否し、など、別のターゲットで受け入れられます。  
  
### <a name="remarks"></a>コメント  
 呼び出した後`reserve`、成功した場合、いずれかを呼び出す必要があります`consume`または`release`かかるまたはそれぞれのメッセージを所有しているを断念するためにします。  
  
##  <a name="a-nameunlinktargeta-unlinktarget"></a><a name="unlink_target"></a>unlink_target 

 派生クラスでオーバーライドされると、これから、ターゲット ブロックのリンクを解除`ISource`場合、ブロックをリンクできる以前検出します。  
  
```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このリンクが解除されるターゲット ブロックへのポインター`ISource`ブロックします。  
  
##  <a name="a-nameunlinktargetsa-unlinktargets"></a><a name="unlink_targets"></a>unlink_targets 

 派生クラスでオーバーライドされると、これからのすべてのターゲット ブロックのリンクを解除`ISource`ブロックします。  
  
```
virtual void unlink_targets() = 0;
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [ITarget クラス](itarget-class.md)

