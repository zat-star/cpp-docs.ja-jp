---
title: "IPersistPropertyBagImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
dev_langs:
- C++
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: abef2ffa759cf74ee2316c7e0c9dd84f5c76b1d7
ms.lasthandoff: 03/31/2017

---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl クラス
このクラスは実装**IUnknown**でき、そのプロパティをクライアントが提供するプロパティ バッグに保存するオブジェクト。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IPersistPropertyBagImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|オブジェクトの CLSID を取得します。|  
|[IPersistPropertyBagImpl::InitNew](#initnew)|新しく作成されたオブジェクトを初期化します。 ATL の実装を返します`S_OK`です。|  
|[IPersistPropertyBagImpl::Load](#load)|クライアントが提供するプロパティ バッグからのオブジェクトのプロパティを読み込みます。|  
|[IPersistPropertyBagImpl::Save](#save)|オブジェクトのプロパティは、クライアントが提供するプロパティ バッグに保存されます。|  
  
## <a name="remarks"></a>コメント  
 [IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx)インターフェイスにより、そのプロパティをクライアントが提供するプロパティ バッグに保存するオブジェクト。 クラス`IPersistPropertyBagImpl`このインターフェイスの既定の実装を提供し、実装**IUnknown**ダンプ情報を送信することによってデバッグ デバイスのビルドします。  
  
 **IPersistPropertyBag**と連携して[IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx)と[IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx)です。 クライアントによって後者 2 つのインターフェイスを実装する必要があります。 を通じて`IPropertyBag`クライアントを保存し、オブジェクトの個々 のプロパティを読み込みます。 を通じて**IErrorLog**オブジェクトとクライアントの両方が発生したエラーを報告できます。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getclassid"></a>IPersistPropertyBagImpl::GetClassID  
 オブジェクトの CLSID を取得します。  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="initnew"></a>IPersistPropertyBagImpl::InitNew  
 新しく作成されたオブジェクトを初期化します。  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="load"></a>IPersistPropertyBagImpl::Load  
 クライアントが提供するプロパティ バッグからのオブジェクトのプロパティを読み込みます。  
  
```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```  
  
### <a name="remarks"></a>コメント  
 ATL では、オブジェクトのプロパティ マップを使用して、この情報を取得します。  
  
 参照してください[IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="save"></a>IPersistPropertyBagImpl::Save  
 オブジェクトのプロパティは、クライアントが提供するプロパティ バッグに保存されます。  
  
```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```  
  
### <a name="remarks"></a>コメント  
 ATL は、この情報を格納するのにオブジェクトのプロパティ マップを使用します。 既定では、このメソッドの値に関係なく、すべてのプロパティを保存*fSaveAllProperties*です。  
  
 参照してください[IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [あり、その場合](property-map-macros.md#begin_prop_map)   
 [クラスの概要](../../atl/atl-class-overview.md)

