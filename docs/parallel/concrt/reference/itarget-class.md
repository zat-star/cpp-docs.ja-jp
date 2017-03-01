---
title: "ITarget クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::ITarget
dev_langs:
- C++
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
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
ms.openlocfilehash: aa9001de9ec35f20cd76f701d6b8acc5de7ffde0
ms.lasthandoff: 02/24/2017

---
# <a name="itarget-class"></a>ITarget クラス
`ITarget` クラスは、すべてのターゲット ブロックのインターフェイスです。 ターゲット ブロックは、`ISource` ブロックから提供されたメッセージを処理します。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class ITarget;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 メッセージ内のペイロードのデータ型は、ターゲット ブロックによって受け入れられます。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`filter_method`|ブロックを表すオブジェクトによって使用されるメソッドのシグネチャ、`bool`提供されたメッセージを受け入れられる必要があるかどうかを決定する値。|  
|`type`|型の別名`T`します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[~ ITarget デストラクター](#dtor)|`ITarget` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[propagate メソッド](#propagate)|派生クラスでオーバーライドされると、非同期的にメッセージ ソース ブロックからこのターゲット ブロックに渡します。|  
|[send メソッド](#send)|派生クラスでオーバーライドされると、ターゲット ブロックにメッセージを同期的に渡します。|  
|[supports_anonymous_source メソッド](#supports_anonymous_source)|派生クラスでオーバーライドされた場合は、true または false メッセージ ブロックがそれにリンクされていないソースから提供されたメッセージを受け入れるかどうかに応じてを返します。 オーバーライドされたメソッドが返された場合`true`、延期されたメッセージの消費量を後で、ソースのリンクのレジストリに識別するソースの必要に応じて、ターゲットは、提供されたメッセージを延期できません。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[link_source メソッド](#link_source)|派生クラスでオーバーライドされた場合は、これに指定されたソース ブロックをリンク`ITarget`ブロックします。|  
|[unlink_source メソッド](#unlink_source)|派生クラスでオーバーライドされると、これから指定されたソース ブロックのリンクを解除`ITarget`ブロックします。|  
|[unlink_sources メソッド](#unlink_sources)|派生クラスでオーバーライドされると、これからのすべてのソース ブロックのリンクを解除`ITarget`ブロックします。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ITarget`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namedtora-itarget"></a><a name="dtor"></a>~ ITarget 

 `ITarget` オブジェクトを破棄します。  
  
```
virtual ~ITarget();
```  
  
##  <a name="a-namelinksourcea-linksource"></a><a name="link_source"></a>link_source 

 派生クラスでオーバーライドされた場合は、これに指定されたソース ブロックをリンク`ITarget`ブロックします。  
  
```
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PSource`  
 `ISource`ブロックにリンクされている`ITarget`ブロックします。  
  
### <a name="remarks"></a>コメント  
 この関数は、上で直接呼び出されませんが、`ITarget`ブロックします。 使用してブロックを連結する必要があります、`link_target`メソッドを`ISource`呼び出しは、ブロック、`link_source`メソッドを対応するターゲット。  
  
##  <a name="a-namepropagatea-propagate"></a><a name="propagate"></a>伝達 

 派生クラスでオーバーライドされると、非同期的にメッセージ ソース ブロックからこのターゲット ブロックに渡します。  
  
```
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)の関係を決定するターゲットを示す値。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターは`NULL`です。  
  
##  <a name="a-namesenda-send"></a><a name="send"></a>送信 

 派生クラスでオーバーライドされると、ターゲット ブロックにメッセージを同期的に渡します。  
  
```
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)の関係を決定するターゲットを示す値。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターは`NULL`です。  
  
 使用して、`send`メソッド メッセージの開始に使用の外部になり、ネットワーク内のメッセージの伝達には危険であり、デッドロックにつながることができます。  
  
 `send`返されるメッセージが、既にされて受け入れられると、してターゲット ブロックに転送されるか、ターゲットが拒否されました。  
  
##  <a name="a-namesupportsanonymoussourcea-supportsanonymoussource"></a><a name="supports_anonymous_source"></a>supports_anonymous_source 

 派生クラスでオーバーライドされた場合は、true または false メッセージ ブロックがそれにリンクされていないソースから提供されたメッセージを受け入れるかどうかに応じてを返します。 オーバーライドされたメソッドが返された場合`true`、延期されたメッセージの消費量を後で、ソースのリンクのレジストリに識別するソースの必要に応じて、ターゲットは、提供されたメッセージを延期できません。  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>戻り値  
 `true`ブロックがそれにリンクされていないソースからのメッセージを受け入れる場合`false`それ以外の場合。  
  
##  <a name="a-nameunlinksourcea-unlinksource"></a><a name="unlink_source"></a>unlink_source 

 派生クラスでオーバーライドされると、これから指定されたソース ブロックのリンクを解除`ITarget`ブロックします。  
  
```
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PSource`  
 `ISource`ここからリンクが解除されるブロック`ITarget`ブロックします。  
  
### <a name="remarks"></a>コメント  
 この関数は、上で直接呼び出されませんが、`ITarget`ブロックします。 使用してブロックを切断する必要があります、`unlink_target`または`unlink_targets`メソッド`ISource`呼び出しは、ブロック、`unlink_source`メソッドを対応するターゲット。  
  
##  <a name="a-nameunlinksourcesa-unlinksources"></a><a name="unlink_sources"></a>unlink_sources 

 派生クラスでオーバーライドされると、これからのすべてのソース ブロックのリンクを解除`ITarget`ブロックします。  
  
```
virtual void unlink_sources() = 0;
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [ISource クラス](isource-class.md)

