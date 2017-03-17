---
title: "CAnimationVariableChangeHandler クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariableChangeHandler class
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 46c4eb9210b69c527375b12100ab7cc22fef0176
ms.lasthandoff: 02/24/2017

---
# <a name="canimationvariablechangehandler-class"></a>CAnimationVariableChangeHandler クラス
アニメーション変数の値が変化したときに Animation API によって呼び出されるコールバックを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|
          `CAnimationVariableChangeHandler` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CAnimationVariableChangeHandler::CreateInstance`|インスタンスを作成`CAnimationVariableChangeHandler`オブジェクトです。|  
|[CAnimationVariableChangeHandler::OnValueChanged](#onvaluechanged)|アニメーション変数の値が変更されたときに呼び出されます。 (`CUIAnimationVariableChangeHandlerBase::OnValueChanged` をオーバーライドします)。|  
|[CAnimationVariableChangeHandler::SetAnimationController](#setanimationcontroller)|イベントをルーティングするアニメーション コント ローラーへのポインターを格納します。|  
  
## <a name="remarks"></a>コメント  
 このイベント ハンドラーを作成してに渡す`IUIAnimationVariable::SetVariableChangeHandler`メソッドを呼び出すときに`CAnimationVariable::EnableValueChangedEvent`または`CAnimationBaseObject::EnableValueChangedEvent`(アニメーション オブジェクトにカプセル化されたすべてのアニメーション変数にこのイベントできます)。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableChangeHandlerBase`  
  
 `CAnimationVariableChangeHandler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="onvaluechanged"></a>CAnimationVariableChangeHandler::OnValueChanged  
 アニメーション変数の値が変更されたときに呼び出されます。  
  
```  
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `storyboard`  
 変数がアニメーション化するストーリー ボードです。  
  
 `variable`  
 更新されたアニメーション変数です。  
  
 `newValue`  
 新しい値。  
  
 `previousValue`  
 前の値。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="setanimationcontroller"></a>CAnimationVariableChangeHandler::SetAnimationController  
 イベントをルーティングするアニメーション コント ローラーへのポインターを格納します。  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>パラメーター  
 `pAnimationController`  
 イベントを受信するアニメーション コント ローラーへのポインター。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

