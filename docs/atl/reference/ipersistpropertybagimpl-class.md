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
- ATL.IPersistPropertyBagImpl<T>
- ATL::IPersistPropertyBagImpl
- ATL::IPersistPropertyBagImpl<T>
- ATL.IPersistPropertyBagImpl
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 901a6a6bf4097b6aa78a898254766f122bb2f959
ms.lasthandoff: 02/24/2017

---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl クラス
このクラスは実装**IUnknown**でき、そのプロパティをクライアントが指定したプロパティ バッグに保存するオブジェクト。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IPersistPropertyBagImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|オブジェクトの CLSID を取得します。|  
|[IPersistPropertyBagImpl::InitNew](#initnew)|新しく作成されたオブジェクトを初期化します。 ATL の実装を返します`S_OK`します。|  
|[IPersistPropertyBagImpl::Load](#load)|クライアントが提供するプロパティ バッグからのオブジェクトのプロパティを読み込みます。|  
|[IPersistPropertyBagImpl::Save](#save)|オブジェクトのプロパティをクライアントが指定したプロパティ バッグに保存します。|  
  
## <a name="remarks"></a>コメント  
 [IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx)インターフェイスにより、オブジェクトのプロパティをクライアントが指定したプロパティ バッグに保存できます。 クラス`IPersistPropertyBagImpl`このインターフェイスの既定の実装を提供しを実装する**IUnknown**ダンプ情報を送信することによってデバッグでデバイスをビルドします。  
  
 **IPersistPropertyBag**と組み合わせて動作[IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx)と[IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx)します。 これら後者の&2; つのインターフェイスは、クライアントによって実装する必要があります。 を通じて`IPropertyBag`クライアントは、保存し、オブジェクトの個々 のプロパティを読み込みます。 を通じて**IErrorLog**オブジェクトとクライアントの両方が発生するエラーを報告できます。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-namegetclassida--ipersistpropertybagimplgetclassid"></a><a name="getclassid"></a>IPersistPropertyBagImpl::GetClassID  
 オブジェクトの CLSID を取得します。  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameinitnewa--ipersistpropertybagimplinitnew"></a><a name="initnew"></a>IPersistPropertyBagImpl::InitNew  
 新しく作成されたオブジェクトを初期化します。  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameloada--ipersistpropertybagimplload"></a><a name="load"></a>IPersistPropertyBagImpl::Load  
 クライアントが提供するプロパティ バッグからのオブジェクトのプロパティを読み込みます。  
  
```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```  
  
### <a name="remarks"></a>コメント  
 ATL では、オブジェクトのプロパティ マップを使用して、この情報を取得します。  
  
 参照してください[IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesavea--ipersistpropertybagimplsave"></a><a name="save"></a>IPersistPropertyBagImpl::Save  
 オブジェクトのプロパティをクライアントが指定したプロパティ バッグに保存します。  
  
```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```  
  
### <a name="remarks"></a>コメント  
 ATL では、オブジェクトのプロパティ マップを使用して、この情報を格納します。 このメソッドは既定では、値に関係なく、すべてのプロパティを保存*fSaveAllProperties*します。  
  
 参照してください[IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [あり、その場合](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427)   
 [クラスの概要](../../atl/atl-class-overview.md)

