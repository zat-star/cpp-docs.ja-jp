---
title: "IObjectWithSiteImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
dev_langs:
- C++
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
caps.latest.revision: 18
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
ms.openlocfilehash: 49c52810417650c3d80fe4d0c09ccb2b67208ad4
ms.lasthandoff: 02/24/2017

---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl クラス
このクラスは、オブジェクトのサイトと通信するようにするメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IObjectWithSiteImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IObjectWithSiteImpl::GetSite](#getsite)|インターフェイス ポインターのサイトを照会します。|  
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|オブジェクトは、サイトの**IUnknown**ポインター。|  
|[IObjectWithSiteImpl::SetSite](#setsite)|オブジェクトは、サイトの**IUnknown**ポインター。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|サイトの管理**IUnknown**ポインター。|  
  
## <a name="remarks"></a>コメント  
 [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765)インターフェイスは、オブジェクトをサイトとの通信を許可します。 クラス`IObjectWithSiteImpl`このインターフェイスの既定の実装を提供しを実装する**IUnknown**ダンプ情報を送信することによってデバッグでデバイスをビルドします。  
  
 `IObjectWithSiteImpl`2 つの方法を指定します。 クライアントの最初の呼び出し`SetSite`、サイトを渡す**IUnknown**ポインター。 このポインターが、オブジェクト内では格納されを呼び出すことによって取得できます`GetSite`します。  
  
 通常、クラスを派生させるから`IObjectWithSiteImpl`するオブジェクトを作成する場合は、そのコントロールではありません。 コントロールの派生クラスから[IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)サイトへのポインターも提供します。 両方のクラスを派生できません`IObjectWithSiteImpl`と`IOleObjectImpl`です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getsite"></a>IObjectWithSiteImpl::GetSite  
 サイトで識別されるインターフェイスへのポインターに問い合わせます`riid`します。  
  
```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```  
  
### <a name="remarks"></a>コメント  
 サイトでは、このインターフェイスをサポートする場合を使用して、ポインターが返されます。`ppvSite`します。 それ以外の場合、`ppvSite`に設定されている**NULL**します。  
  
 参照してください[IObjectWithSite::GetSite](http://msdn.microsoft.com/library/windows/desktop/ms694452)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="m_spunksite"></a>IObjectWithSiteImpl::m_spUnkSite  
 サイトの管理**IUnknown**ポインター。  
  
```
CComPtr<IUnknown> m_spUnkSite;
```  
  
### <a name="remarks"></a>コメント  
 `m_spUnkSite`呼び出すことによってこのポインターを最初に受信[SetSite](#setsite)します。  
  
##  <a name="setchildsite"></a>IObjectWithSiteImpl::SetChildSite  
 オブジェクトは、サイトの**IUnknown**ポインター。  
  
```
HRESULT SetChildSite(IUnknown* pUnkSite);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnkSite*  
 [in]ポインター、 **IUnknown**このオブジェクトを管理するサイトのインターフェイス ポインター。 NULL の場合、オブジェクトを呼び出す必要があります`IUnknown::Release`この時点でオブジェクトいいえを認識できなくなり、サイトの既存のサイトにします。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
##  <a name="setsite"></a>IObjectWithSiteImpl::SetSite  
 オブジェクトは、サイトの**IUnknown**ポインター。  
  
```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

