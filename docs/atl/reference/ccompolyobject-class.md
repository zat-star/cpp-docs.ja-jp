---
title: "CComPolyObject クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComPolyObject
- ATL.CComPolyObject<contained>
- ATL::CComPolyObject
- ATL::CComPolyObject<contained>
- ATL.CComPolyObject
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 37be4c985983cb760246a4a2450c27d175d1f440
ms.lasthandoff: 02/24/2017

---
# <a name="ccompolyobject-class"></a>CComPolyObject クラス
このクラスは実装**IUnknown**集計または非集約オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```
template<class contained>  
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>パラメーター  
 `contained`  
 派生したクラスに、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のインターフェイスからも、です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComPolyObject::CComPolyObject](#ccompolyobject)|コンストラクターです。|  
|[CComPolyObject:: ~ CComPolyObject](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComPolyObject::AddRef](#addref)|オブジェクトの参照カウントをインクリメントします。|  
|[CComPolyObject::CreateInstance](#createinstance)|(静的)新しいを作成することができます**CComPolyObject** `contained` ** > **のオーバーヘッドなしオブジェクト[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)します。|  
|[CComPolyObject::FinalConstruct](#finalconstruct)|最終的な初期化を実行`m_contained`します。|  
|[CComPolyObject::FinalRelease](#finalrelease)|最終的な破棄を実行`m_contained`します。|  
|[CComPolyObject::QueryInterface](#queryinterface)|要求されたインターフェイスへのポインターを取得します。|  
|[CComPolyObject::Release](#release)|オブジェクトの参照カウントをデクリメントします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComPolyObject::m_contained](#m_contained)|デリゲート**IUnknown**集約オブジェクトの場合、外部への呼び出し、 **IUnknown**内のオブジェクト、オブジェクトが集計されない場合。|  
  
## <a name="remarks"></a>コメント  
 `CComPolyObject`実装する[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)集計または非集約オブジェクトです。  
  
 インスタンス`CComPolyObject`作成されると、外側の値"不明"がオンになっています。 ある場合**NULL**、 **IUnknown**非集約オブジェクトを実装します。 外側の unknown がない場合**NULL**、 **IUnknown**集約オブジェクトの実装です。  
  
 使用する利点`CComPolyObject`両方を避けることは、[すると](../../atl/reference/ccomaggobject-class.md)と[と](../../atl/reference/ccomobject-class.md)モジュールで、集計データおよび非集計の状況に対処します。 単一の`CComPolyObject`オブジェクトがどちらの場合も、処理します。 つまり、モジュールで、vtable の&1; つだけのコピーと関数の&1; つのコピーが存在します。 Vtable のサイズが大きい場合は、モジュールのサイズを大幅に縮小このできます。 ただし、vtable が小さい場合を使用して`CComPolyObject`集計または非集約オブジェクトは、最適化されていないために、モジュールのサイズを少しだけ多めにつながると`CComAggObject`と`CComObject`です。  
  
 場合、`DECLARE_POLY_AGGREGATABLE`マクロはオブジェクトのクラス定義で指定された`CComPolyObject`オブジェクトを作成するために使用されます。 `DECLARE_POLY_AGGREGATABLE`自動的に宣言する、ATL プロジェクト ウィザードを使用して、フル コントロールまたは Internet Explorer のコントロールを作成するかどうか。  
  
 集約される場合、`CComPolyObject`オブジェクトには、独自**IUnknown**、外側のオブジェクトから別の**IUnknown**、および参照カウントを管理します。 `CComPolyObject`使用して[した](../../atl/reference/ccomcontainedobject-class.md)を外部の"不明"に委任します。  
  
 集計の詳細については、記事を参照してください。 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComPolyObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-nameaddrefa--ccompolyobjectaddref"></a><a name="addref"></a>CComPolyObject::AddRef  
 オブジェクトの参照カウントをインクリメントします。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たないかテスト可能性のある値。  
  
##  <a name="a-nameccompolyobjecta--ccompolyobjectccompolyobject"></a><a name="ccompolyobject"></a>CComPolyObject::CComPolyObject  
 コンストラクターです。  
  
```
CComPolyObject(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 [in]外側の unknown を集計する場合は、オブジェクトへのポインターまたは**NULL**場合、オブジェクトの場合は、オブジェクトが集計されません。  
  
### <a name="remarks"></a>コメント  
 初期化、`CComContainedObject`データ メンバー[で呼び出され](#m_contained)とモジュールのロック カウントをインクリメントします。  
  
 デストラクター、モジュール ロック カウントをデクリメントします。  
  
##  <a name="a-namedtora--ccompolyobjectccompolyobject"></a><a name="dtor"></a>CComPolyObject:: ~ CComPolyObject  
 デストラクターです。  
  
```
~CComPolyObject();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し、割り当てられているすべてのリソースを解放[FinalRelease](#finalrelease)、およびモジュールのロック カウントをデクリメントします。  
  
##  <a name="a-namecreateinstancea--ccompolyobjectcreateinstance"></a><a name="createinstance"></a>CComPolyObject::CreateInstance  
 新しいを作成することができます**CComPolyObject** `contained` ** > **のオーバーヘッドなしオブジェクト[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)します。  
  
```
static HRESULT WINAPI CreateInstance(  
    LPUNKNOWN pUnkOuter, 
    CComPolyObject<contained>** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pp`  
 [out]ポインター、 **CComPolyObject** `contained` ** > **ポインター。 場合`CreateInstance`は成功せず`pp`に設定されている**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 返されるオブジェクトは、参照カウントが&0;、ためコール`AddRef`、すぐに実行して**リリース**終わったときに、オブジェクトへのポインターの参照を解放します。  
  
 直接オブジェクトにアクセスすることは引き続きのオーバーヘッドを生じさせずに新しいオブジェクトを作成する場合`CoCreateInstance`を使用して[あって](../../atl/reference/ccomcoclass-class.md#createinstance)代わりにします。  
  
##  <a name="a-namefinalconstructa--ccompolyobjectfinalconstruct"></a><a name="finalconstruct"></a>CComPolyObject::FinalConstruct  
 オブジェクトの構築の最終段階で呼び出されると、このメソッドの最終に対して初期化を実行、[で呼び出され](#m_contained)データ メンバーです。  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="a-namefinalreleasea--ccompolyobjectfinalrelease"></a><a name="finalrelease"></a>CComPolyObject::FinalRelease  
 オブジェクトの破棄時に呼び出されると、このメソッドは、解放、[で呼び出され](#m_contained)データ メンバーです。  
  
```
void FinalRelease();
```  
  
##  <a name="a-namemcontaineda--ccompolyobjectmcontained"></a><a name="m_contained"></a>CComPolyObject::m_contained  
 A[した](../../atl/reference/ccomcontainedobject-class.md)クラスから派生するオブジェクト。  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>パラメーター  
 `contained`  
 [in]派生したクラスに、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のインターフェイスからも、です。  
  
### <a name="remarks"></a>コメント  
 **IUnknown**を介して呼び出す`m_contained`集約オブジェクトの場合は、外部に委任、 **IUnknown**場合は、オブジェクトは集計されません。 このオブジェクトのです。  
  
##  <a name="a-namequeryinterfacea--ccompolyobjectqueryinterface"></a><a name="queryinterface"></a>CComPolyObject::QueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>  
HRESULT QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `Q`  
 COM インターフェイスです。  
  
 `iid`  
 [in]要求されているインターフェイスの識別子。  
  
 `ppvObject`  
 [out]によって識別されるインターフェイス ポインターへのポインター`iid`します。 オブジェクトがこのインターフェイスをサポートしていない場合`ppvObject`に設定されている**NULL**します。  
  
 `pp`  
 [out]識別されるインターフェイスへのポインター **__uuidof(Q)**します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 要求されたインターフェイスの場合、集約オブジェクトの**IUnknown**、 `QueryInterface` 、集約オブジェクトの独自のポインターを返します**IUnknown**し、参照カウントをインクリメントします。 それ以外の場合、このメソッドは、インターフェイスを介しての照会、`CComContainedObject`データ メンバー[で呼び出され](#m_contained)します。  
  
##  <a name="a-namereleasea--ccompolyobjectrelease"></a><a name="release"></a>CComPolyObject::Release  
 オブジェクトの参照カウントをデクリメントします。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、**リリース**診断に役に立たないかテスト可能性のある値を返します。 非デバッグ ビルドで**リリース**常に 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [DECLARE_POLY_AGGREGATABLE](http://msdn.microsoft.com/library/7569e738-cfbc-4404-ba1d-78dcefa3bdb3)   
 [クラスの概要](../../atl/atl-class-overview.md)

