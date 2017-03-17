---
title: "ティアオフ クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 96f040c732c5545a9b8febb32fcb1636f0fe4a40
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcachedtearoffobject-class"></a>ティアオフ クラス
このクラスは実装[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)ティアオフ インターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
template
 <class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
 ::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>パラメーター  
 `contained`  
 ティアオフ クラスから派生`CComTearOffObjectBase`ティアオフ オブジェクトをサポートする場合、インターフェイスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|コンストラクターです。|  
|[ティアオフ:: ~ ティアオフ](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComCachedTearOffObject::AddRef](#addref)|参照カウントをインクリメントする`CComCachedTearOffObject`オブジェクトです。|  
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|呼び出し、 `m_contained::FinalConstruct` (ティアオフ クラスのメソッド)。|  
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|呼び出し、 `m_contained::FinalRelease` (ティアオフ クラスのメソッド)。|  
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|ポインターを返す、`IUnknown`の`CComCachedTearOffObject`オブジェクト、またはティアオフ クラスに要求されたインターフェイスへ (クラス`contained`)。|  
|[CComCachedTearOffObject::Release](#release)|参照カウントをデクリメント、`CComCachedTearOffObject`オブジェクトし、参照カウントが 0 の場合は、それを破棄します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComCachedTearOffObject::m_contained](#m_contained)|A`CComContainedObject`ティアオフ クラスから派生したオブジェクト (クラス`contained`)。|  
  
## <a name="remarks"></a>コメント  
 `CComCachedTearOffObject`実装する[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)ティアオフ インターフェイスです。 このクラスとは異なります`CComTearOffObject`で`CComCachedTearOffObject`で独自**IUnknown**、所有者オブジェクトから別の**IUnknown** (所有者は、ティアオフが作成される対象のオブジェクト)。 `CComCachedTearOffObject`独自に維持に参照カウントの**IUnknown**し、その参照カウントが&0; と自体を削除します。 ただし、そのティアオフのいずれかを照会する場合は、インターフェイス、オブジェクト所有者の参照カウント**IUnknown**が加算されます。  
  
 場合、`CComCachedTearOffObject`オブジェクトのティアオフの実装が既にインスタンス化され、もう一度同じについてティアオフ インターフェイスが照会`CComCachedTearOffObject`オブジェクトが再利用します。 これに対して、ティアオフ インターフェイス実装されている場合、`CComTearOffObject`所有者オブジェクトを使用してもう一度照会された別`CComTearOffObject`がインスタンス化されます。  
  
 所有者クラスを実装する必要があります`FinalRelease`と呼び出し**リリース**にキャッシュされた**IUnknown**の`CComCachedTearOffObject`、参照カウントをデクリメントします。 これにより、`CComCachedTearOffObject`の`FinalRelease`に呼び出され、ティアオフを削除します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="addref"></a>CComCachedTearOffObject::AddRef  
 参照カウントをインクリメント、 `CComCachedTearOffObject` 1 オブジェクト。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役立ちますしテスト可能性のある値。  
  
##  <a name="ccomcachedtearoffobject"></a>CComCachedTearOffObject::CComCachedTearOffObject  
 コンストラクターです。  
  
```
CComCachedTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 [in]ポインター、 **IUnknown**の`CComCachedTearOffObject`です。  
  
### <a name="remarks"></a>コメント  
 初期化、`CComContainedObject`メンバー、[で呼び出され](#m_contained)します。  
  
##  <a name="dtor"></a>ティアオフ:: ~ ティアオフ  
 デストラクターです。  
  
```
~CComCachedTearOffObject();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放[FinalRelease](#finalrelease)します。  
  
##  <a name="finalconstruct"></a>CComCachedTearOffObject::FinalConstruct  
 呼び出し**m_contained::FinalConstruct**を作成する`m_contained`、 `CComContainedObject` <  `contained`> ティアオフ クラスによって実装されるインターフェイスにアクセスするために使用します。  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="finalrelease"></a>CComCachedTearOffObject::FinalRelease  
 呼び出し**m_contained::FinalRelease**を解放する`m_contained`、 `CComContainedObject` <  `contained`> オブジェクトです。  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>CComCachedTearOffObject::m_contained  
 A[した](../../atl/reference/ccomcontainedobject-class.md)ティアオフ クラスから派生するオブジェクト。  
  
```
CcomContainedObject <contained> m_contained;
```     
  
### <a name="parameters"></a>パラメーター  
 `contained`  
 [in]ティアオフ クラスから派生`CComTearOffObjectBase`ティアオフ オブジェクトをサポートする場合、インターフェイスです。  
  
### <a name="remarks"></a>コメント  
 メソッド`m_contained`継承ではキャッシュされたティアオフ オブジェクトのティアオフ クラスにティアオフ インターフェイスにアクセスするため`QueryInterface`、 `FinalConstruct`、および`FinalRelease`です。  
  
##  <a name="queryinterface"></a>CComCachedTearOffObject::QueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの GUID です。  
  
 `ppvObject`  
 [out]によって識別されるインターフェイス ポインターへのポインター `iid`、または**NULL**インターフェイスが見つからない場合。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 要求されたインターフェイスの場合**IUnknown**へのポインターを返します、`CComCachedTearOffObject`の独自**IUnknown**し、参照カウントをインクリメントします。 それ以外の場合、ティアオフ クラスを使用して、上のインターフェイスに対してクエリを実行、 [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface)から継承されたメソッド`CComObjectRootEx`します。  

  
##  <a name="release"></a>CComCachedTearOffObject::Release  
 参照カウントを 1 つデクリメントし、参照カウントが 0 の場合は、削除、`CComCachedTearOffObject`オブジェクトです。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 非デバッグ ビルドでは、常に 0 を返します。 デバッグ ビルドで、診断に役に立たないかテスト可能性のある値を返します。  
  
## <a name="see-also"></a>関連項目  
 [CComTearOffObject クラス](../../atl/reference/ccomtearoffobject-class.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

