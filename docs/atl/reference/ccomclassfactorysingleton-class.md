---
title: "CComClassFactorySingleton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComClassFactorySingleton
- ATL.CComClassFactorySingleton<T>
- ATL::CComClassFactorySingleton
- ATL::CComClassFactorySingleton<T>
- CComClassFactorySingleton
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 7ff6f3a9d00c0f579077d9502aefad5cbea35f17
ms.lasthandoff: 02/24/2017

---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton クラス
このクラスから派生[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を&1; つのオブジェクトを構築します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class CComClassFactorySingleton : public CComClassFactory
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 作成したクラス。  
  
 `CComClassFactorySingleton`派生した[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を&1; つのオブジェクトを構築します。 呼び出すたび、`CreateInstance`メソッドは、単にインターフェイス ポインターに対して、このオブジェクトを照会します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComClassFactorySingleton::CreateInstance](#createinstance)|クエリ`m_spObj`にインターフェイス ポインター。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComClassFactorySingleton::m_spObj](#m_spobj)|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)によって構築されたオブジェクト`CComClassFactorySingleton`します。|  
  
## <a name="remarks"></a>コメント  
 ATL オブジェクトから派生することにより、クラス ファクトリを通常取得[示す](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4)、宣言`CComClassFactory`既定のクラス ファクトリとして。 使用する`CComClassFactorySingleton`、指定、 [DECLARE_CLASSFACTORY_SINGLETON](http://msdn.microsoft.com/library/0e4a3964-c03d-463e-884c-fe3b416db478)オブジェクトのクラスの定義でマクロです。 例:  
  
 [!code-cpp[NVC_ATL_COM&#10;](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)  
  
 `CComClassFactorySingleton`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-namecreateinstancea--ccomclassfactorysingletoncreateinstance"></a><a name="createinstance"></a>CComClassFactorySingleton::CreateInstance  
 呼び出し`QueryInterface`を通じて[m_spObj](#m_spobj)インターフェイス ポインターを取得します。  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkOuter`  
 [in]オブジェクトが作成されるかどうか、集計の一部として、`pUnkOuter`外側の不明な使用する必要があります。 それ以外の場合、`pUnkOuter`する必要があります**NULL**します。  
  
 `riid`  
 [in]要求されたインターフェイスの IID です。 場合`pUnkOuter`以外は、 **NULL**、`riid`する必要があります**IID_IUnknown**します。  
  
 `ppvObj`  
 [out]によって識別されるインターフェイス ポインターへのポインター`riid`します。 オブジェクトがこのインターフェイスをサポートしていない場合`ppvObj`に設定されている**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="a-namemspobja--ccomclassfactorysingletonmspobj"></a><a name="m_spobj"></a>CComClassFactorySingleton::m_spObj  
 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)によって構築されたオブジェクト`CComClassFactorySingleton`します。  
  
```
CComPtr<IUnknown> m_spObj;
```  
  
### <a name="remarks"></a>コメント  
 呼び出すたび、 [CreateInstance](#createinstance)メソッドは、単にインターフェイス ポインターに対して、このオブジェクトを照会します。  
  
 注意の現在のフォーム`m_spObj`方法から重大な変更を表示する`CComClassFactorySingleton`ATL の以前のバージョンで動作していた 以前のバージョンで、`CComClassFactorySingleton`オブジェクトは、サーバーの初期化中にクラス ファクトリと同時に作成されました。 Visual c .NET 2003年では、最初の要求で、オブジェクトが遅延、作成します。 この変更の初期化に依存するプログラムでエラーが発生する可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 クラス](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactoryAutoThread クラス](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [クラスの概要](../../atl/atl-class-overview.md)

