---
title: "したクラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComContainedObject
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 60958f328d78205c3432f35ed4e3e3c4b652ebfe
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcontainedobject-class"></a>したクラス
このクラスは実装[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 、所有者オブジェクトのデリゲート**IUnknown**します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class Base>  
class CComContainedObject : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 派生したクラスに、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|コンストラクターです。 所有者オブジェクトのメンバーのポインターを初期化します`IUnknown`します。|  
|[した:: ~ しました。](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComContainedObject::AddRef](#addref)|所有者オブジェクトの参照カウントをインクリメントします。|  
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|所有者オブジェクトの取得`IUnknown`します。|  
|[CComContainedObject::QueryInterface](#queryinterface)|所有者オブジェクトの要求されたインターフェイスへのポインターを取得します。|  
|[CComContainedObject::Release](#release)|所有者オブジェクトの参照カウントをデクリメントします。|  
  
## <a name="remarks"></a>コメント  
 ATL では、`CComContainedObject`クラスに[すると](../../atl/reference/ccomaggobject-class.md)、 [CComPolyObject](../../atl/reference/ccompolyobject-class.md)、および[ティアオフ](../../atl/reference/ccomcachedtearoffobject-class.md)します。 `CComContainedObject`実装する[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 、所有者オブジェクトのデリゲート**IUnknown**します。 (所有者は、集計の外部オブジェクトまたはティアオフ インターフェイスの作成対象となるオブジェクトのいずれか)。`CComContainedObject`呼び出し`CComObjectRootEx`の`OuterQueryInterface`、 `OuterAddRef`、および`OuterRelease`から継承されたすべての`Base`です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComContainedObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-nameaddrefa--ccomcontainedobjectaddref"></a><a name="addref"></a>CComContainedObject::AddRef  
 所有者オブジェクトの参照カウントをインクリメントします。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たないかテスト可能性のある値。  
  
##  <a name="a-nameccomcontainedobjecta--ccomcontainedobjectccomcontainedobject"></a><a name="ccomcontainedobject"></a>CComContainedObject::CComContainedObject  
 コンストラクターです。  
  
```
CComContainedObject(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 [in]所有者オブジェクトの**IUnknown**します。  
  
### <a name="remarks"></a>コメント  
 セット、`m_pOuterUnknown`メンバー ポインター (から継承された、`Base`クラス) を`pv`します。  
  
##  <a name="a-namedtora--ccomcontainedobjectccomcontainedobject"></a><a name="dtor"></a>した:: ~ しました。  
 デストラクターです。  
  
```
~CComContainedObject();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="a-namegetcontrollingunknowna--ccomcontainedobjectgetcontrollingunknown"></a><a name="getcontrollingunknown"></a>CComContainedObject::GetControllingUnknown  
 返します。、`m_pOuterUnknown`メンバー ポインター (から継承された、*ベース*クラス)、所有者オブジェクトの保持している**IUnknown**します。  
  
```
IUnknown* GetControllingUnknown();
```  
  
### <a name="return-value"></a>戻り値  
 所有者オブジェクトの**IUnknown**します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは仮想にする場合は`Base`が宣言されている、 [DECLARE_GET_CONTROLLING_UNKNOWN](http://msdn.microsoft.com/library/82b0199a-a9d5-4f95-a711-fa1ae18e1f77)マクロです。  
  
##  <a name="a-namequeryinterfacea--ccomcontainedobjectqueryinterface"></a><a name="queryinterface"></a>CComContainedObject::QueryInterface  
 所有者オブジェクトの要求されたインターフェイスへのポインターを取得します。  
  
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
  
##  <a name="a-namereleasea--ccomcontainedobjectrelease"></a><a name="release"></a>CComContainedObject::Release  
 所有者オブジェクトの参照カウントをデクリメントします。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、**リリース**診断に役に立たないかテスト可能性のある値を返します。 非デバッグ ビルドでは、**リリース**常に 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

