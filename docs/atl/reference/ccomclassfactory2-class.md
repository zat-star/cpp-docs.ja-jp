---
title: "CComClassFactory2 クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComClassFactory2<license>
- CComClassFactory2
- ATL.CComClassFactory2<license>
- ATL::CComClassFactory2
- ATL.CComClassFactory2
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 3787214d5479e1cd57295c9c25335e87651a16bb
ms.lasthandoff: 02/24/2017

---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2 クラス
このクラスは、実装、 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720)インターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
template <class license>  
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```  
  
#### <a name="parameters"></a>パラメーター  
 *ライセンス*  
 次の静的関数を実装するクラス。  
  
- **静的な BOOL VerifyLicenseKey (BSTR** `bstr` **) です。**  
  
- **静的な BOOL GetLicenseKey (DWORD** `dwReserved` **、BSTR\* ** `pBstr` **) です。**  
  
- **静的な BOOL IsLicenseValid ();**  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComClassFactory2::CreateInstance](#createinstance)|指定された CLSID のオブジェクトを作成します。|  
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|ライセンス キーでは、指定された CLSID のオブジェクトを作成します。|  
|[CComClassFactory2::GetLicInfo](#getlicinfo)|クラス ファクトリのライセンスの機能を説明する情報を取得します。|  
|[CComClassFactory2::LockServer](#lockserver)|メモリ内のクラス ファクトリをロックします。|  
|[CComClassFactory2::RequestLicKey](#requestlickey)|作成して、ライセンス キーを返します。|  
  
## <a name="remarks"></a>コメント  
 `CComClassFactory2`実装して、 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720)拡張機能であるインターフェイスの[IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)します。 **IClassFactory2**コントロール オブジェクトを介して、ライセンスを作成します。 ライセンスのあるコンピューターで実行するクラス ファクトリと、ランタイム ライセンス キーを指定できます。 このライセンス キーには、コンピューターのフル ライセンスが存在しないときにオブジェクトをインスタンス化するアプリケーションことができます。  
  
 ATL オブジェクトから派生することにより、クラス ファクトリを通常取得[示す](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4)、宣言[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 使用する`CComClassFactory2`、指定、 [DECLARE_CLASSFACTORY2](http://msdn.microsoft.com/library/38a6c969-7297-4bb1-9ba6-1fe2d355b285)オブジェクトのクラスの定義でマクロです。 例:  
  
 [!code-cpp[NVC_ATL_COM&2;](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]  
  
 **CMyLicense**、テンプレート パラメーターを`CComClassFactory2`、静的関数を実装する必要があります`VerifyLicenseKey`、 `GetLicenseKey`、および`IsLicenseValid`です。 簡単なライセンス クラスの例を次に示します。  
  
 [!code-cpp[NVC_ATL_COM&3;](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]  
  
 `CComClassFactory2`2 つの派生**CComClassFactory2Base**と*ライセンス*します。 **CComClassFactory2Base**から派生、 **IClassFactory2**と**CComObjectRootEx\< CComGlobalsThreadModel >**します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 `license`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory2`  
  
 `CComClassFactory2`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-namecreateinstancea--ccomclassfactory2createinstance"></a><a name="createinstance"></a>CComClassFactory2::CreateInstance  
 指定された CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。  
  
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
  
### <a name="remarks"></a>コメント  
 完全にライセンスを取得するマシンが必要です。 コンピューターのフル ライセンスが存在しない場合に呼び出す[取得していない](#createinstancelic)します。  
  
##  <a name="a-namecreateinstancelica--ccomclassfactory2createinstancelic"></a><a name="createinstancelic"></a>CComClassFactory2::CreateInstanceLic  
 ような[CreateInstance](#createinstance)する点を除いて、`CreateInstanceLic`ライセンス キーが必要です。  
  
```
STDMETHOD(CreateInstanceLic)(
    IUnknown* pUnkOuter,
    IUnknown* /* pUnkReserved
 */,
    REFIID riid,
    BSTR bstrKey,
    void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkOuter`  
 [in]オブジェクトが作成されるかどうか、集計の一部として、`pUnkOuter`外側の不明な使用する必要があります。 それ以外の場合、`pUnkOuter`する必要があります**NULL**します。  
  
 *pUnkReserved*  
 [in]使用しません。 必要があります**NULL**します。  
  
 `riid`  
 [in]要求されたインターフェイスの IID です。 場合`pUnkOuter`以外は、 **NULL**、`riid`する必要があります**IID_IUnknown**します。  
  
 `bstrKey`  
 [in]実行時のライセンス キーが以前に取得する呼び出しから`RequestLicKey`します。 オブジェクトを作成するには、このキーが必要です。  
  
 `ppvObject`  
 [out]指定されたインターフェイス ポインターへのポインター`riid`します。 オブジェクトがこのインターフェイスをサポートしていない場合`ppvObject`に設定されている**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ライセンス キーを使用して、取得できます[RequestLicKey](#requestlickey)します。 ライセンスされていないコンピューター上のオブジェクトを作成するために呼び出す必要があります`CreateInstanceLic`します。  
  
##  <a name="a-namegetlicinfoa--ccomclassfactory2getlicinfo"></a><a name="getlicinfo"></a>CComClassFactory2::GetLicInfo  
 入力、 [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590)クラス ファクトリを記述する情報を含む構造体の機能のライセンスします。  
  
```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 *pLicInfo*  
 [out]ポインター、 **LICINFO**構造体。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 `fRuntimeKeyAvail`この構造体のメンバーができるかどうか、ライセンス キーを指定するには、クラス ファクトリ オブジェクトをライセンスされていないコンピューターで作成できることを示します。 *FLicVerified*メンバーは、コンピューターのフル ライセンスが存在するかどうかを示します。  
  
##  <a name="a-namelockservera--ccomclassfactory2lockserver"></a><a name="lockserver"></a>CComClassFactory2::LockServer  
 インクリメントおよびデクリメント モジュールのロックを呼び出すことによってカウント**_Module::Lock**と**_Module::Unlock**、それぞれします。  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>パラメーター  
 `fLock`  
 [in]場合**TRUE**ロック数がインクリメントされます。 それ以外の場合、ロック カウントがデクリメントします。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 **_Module**のグローバル インスタンスを指す[CComModule](../../atl/reference/ccommodule-class.md)またはその派生クラスです。  
  
 呼び出す`LockServer`クライアントは、複数のオブジェクトをすばやく作成できるように、クラス ファクトリを保持できます。  
  
##  <a name="a-namerequestlickeya--ccomclassfactory2requestlickey"></a><a name="requestlickey"></a>CComClassFactory2::RequestLicKey  
 作成しているライセンス キーを返します、`fRuntimeKeyAvail`のメンバー、 [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590)構造体は**TRUE**します。  
  
```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwReserved`  
 [in]使用しません。 ゼロを指定してください。  
  
 `pbstrKey`  
 [out]ライセンス キーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 呼び出し元にライセンス キーが必要[取得していない](#createinstancelic)ライセンスされていないコンピューター上のオブジェクトを作成します。 場合`fRuntimeKeyAvail`は**FALSE**オブジェクトは完全なライセンスのマシンでのみ作成されます。  
  
 呼び出す[GetLicInfo](#getlicinfo)の値を取得する`fRuntimeKeyAvail`です。  
  
## <a name="see-also"></a>関連項目  
 [CComClassFactoryAutoThread クラス](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComClassFactorySingleton クラス](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [クラスの概要](../../atl/atl-class-overview.md)

