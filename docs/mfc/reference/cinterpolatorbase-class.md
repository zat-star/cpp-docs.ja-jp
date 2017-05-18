---
title: "CInterpolatorBase クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CreateInstance
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDependencies
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetFinalValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetCustomInterpolator
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetInitialValueAndVelocity
dev_langs:
- C++
helpviewer_keywords:
- CInterpolatorBase class
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 44c67eef38b34a2a3cf677b42a40304c01668b42
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cinterpolatorbase-class"></a>CInterpolatorBase クラス
アニメーション変数の新しい値を計算する必要があるときに、Animation API によって呼び出されるコールバックを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CInterpolatorBase::CInterpolatorBase](#cinterpolatorbase)|構築、`CInterpolatorBase`オブジェクトです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CInterpolatorBase::CreateInstance](#createinstance)|インスタンスを作成`CInterpolatorBase`し、イベントを処理するカスタム補間へのポインターを格納します。|  
|[CInterpolatorBase::GetDependencies](#getdependencies)|補間の依存関係を取得します。 (`CUIAnimationInterpolatorBase::GetDependencies` をオーバーライドします)。|  
|[CInterpolatorBase::GetDuration](#getduration)|補間の期間を取得します。 (`CUIAnimationInterpolatorBase::GetDuration` をオーバーライドします)。|  
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|インターポレーターが潜在顧客の最終的な値を取得します。 (`CUIAnimationInterpolatorBase::GetFinalValue` をオーバーライドします)。|  
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|指定されたオフセット位置にある値を補間 (オーバーライド`CUIAnimationInterpolatorBase::InterpolateValue`)。|  
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|指定したオフセットで velocity を補間 (オーバーライド`CUIAnimationInterpolatorBase::InterpolateVelocity`)。|  
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|イベントを処理するカスタム補間へのポインターを格納します。|  
|[CInterpolatorBase::SetDuration](#setduration)|補間の期間を設定 (オーバーライド`CUIAnimationInterpolatorBase::SetDuration`)。|  
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|補間の初期値と速度を設定します。 (`CUIAnimationInterpolatorBase::SetInitialValueAndVelocity` をオーバーライドします)。|  
  
## <a name="remarks"></a>コメント  
 このハンドラーが作成されに渡される`IUIAnimationTransitionFactory::CreateTransition`ときに、`CCustomTransition`アニメーション初期化プロセスの一部としてオブジェクトが作成される (によって開始された`CAnimationController::AnimateGroup`)。 通常、このクラスを直接使用する必要はありませんにすべてのイベントを routs だけ、`CCustomInterpolator`の派生クラスを持つポインターのコンス トラクターに渡される`CCustomTransition`です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationInterpolatorBase`  
  
 `CInterpolatorBase`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="cinterpolatorbase"></a>CInterpolatorBase::CInterpolatorBase  
 CInterpolatorBase のオブジェクトを構築します。  
  
```  
CInterpolatorBase();
```  
  
##  <a name="createinstance"></a>CInterpolatorBase::CreateInstance  
 CInterpolatorBase のインスタンスを作成し、イベントを処理するカスタム補間へのポインターを格納します。  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,  
    IUIAnimationInterpolator** ppHandler);
```  
  
### <a name="parameters"></a>パラメーター  
 `pInterpolator`  
 カスタム インターポレーターへのポインター。  
  
 `ppHandler`  
 出力します。 関数が返す場合は、CInterpolatorBase のインスタンスへのポインターを格納します。  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="getdependencies"></a>CInterpolatorBase::GetDependencies  
 補間の依存関係を取得します。  
  
```  
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```  
  
### <a name="parameters"></a>パラメーター  
 `initialValueDependencies`  
 出力します。 初期値に依存する interpolator の側面は、SetInitialValueAndVelocity に渡されます。  
  
 `initialVelocityDependencies`  
 出力します。 初期速度に依存する interpolator の側面は、SetInitialValueAndVelocity に渡されます。  
  
 `durationDependencies`  
 出力します。 期間に依存する interpolator の側面は、SetDuration に渡されます。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていないか、カスタム実装は、GetDependencies メソッドから FALSE を返しますがある場合は E_FAIL を返します。  
  
##  <a name="getduration"></a>CInterpolatorBase::GetDuration  
 補間の期間を取得します。  
  
```  
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 出力します。 秒単位での遷移の期間です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていないか、カスタム実装は GetDuration メソッドから FALSE を返しますがある場合は E_FAIL を返します。  
  
##  <a name="getfinalvalue"></a>CInterpolatorBase::GetFinalValue  
 インターポレーターが潜在顧客の最終的な値を取得します。  
  
```  
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```  
  
### <a name="parameters"></a>パラメーター  
 `value`  
 出力します。 移行の最後に変数の最終的な値。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていないか、カスタム実装は GetFinalValue メソッドから FALSE を返しますがある場合は E_FAIL を返します。  
  
##  <a name="interpolatevalue"></a>CInterpolatorBase::InterpolateValue  
 指定されたオフセット位置にある値を補間します。  
  
```  
IFACEMETHOD(InterpolateValue)(
  __in UI_ANIMATION_SECONDS offset, 
  __out DOUBLE* value);
```  
  
### <a name="parameters"></a>パラメーター  
 `offset`  
 遷移の始点からのオフセット。 オフセットは、常により大きい、または&0; に等しいと遷移の期間より小さい。 遷移の期間が&0; の場合は、このメソッドは呼び出されません。  
  
 `value`  
 出力します。 補間値です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていないか、カスタム実装は InterpolateValue メソッドから FALSE を返しますがある場合は E_FAIL を返します。  
  
##  <a name="interpolatevelocity"></a>CInterpolatorBase::InterpolateVelocity  
 指定したオフセットで velocity を補間します。  
  
```  
IFACEMETHOD(InterpolateVelocity)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* velocity);
```  
  
### <a name="parameters"></a>パラメーター  
 `offset`  
 遷移の始点からのオフセット。 オフセットは&0; 以上では常に、遷移の期間以下です。 遷移の期間が&0; の場合は、このメソッドは呼び出されません。  
  
 `velocity`  
 出力します。 オフセットで変数の速度。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていないか、カスタム実装は InterpolateVelocity メソッドから FALSE を返しますがある場合は E_FAIL を返します。  
  
##  <a name="setcustominterpolator"></a>CInterpolatorBase::SetCustomInterpolator  
 イベントを処理するカスタム補間へのポインターを格納します。  
  
```  
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```  
  
### <a name="parameters"></a>パラメーター  
 `pInterpolator`  
 カスタム インターポレーターへのポインター。  
  
##  <a name="setduration"></a>CInterpolatorBase::SetDuration  
 補間の期間を設定します。  
  
```  
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 遷移の期間です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていないか、カスタム実装は、SetDuration メソッドから FALSE を返しますがある場合は E_FAIL を返します。  
  
##  <a name="setinitialvalueandvelocity"></a>CInterpolatorBase::SetInitialValueAndVelocity  
 補間の初期値と速度を設定します。  
  
```  
IFACEMETHOD(SetInitialValueAndVelocity)(
  __in DOUBLE initialValue, 
  __in DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>パラメーター  
 `initialValue`  
 移行の開始時に変数の値。  
  
 `initialVelocity`  
 移行の開始時に変数の速度。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていないか、カスタム実装は SetInitialValueAndVelocity メソッドから FALSE を返しますがある場合は E_FAIL を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

