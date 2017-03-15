---
title: "IPerPropertyBrowsingImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.IPerPropertyBrowsingImpl
- IPerPropertyBrowsing
- ATL::IPerPropertyBrowsingImpl
- ATL::IPerPropertyBrowsingImpl<T>
- IPerPropertyBrowsingImpl
- ATL.IPerPropertyBrowsingImpl<T>
dev_langs:
- C++
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
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
ms.openlocfilehash: 8f2c2016a83cad906be22183fcffa20ae3da3042
ms.lasthandoff: 02/24/2017

---
# <a name="iperpropertybrowsingimpl-class"></a>IPerPropertyBrowsingImpl クラス
このクラスは実装**IUnknown**により、クライアントは、オブジェクトのプロパティ ページの情報にアクセスするとします。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IPerPropertyBrowsingImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|指定したプロパティを説明する文字列を取得します。|  
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|指定したプロパティが受け入れられる値に対応する文字列の配列を取得します。|  
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|取得、 **VARIANT**特定 DISPID で識別されるプロパティの値を格納します。 取得した文字列の名前を持つように DISPID が関連付けられている`GetPredefinedStrings`します。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|指定したプロパティに関連付けられたプロパティ ページの CLSID を取得します。|  
  
## <a name="remarks"></a>コメント  
 [IPerPropertyBrowsing](http://msdn.microsoft.com/library/windows/desktop/ms678432)インターフェイスにより、クライアントは、オブジェクトのプロパティ ページの情報にアクセスします。 クラス`IPerPropertyBrowsingImpl`このインターフェイスの既定の実装を提供しを実装する**IUnknown**ダンプ情報を送信することによってデバッグでデバイスをビルドします。  
  
> [!NOTE]
>  クラスを派生させる必要がありますコンテナー アプリケーションとして Microsoft Access を使用している場合`IPerPropertyBrowsingImpl`します。 それ以外の場合、アクセスは、コントロールを読み込めません。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPerPropertyBrowsing`  
  
 `IPerPropertyBrowsingImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="a-namegetdisplaystringa--iperpropertybrowsingimplgetdisplaystring"></a><a name="getdisplaystring"></a>IPerPropertyBrowsingImpl::GetDisplayString  
 指定したプロパティを説明する文字列を取得します。  
  
```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPerPropertyBrowsing::GetDisplayString](http://msdn.microsoft.com/library/windows/desktop/ms688734)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetpredefinedstringsa--iperpropertybrowsingimplgetpredefinedstrings"></a><a name="getpredefinedstrings"></a>IPerPropertyBrowsingImpl::GetPredefinedStrings  
 各配列項目数を&0; に設定します。  
  
```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```  
  
### <a name="return-value"></a>戻り値  
 ATL の実装の[GetPredefinedValue](#getpredefinedvalue)返します**E_NOTIMPL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPerPropertyBrowsing::GetPredefinedStrings](http://msdn.microsoft.com/library/windows/desktop/ms679724)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetpredefinedvaluea--iperpropertybrowsingimplgetpredefinedvalue"></a><a name="getpredefinedvalue"></a>IPerPropertyBrowsingImpl::GetPredefinedValue  
 取得、 **VARIANT**特定 DISPID で識別されるプロパティの値を格納します。 取得した文字列の名前を持つように DISPID が関連付けられている`GetPredefinedStrings`します。  
  
```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
### <a name="remarks"></a>コメント  
 ATL の実装の[GetPredefinedStrings](#getpredefinedstrings)対応する文字列が取得されません。  
  
 参照してください[IPerPropertyBrowsing::GetPredefinedValue](http://msdn.microsoft.com/library/windows/desktop/ms690401)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namemappropertytopagea--iperpropertybrowsingimplmappropertytopage"></a><a name="mappropertytopage"></a>IPerPropertyBrowsingImpl::MapPropertyToPage  
 指定したプロパティに関連付けられたプロパティ ページの CLSID を取得します。  
  
```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```  
  
### <a name="remarks"></a>コメント  
 ATL では、オブジェクトのプロパティ マップを使用して、この情報を取得します。  
  
 参照してください[IPerPropertyBrowsing::MapPropertyToPage](http://msdn.microsoft.com/library/windows/desktop/ms694476)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [IPropertyPageImpl クラス](../../atl/reference/ipropertypageimpl-class.md)   
 [ISpecifyPropertyPagesImpl クラス](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

