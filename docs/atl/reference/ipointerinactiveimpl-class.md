---
title: "IPointerInactiveImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPointerInactiveImpl
dev_langs:
- C++
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
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
ms.openlocfilehash: 05cf4b2247cabe713cfc6b0dd54c95c01e5bbddc
ms.lasthandoff: 02/24/2017

---
# <a name="ipointerinactiveimpl-class"></a>IPointerInactiveImpl クラス
このクラスは実装**IUnknown**と[IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712)インターフェイスのメソッドです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class IPointerInactiveImpl
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IPointerInactiveImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|オブジェクトの現在のアクティブ化ポリシーを取得します。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|マウス ポインターが上に移動されたオブジェクトを示すオブジェクトは、マウス イベントを発生させることを通知します。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|アクティブでないオブジェクトにマウス ポインターを設定します。 ATL の実装を返します**E_NOTIMPL**します。|  
  
## <a name="remarks"></a>コメント  
 非アクティブなオブジェクトが単に読み込まれたか実行されているいずれかです。 アクティブでないオブジェクトは、アクティブなオブジェクトとは異なり、Windows のマウスとキーボードのメッセージを取得できません。 したがって、アクティブでないオブジェクトはより少ないリソースを使用して、通常は効率的な。  
  
 [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712)インターフェイスが非アクティブなままマウスとの対話の最小レベルをサポートするためにオブジェクトを許可します。 この機能は、コントロールに特に便利です。  
  
 クラス`IPointerInactiveImpl`を実装して、`IPointerInactive`メソッドを返すだけで**E_NOTIMPL**します。 ただしを実装して**IUnknown**ダンプ情報を送信することによってデバッグでデバイスをビルドします。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPointerInactive`  
  
 `IPointerInactiveImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="a-namegetactivationpolicya--ipointerinactiveimplgetactivationpolicy"></a><a name="getactivationpolicy"></a>IPointerInactiveImpl::GetActivationPolicy  
 オブジェクトの現在のアクティブ化ポリシーを取得します。  
  
```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPointerInactive::GetActivationPolicy](http://msdn.microsoft.com/library/windows/desktop/ms692470)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameoninactivemousemovea--ipointerinactiveimploninactivemousemove"></a><a name="oninactivemousemove"></a>IPointerInactiveImpl::OnInactiveMouseMove  
 マウス ポインターが上に移動されたオブジェクトを示すオブジェクトは、マウス イベントを発生させることを通知します。  
  
```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPointerInactive::OnInactiveMouseMove](http://msdn.microsoft.com/library/windows/desktop/ms693374)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameoninactivesetcursora--ipointerinactiveimploninactivesetcursor"></a><a name="oninactivesetcursor"></a>IPointerInactiveImpl::OnInactiveSetCursor  
 アクティブでないオブジェクトにマウス ポインターを設定します。  
  
```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPointerInactive::OnInactiveSetCursor](http://msdn.microsoft.com/library/windows/desktop/ms694336)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

