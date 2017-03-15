---
title: "IConnectionPointImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.IConnectionPointImpl
- IConnectionPointImpl
- ATL::IConnectionPointImpl
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
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
ms.openlocfilehash: c9788496bbed3734b959d0ab4c49c89a176ea199
ms.lasthandoff: 02/24/2017

---
# <a name="iconnectionpointimpl-class"></a>IConnectionPointImpl クラス
このクラスは、接続ポイントを実装します。  
  
## <a name="syntax"></a>構文  
  
```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>  
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IConnectionPointImpl`です。  
  
 `piid`  
 コネクション ポイントのオブジェクトによって表されるインターフェイスの IID へのポインター。  
  
 `CDV`  
 接続を管理するクラスです。 既定値は[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)、無制限の接続を許可します。 使用することも[CComUnkArray](../../atl/reference/ccomunkarray-class.md)接続の数を指定します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IConnectionPointImpl::Advise](#advise)|接続ポイントとシンクの間の接続を確立します。|  
|[IConnectionPointImpl::EnumConnections](#enumconnections)|コネクション ポイントの接続を反復処理する列挙子を作成します。|  
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|接続ポイントで表されるインターフェイスの IID を取得します。|  
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|接続可能なオブジェクトへのインターフェイス ポインターを取得します。|  
|[IConnectionPointImpl::Unadvise](#unadvise)|以前に確立した接続が終了した`Advise`します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[IConnectionPointImpl::m_vec](#m_vec)|コネクション ポイントの接続を管理します。|  
  
## <a name="remarks"></a>コメント  
 `IConnectionPointImpl`クライアントへの着信インターフェイスを公開するオブジェクトを許可する接続ポイントを実装します。 クライアントは、シンクと呼ばれるオブジェクトのこのインターフェイスを実装します。  
  
 ATL では、[入力したコネクション](../../atl/reference/iconnectionpointcontainerimpl-class.md)接続可能オブジェクトを実装します。 接続可能オブジェクト内で各接続ポイントがで識別される、アウトゴーイング インターフェイスを表す`piid`します。 クラス*CDV*シンクとコネクション ポイント間の接続を管理します。 各接続は"cookie"によって一意に識別します。  
  
 ATL でのコネクション ポイントの使用に関する詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_ICPLocator`  
  
 `IConnectionPointImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-nameadvisea--iconnectionpointimpladvise"></a><a name="advise"></a>IConnectionPointImpl::Advise  
 接続ポイントとシンクの間の接続を確立します。  
  
```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```  
  
### <a name="remarks"></a>コメント  
 使用[Unadvise](#unadvise)接続通話を終了します。  
  
 参照してください[iconnectionpoint::advise](http://msdn.microsoft.com/library/windows/desktop/ms678815)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameenumconnectionsa--iconnectionpointimplenumconnections"></a><a name="enumconnections"></a>IConnectionPointImpl::EnumConnections  
 コネクション ポイントの接続を反復処理する列挙子を作成します。  
  
```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IConnectionPoint::EnumConnections](http://msdn.microsoft.com/library/windows/desktop/ms680755)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetconnectioninterfacea--iconnectionpointimplgetconnectioninterface"></a><a name="getconnectioninterface"></a>IConnectionPointImpl::GetConnectionInterface  
 接続ポイントで表されるインターフェイスの IID を取得します。  
  
```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IConnectionPoint::GetConnectionInterface](http://msdn.microsoft.com/library/windows/desktop/ms693468)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetconnectionpointcontainera--iconnectionpointimplgetconnectionpointcontainer"></a><a name="getconnectionpointcontainer"></a>IConnectionPointImpl::GetConnectionPointContainer  
 接続可能なオブジェクトへのインターフェイス ポインターを取得します。  
  
```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IConnectionPoint::GetConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms679669)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namemveca--iconnectionpointimplmvec"></a><a name="m_vec"></a>IConnectionPointImpl::m_vec  
 コネクション ポイントのオブジェクトとシンクの間の接続を管理します。  
  
```
CDV m_vec;
```     
  
### <a name="remarks"></a>コメント  
 既定では、`m_vec`型[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)します。  
  
##  <a name="a-nameunadvisea--iconnectionpointimplunadvise"></a><a name="unadvise"></a>IConnectionPointImpl::Unadvise  
 以前に確立した接続が終了した[Advise](#advise)します。  
  
```
STDMETHOD(Unadvise)(DWORD dwCookie);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)   
 [クラスの概要](../../atl/atl-class-overview.md)

