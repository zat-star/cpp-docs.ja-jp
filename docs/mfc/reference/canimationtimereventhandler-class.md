---
title: "CAnimationTimerEventHandler クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationTimerEventHandler class
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 5412c215caf85440e923e8a083ed310f8960849a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="canimationtimereventhandler-class"></a>CAnimationTimerEventHandler クラス
タイミング イベントの発生時に Animation API によって呼び出されるコールバックを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationTimerEventHandler::CreateInstance](#createinstance)|インスタンスを作成`CAnimationTimerEventHandler`コールバックします。|  
|[CAnimationTimerEventHandler::OnPostUpdate](#onpostupdate)|アニメーション更新が完了した後に発生するイベントを処理します。 (`CUIAnimationTimerEventHandlerBase::OnPostUpdate` をオーバーライドします)。|  
|[CAnimationTimerEventHandler::OnPreUpdate](#onpreupdate)|アニメーションの更新が始まる前に発生するイベントを処理します。 (`CUIAnimationTimerEventHandlerBase::OnPreUpdate` をオーバーライドします)。|  
|[CAnimationTimerEventHandler::OnRenderingTooSlow](#onrenderingtooslow)|アニメーションのレンダリングのフレーム レートが最小の望ましいフレーム レートを下回った場合に発生するイベントを処理します。 (`CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow` をオーバーライドします)。|  
|[CAnimationTimerEventHandler::SetAnimationController](#setanimationcontroller)|イベントをルーティングするアニメーション コント ローラーへのポインターを格納します。|  
  
## <a name="remarks"></a>コメント  
 このイベント ハンドラーが作成され、CAnimationController::EnableAnimationTimerEventHandler を呼び出すときに、IUIAnimationTimer::SetTimerEventHandler に渡されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationTimerEventHandlerBase`  
  
 `CAnimationTimerEventHandler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="createinstance"></a>CAnimationTimerEventHandler::CreateInstance  
 CAnimationTimerEventHandler コールバックのインスタンスを作成します。  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```  
  
### <a name="parameters"></a>パラメーター  
 `pAnimationController`  
 イベントを受信するアニメーション コント ローラーへのポインター。  
  
 `ppTimerEventHandler`  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="onpostupdate"></a>CAnimationTimerEventHandler::OnPostUpdate  
 アニメーション更新が完了した後に発生するイベントを処理します。  
  
```  
IFACEMETHOD(OnPostUpdate)();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OKそれ以外の場合 E_FAIL します。  
  
##  <a name="onpreupdate"></a>CAnimationTimerEventHandler::OnPreUpdate  
 アニメーションの更新が始まる前に発生するイベントを処理します。  
  
```  
IFACEMETHOD(OnPreUpdate)();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OKそれ以外の場合 E_FAIL します。  
  
##  <a name="onrenderingtooslow"></a>CAnimationTimerEventHandler::OnRenderingTooSlow  
 アニメーションのレンダリングのフレーム レートが最小の望ましいフレーム レートを下回った場合に発生するイベントを処理します。  
  
```  
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```  
  
### <a name="parameters"></a>パラメーター  
 `fps`  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OKそれ以外の場合 E_FAIL します。  
  
##  <a name="setanimationcontroller"></a>CAnimationTimerEventHandler::SetAnimationController  
 イベントをルーティングするアニメーション コント ローラーへのポインターを格納します。  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>パラメーター  
 `pAnimationController`  
 イベントを受信するアニメーション コント ローラーへのポインター。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

