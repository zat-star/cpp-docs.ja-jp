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
- ATL.CComObject<Base>
- ATL::CComObject
- ATL::CComObject<Base>
- ATL.CComObject
- CComObject
dev_langs:
- C++
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
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
ms.openlocfilehash: 5f752b96d4a722fbddfcc9e5be3a82b8b12a86a1
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobject-class"></a>クラス
このクラスは実装**IUnknown**非集約オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```
template<class Base>  
class CComObject : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 派生したクラスに、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のインターフェイスからも、です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComObject::CComObject](#ccomobject)|コンストラクターです。|  
|[:: ~ と](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComObject::AddRef](#addref)|オブジェクトの参照カウントをインクリメントします。|  
|[CComObject::CreateInstance](#createinstance)|(静的)新しい`CComObject`オブジェクトです。|  
|[CComObject::QueryInterface](#queryinterface)|要求されたインターフェイスへのポインターを取得します。|  
|[CComObject::Release](#release)|オブジェクトの参照カウントをデクリメントします。|  
  
## <a name="remarks"></a>コメント  
 `CComObject`実装する[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)非集約オブジェクトです。 ただし、するために呼び出す`QueryInterface`、 `AddRef`、および**リリース**に委任`CComObjectRootEx`します。  
  
 使用の詳細については`CComObject`、記事を参照して[ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-nameaddrefa--ccomobjectaddref"></a><a name="addref"></a>CComObject::AddRef  
 オブジェクトの参照カウントをインクリメントします。  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>戻り値  
 この関数は、オブジェクトの新しいインクリメントされた参照カウントを返します。 この値は、診断やテストに便利である可能性があります。  
  
##  <a name="a-nameccomobjecta--ccomobjectccomobject"></a><a name="ccomobject"></a>CComObject::CComObject  
 コンス トラクターは、モジュールのロック カウントをインクリメントします。  
  
```
CComObject(void* = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 **void\***  
 [in]この名前のないパラメーターは使用されません。 他の対称性が存在する**ほか***XXX*`Object`*XXX*コンス トラクターです。  
  
### <a name="remarks"></a>コメント  
 デストラクターをデクリメントしています。  
  
 場合、 `CComObject`-を使用して派生オブジェクトが正常に作成、**新しい**演算子で、最初の参照カウントが 0 です。 参照カウントを適切な値 (1) に設定するには、呼び出しを行う、 [AddRef](#addref)関数です。  
  
##  <a name="a-namedtora--ccomobjectccomobject"></a><a name="dtor"></a>:: ~ と  
 デストラクターです。  
  
```
CComObject();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し、割り当てられているすべてのリソースを解放[FinalRelease](ccomobjectrootex-class.md#finalrelease)、およびモジュールのロック カウントをデクリメントします。  

  
##  <a name="a-namecreateinstancea--ccomobjectcreateinstance"></a><a name="createinstance"></a>CComObject::CreateInstance  
 この静的関数では、新しいを作成することができます**と**`Base` ** > **のオーバーヘッドなしのオブジェクト[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)します。  
  
```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pp`  
 [out]ポインター、**と**`Base` ** > **ポインター。 場合`CreateInstance`は成功せず`pp`に設定されている**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 返されるオブジェクトは、参照カウントが&0;、ためコール`AddRef`、すぐに実行して**リリース**終わったときに、オブジェクトへのポインターの参照を解放します。  
  
 必要な送信しない、オブジェクトへのアクセスが、引き続きのオーバーヘッドを生じさせずに新しいオブジェクトを作成する場合`CoCreateInstance`を使用して[あって](../../atl/reference/ccomcoclass-class.md#createinstance)代わりにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#38;](../../atl/codesnippet/cpp/ccomobject-class_1.h)]  
  
 [!code-cpp[NVC_ATL_COM&#39;](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]  
  
##  <a name="a-namequeryinterfacea--ccomobjectqueryinterface"></a><a name="queryinterface"></a>CComObject::QueryInterface  
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
  
##  <a name="a-namereleasea--ccomobjectrelease"></a><a name="release"></a>CComObject::Release  
 オブジェクトの参照カウントをデクリメントします。  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>戻り値  
 この関数は、オブジェクトの新しいデクリメント参照カウントを返します。 デバッグ ビルドでは、戻り値は診断に役立ちますやテストを使用ことがあります。 非デバッグ ビルドでは、**リリース**常に 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab)   
 [DECLARE_NOT_AGGREGATABLE](http://msdn.microsoft.com/library/2a116c7c-bab8-4f2a-a9ad-03d7aba0f762)   
 [クラスの概要](../../atl/atl-class-overview.md)

