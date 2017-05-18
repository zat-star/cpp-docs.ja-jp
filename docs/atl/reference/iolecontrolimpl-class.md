---
title: "IOleControlImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
dev_langs:
- C++
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5e63849a504b931de30141dd91af557f16c67fd8
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl クラス
このクラスの既定の実装を提供する、 **IOleControl**インターフェイスと実装**IUnknown**します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class IOleControlImpl
```   
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IOleControlImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IOleControlImpl::FreezeEvents](#freezeevents)|コンテナーを無視するか、コントロールからのイベントを受け入れるかどうかを示します。|  
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|コントロールのキーボード動作に関する情報が表示されます。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|1 つ以上のコンテナーのアンビエント プロパティが変更されたことをコントロールに通知します。 ATL の実装を返します`S_OK`します。|  
|[IOleControlImpl::OnMnemonic](#onmnemonic)|ユーザーが特定のキーを押したことをコントロールに通知します。 ATL の実装を返します**E_NOTIMPL**します。|  
  
## <a name="remarks"></a>コメント  
 クラス`IOleControlImpl`の既定の実装を提供、 [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320)インターフェイスと実装**IUnknown**ダンプ情報を送信することによってデバッグでデバイスをビルドします。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="freezeevents"></a>IOleControlImpl::FreezeEvents  
 ATL の実装で`FreezeEvents`コントロール クラスのインクリメント`m_nFreezeEvents`データ メンバー場合`bFreeze`は**TRUE**、およびデクリメント`m_nFreezeEvents`場合`bFreeze`は**FALSE**します。  
  
```
HRESULT FreezeEvents(BOOL bFreeze);
```  
  
### <a name="remarks"></a>コメント  
 `FreezeEvents`戻ります`S_OK`します。  
  
 参照してください[IOleControl::FreezeEvents](http://msdn.microsoft.com/library/windows/desktop/ms678482)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getcontrolinfo"></a>IOleControlImpl::GetControlInfo  
 コントロールのキーボード動作に関する情報が表示されます。  
  
```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleControl:GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
##  <a name="onambientpropertychange"></a>IOleControlImpl::OnAmbientPropertyChange  
 1 つ以上のコンテナーのアンビエント プロパティが変更されたことをコントロールに通知します。  
  
```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleControl::OnAmbientPropertyChange](http://msdn.microsoft.com/library/windows/desktop/ms690175)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="onmnemonic"></a>IOleControlImpl::OnMnemonic  
 ユーザーが特定のキーを押したことをコントロールに通知します。  
  
```
HRESULT OnMnemonic(LPMSG pMsg);
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleControl::OnMnemonic](http://msdn.microsoft.com/library/windows/desktop/ms680699)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [IOleObjectImpl クラス](../../atl/reference/ioleobjectimpl-class.md)   
 [ActiveX コントロールのインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [クラスの概要](../../atl/atl-class-overview.md)

