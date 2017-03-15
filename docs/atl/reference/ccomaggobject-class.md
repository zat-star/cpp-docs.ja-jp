---
title: "クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComAggObject<contained>
- ATL.CComAggObject
- ATL.CComAggObject<contained>
- CComAggObject
- ATL::CComAggObject
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
caps.latest.revision: 29
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 386ab09418c879c0de0d82d729a3de1b2e270016
ms.lasthandoff: 02/24/2017

---
# <a name="ccomaggobject-class"></a>クラス
このクラスは、実装、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)集約オブジェクトのインターフェイスです。 定義上、外部オブジェクトに集約オブジェクトが含まれています。 `CComAggObject`クラスがに似ていますが、[とクラス](../../atl/reference/ccomobject-class.md)外部クライアントに直接アクセスできるインターフェイスを公開する点が異なります。  
  
## <a name="syntax"></a>構文  
  
```
template<class contained>  
class CComAggObject : public IUnknown, 
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>パラメーター  
 `contained`  
 派生したクラスに、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のインターフェイスからも、です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComAggObject::CComAggObject](#ccomaggobject)|コンストラクターです。|  
|[:: ~ すると](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComAggObject::AddRef](#addref)|集約オブジェクトの参照カウントをインクリメントします。|  
|[CComAggObject::CreateInstance](#createinstance)|この静的関数では、新しいを作成することができます**すると** `contained` ** > **のオーバーヘッドなしオブジェクト[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)します。|  
|[CComAggObject::FinalConstruct](#finalconstruct)|最終的な初期化を実行`m_contained`します。|  
|[CComAggObject::FinalRelease](#finalrelease)|最終的な破棄を実行`m_contained`します。|  
|[CComAggObject::QueryInterface](#queryinterface)|要求されたインターフェイスへのポインターを取得します。|  
|[CComAggObject::Release](#release)|集約オブジェクトの参照カウントをデクリメントします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComAggObject::m_contained](#m_contained)|デリゲート`IUnknown`外部への呼び出しです。|  
  
## <a name="remarks"></a>コメント  
 `CComAggObject`実装する[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)集約オブジェクトです。 `CComAggObject`それぞれの**IUnknown**インターフェイスを外部のオブジェクトとは別**IUnknown**インターフェイス、および参照カウントを保持します。  
  
 集計の詳細については、記事を参照してください。 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-nameaddrefa--ccomaggobjectaddref"></a><a name="addref"></a>CComAggObject::AddRef  
 集約オブジェクトの参照カウントをインクリメントします。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たないかテスト可能性のある値。  
  
##  <a name="a-nameccomaggobjecta--ccomaggobjectccomaggobject"></a><a name="ccomaggobject"></a>CComAggObject::CComAggObject  
 コンストラクターです。  
  
```
CComAggObject(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 [in]外部不明です。  
  
### <a name="remarks"></a>コメント  
 初期化、`CComContainedObject`メンバー、[で呼び出され](#m_contained)モジュールのロック カウントをインクリメントします。  
  
 デストラクター、モジュール ロック カウントをデクリメントします。  
  
##  <a name="a-namedtora--ccomaggobjectccomaggobject"></a><a name="dtor"></a>:: ~ すると  
 デストラクターです。  
  
```
~CComAggObject();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し、割り当てられているすべてのリソースを解放[FinalRelease](#finalrelease)、およびモジュールのロック カウントをデクリメントします。  
  
##  <a name="a-namecreateinstancea--ccomaggobjectcreateinstance"></a><a name="createinstance"></a>CComAggObject::CreateInstance  
 この静的関数では、新しいを作成することができます**すると**`contained` ** > **のオーバーヘッドなしオブジェクト[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)します。  
  
```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pp`  
 [out]ポインター、**すると\<***に含まれる* ** > **ポインター。 場合`CreateInstance`は成功せず`pp`に設定されている**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 返されるオブジェクトは、参照カウントが&0;、ためコール`AddRef`、すぐに実行して**リリース**終わったときに、オブジェクトへのポインターの参照を解放します。  
  
 必要な送信しない、オブジェクトへのアクセスが、引き続きのオーバーヘッドを生じさせずに新しいオブジェクトを作成する場合`CoCreateInstance`を使用して[あって](../../atl/reference/ccomcoclass-class.md#createinstance)代わりにします。  
  
##  <a name="a-namefinalconstructa--ccomaggobjectfinalconstruct"></a><a name="finalconstruct"></a>CComAggObject::FinalConstruct  
 オブジェクトの構築の最終段階で呼び出されると、このメソッドの最終に対して初期化を実行、[で呼び出され](#m_contained)メンバーです。  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="a-namefinalreleasea--ccomaggobjectfinalrelease"></a><a name="finalrelease"></a>CComAggObject::FinalRelease  
 オブジェクトの破棄時に呼び出されると、このメソッドは、解放、[で呼び出され](#m_contained)メンバーです。  
  
```
void FinalRelease();
```  
  
##  <a name="a-namemcontaineda--ccomaggobjectmcontained"></a><a name="m_contained"></a>CComAggObject::m_contained  
 A[した](../../atl/reference/ccomcontainedobject-class.md)クラスから派生するオブジェクト。  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>パラメーター  
 `contained`  
 [in]派生したクラスに、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のインターフェイスからも、です。  
  
### <a name="remarks"></a>コメント  
 すべて**IUnknown**を介して呼び出す`m_contained`外部の"不明"に委任します。  
  
##  <a name="a-namequeryinterfacea--ccomaggobjectqueryinterface"></a><a name="queryinterface"></a>CComAggObject::QueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの識別子。  
  
 `ppvObject`  
 [out]によって識別されるインターフェイス ポインターへのポインター`iid`します。 オブジェクトがこのインターフェイスをサポートしていない場合`ppvObject`に設定されている**NULL**します。  
  
 `pp`  
 [out]型によって識別されるインターフェイス ポインターへのポインター`Q`します。 オブジェクトがこのインターフェイスをサポートしていない場合`pp`に設定されている**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 要求されたインターフェイスの場合**IUnknown**、 `QueryInterface` 、集約オブジェクトの独自のポインターを返します**IUnknown**し、参照カウントをインクリメントします。 それ以外の場合、このメソッドは、インターフェイスを介しての照会、`CComContainedObject`メンバー、[で呼び出され](#m_contained)します。  
  
##  <a name="a-namereleasea--ccomaggobjectrelease"></a><a name="release"></a>CComAggObject::Release  
 集約オブジェクトの参照カウントをデクリメントします。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、**リリース**診断に役に立たないかテスト可能性のある値を返します。 非デバッグ ビルドでは、**リリース**常に 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab)   
 [集約](http://msdn.microsoft.com/library/a54220df-4330-4e4d-b7fb-8b63dd62d337)   
 [DECLARE_NOT_AGGREGATABLE](http://msdn.microsoft.com/library/2a116c7c-bab8-4f2a-a9ad-03d7aba0f762)   
 [クラスの概要](../../atl/atl-class-overview.md)

