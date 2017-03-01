---
title: "IPersistStreamInitImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IPersistStreamInitImpl
- ATL::IPersistStreamInitImpl<T>
- ATL.IPersistStreamInitImpl<T>
- IPersistStreamInitImpl
- ATL.IPersistStreamInitImpl
dev_langs:
- C++
helpviewer_keywords:
- IPersistStreamInit ATL implementation
- IPersistStreamInitImpl class
- streams, ATL
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
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
ms.openlocfilehash: aa8427a891ac8d8e18ec7794a12e838a55bc23c8
ms.lasthandoff: 02/24/2017

---
# <a name="ipersiststreaminitimpl-class"></a>IPersistStreamInitImpl クラス
このクラスは実装**IUnknown**の既定の実装を提供し、 [ipersiststreaminit など](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE IPersistStreamInitImpl 
   : public IPersistStreamInit
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IPersistStreamInitImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPersistStreamInitImpl::GetClassID](#getclassid)|オブジェクトの CLSID を取得します。|  
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|オブジェクトのデータを保存するために必要なストリームのサイズを取得します。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IPersistStreamInitImpl::InitNew](#initnew)|新しく作成されたオブジェクトを初期化します。|  
|[IPersistStreamInitImpl::IsDirty](#isdirty)|最後に保存されてから、オブジェクトのデータが変更されたかどうかを確認します。|  
|[IPersistStreamInitImpl::Load](#load)|オブジェクトのプロパティを指定したストリームから読み込みます。|  
|[IPersistStreamInitImpl::Save](#save)|オブジェクトのプロパティを指定したストリームに保存します。|  
  
## <a name="remarks"></a>コメント  
 [Ipersiststreaminit など](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイスにより、クライアントは、オブジェクトの読み込みおよびを&1; つのストリームに永続的なデータを保存を要求します。 クラス`IPersistStreamInitImpl`このインターフェイスの既定の実装を提供しを実装する**IUnknown**ダンプ情報を送信することによってデバッグでデバイスをビルドします。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPersistStreamInit`  
  
 `IPersistStreamInitImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-namegetclassida--ipersiststreaminitimplgetclassid"></a><a name="getclassid"></a>IPersistStreamInitImpl::GetClassID  
 オブジェクトの CLSID を取得します。  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetsizemaxa--ipersiststreaminitimplgetsizemax"></a><a name="getsizemax"></a>IPersistStreamInitImpl::GetSizeMax  
 オブジェクトのデータを保存するために必要なストリームのサイズを取得します。  
  
```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersistStreamInit::GetSizeMax](http://msdn.microsoft.com/library/windows/desktop/ms687287)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameinitnewa--ipersiststreaminitimplinitnew"></a><a name="initnew"></a>IPersistStreamInitImpl::InitNew  
 新しく作成されたオブジェクトを初期化します。  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersistStreamInit::InitNew](http://msdn.microsoft.com/library/windows/desktop/ms690234)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameisdirtya--ipersiststreaminitimplisdirty"></a><a name="isdirty"></a>IPersistStreamInitImpl::IsDirty  
 最後に保存されてから、オブジェクトのデータが変更されたかどうかを確認します。  
  
```
STDMETHOD(IsDirty)();
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersistStreamInit::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms680092)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameloada--ipersiststreaminitimplload"></a><a name="load"></a>IPersistStreamInitImpl::Load  
 オブジェクトのプロパティを指定したストリームから読み込みます。  
  
```
STDMETHOD(Load)(LPSTREAM pStm);
```  
  
### <a name="remarks"></a>コメント  
 ATL では、オブジェクトのプロパティ マップを使用して、この情報を取得します。  
  
 参照してください[IPersistStreamInit::Load](http://msdn.microsoft.com/library/windows/desktop/ms680730)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesavea--ipersiststreaminitimplsave"></a><a name="save"></a>IPersistStreamInitImpl::Save  
 オブジェクトのプロパティを指定したストリームに保存します。  
  
```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```  
  
### <a name="remarks"></a>コメント  
 ATL では、オブジェクトのプロパティ マップを使用して、この情報を格納します。  
  
 参照してください[IPersistStreamInit::Save](http://msdn.microsoft.com/library/windows/desktop/ms694439)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [記憶域とストリーム](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [クラスの概要](../../atl/atl-class-overview.md)

