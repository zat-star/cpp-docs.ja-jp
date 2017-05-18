---
title: "CCustomInterpolator クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDependencies
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetFinalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::Init
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetInitialValueAndVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_duration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_finalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialVelocity
dev_langs:
- C++
helpviewer_keywords:
- CCustomInterpolator class
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
caps.latest.revision: 17
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: 4d0b38543092dc68c2527f7e1385712164faf996
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccustominterpolator-class"></a>CCustomInterpolator クラス
基本のインターポレータを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CCustomInterpolator;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCustomInterpolator::CCustomInterpolator](#ccustominterpolator)|オーバーロードされます。 カスタム インターポレーター オブジェクトを構築し、期間と指定した値に velocity を初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCustomInterpolator::GetDependencies](#getdependencies)|補間の依存関係を取得します。|  
|[CCustomInterpolator::GetDuration](#getduration)|補間の期間を取得します。|  
|[CCustomInterpolator::GetFinalValue](#getfinalvalue)|インターポレーターが潜在顧客の最終的な値を取得します。|  
|[CCustomInterpolator::Init](#init)|期間と最終的な値を初期化します。|  
|[CCustomInterpolator::InterpolateValue](#interpolatevalue)|指定されたオフセット位置にある値を補間します。|  
|[CCustomInterpolator::InterpolateVelocity](#interpolatevelocity)|指定したオフセットで velocity を補間します。|  
|[CCustomInterpolator::SetDuration](#setduration)|補間の期間を設定します。|  
|[CCustomInterpolator::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|補間の初期値と速度を設定します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CCustomInterpolator::m_currentValue](#m_currentvalue)|補間値です。|  
|[CCustomInterpolator::m_currentVelocity](#m_currentvelocity)|補間速度。|  
|[CCustomInterpolator::m_duration](#m_duration)|遷移の期間です。|  
|[CCustomInterpolator::m_finalValue](#m_finalvalue)|移行の最後に変数の最終的な値。|  
|[CCustomInterpolator::m_initialValue](#m_initialvalue)|移行の開始時に変数の値。|  
|[CCustomInterpolator::m_initialVelocity](#m_initialvelocity)|移行の開始時に変数の速度。|  
  
## <a name="remarks"></a>コメント  
 CCustomInterpolator からクラスを派生し、補間のカスタム アルゴリズムを実装するために必要なすべてのメソッドをオーバーライドします。 このクラスへのポインターは、CCustomTransition にパラメーターとして渡す必要があります。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CCustomInterpolator`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="ccustominterpolator"></a>CCustomInterpolator::CCustomInterpolator  
 カスタム インターポレーター オブジェクトを構築し、0 を既定値にすべての値を設定します。  
  
```  
CCustomInterpolator();

 
CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 遷移の期間です。  
  
 `finalValue`  
  
### <a name="remarks"></a>コメント  
 CCustomInterpolator::Init を使用して、期間と、コードの後で最終的な値を初期化します。  
  
##  <a name="getdependencies"></a>CCustomInterpolator::GetDependencies  
 補間の依存関係を取得します。  
  
```  
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,  
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,  
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```  
  
### <a name="parameters"></a>パラメーター  
 `initialValueDependencies`  
 出力します。 初期値に依存する interpolator の側面は、SetInitialValueAndVelocity に渡されます。  
  
 `initialVelocityDependencies`  
 出力します。 初期速度に依存する interpolator の側面は、SetInitialValueAndVelocity に渡されます。  
  
 `durationDependencies`  
 出力します。 期間に依存する interpolator の側面は、SetDuration に渡されます。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装は常に TRUE を返します。 FALSE を返すオーバーライドして実装したイベントが失敗する場合。  
  
##  <a name="getduration"></a>CCustomInterpolator::GetDuration  
 補間の期間を取得します。  
  
```  
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 出力します。 秒単位での遷移の期間です。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装は常に TRUE を返します。 FALSE を返すオーバーライドして実装したイベントが失敗する場合。  
  
##  <a name="getfinalvalue"></a>CCustomInterpolator::GetFinalValue  
 インターポレーターが潜在顧客の最終的な値を取得します。  
  
```  
virtual BOOL GetFinalValue(DOUBLE* value);
```  
  
### <a name="parameters"></a>パラメーター  
 `value`  
 出力します。 移行の最後に変数の最終的な値。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装は常に TRUE を返します。 FALSE を返すオーバーライドして実装したイベントが失敗する場合。  
  
##  <a name="init"></a>CCustomInterpolator::Init  
 期間と最終的な値を初期化します。  
  
```  
void Init(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 遷移の期間です。  
  
 `finalValue`  
 移行の最後に変数の最終的な値。  
  
##  <a name="interpolatevalue"></a>CCustomInterpolator::InterpolateValue  
 指定されたオフセット位置にある値を補間します。  
  
```  
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,  
    DOUBLE* value);
```  
  
### <a name="parameters"></a>パラメーター  
 `value`  
 出力します。 補間値です。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装は常に TRUE を返します。 FALSE を返すオーバーライドして実装したイベントが失敗する場合。  
  
##  <a name="interpolatevelocity"></a>CCustomInterpolator::InterpolateVelocity  
 指定したオフセットで velocity を補間します。  
  
```  
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,  
    DOUBLE* velocity);
```  
  
### <a name="parameters"></a>パラメーター  
 `velocity`  
 出力します。 オフセットで変数の速度。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装は常に TRUE を返します。 FALSE を返すオーバーライドして実装したイベントが失敗する場合。  
  
##  <a name="m_currentvalue"></a>CCustomInterpolator::m_currentValue  
 補間値です。  
  
```  
DOUBLE m_currentValue;  
```  
  
##  <a name="m_currentvelocity"></a>CCustomInterpolator::m_currentVelocity  
 補間速度。  
  
```  
DOUBLE m_currentVelocity;  
```  
  
##  <a name="m_duration"></a>CCustomInterpolator::m_duration  
 遷移の期間です。  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_finalvalue"></a>CCustomInterpolator::m_finalValue  
 移行の最後に変数の最終的な値。  
  
```  
DOUBLE m_finalValue;  
```  
  
##  <a name="m_initialvalue"></a>CCustomInterpolator::m_initialValue  
 移行の開始時に変数の値。  
  
```  
DOUBLE m_initialValue;  
```  
  
##  <a name="m_initialvelocity"></a>CCustomInterpolator::m_initialVelocity  
 移行の開始時に変数の速度。  
  
```  
DOUBLE m_initialVelocity;  
```  
  
##  <a name="setduration"></a>CCustomInterpolator::SetDuration  
 補間の期間を設定します。  
  
```  
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 遷移の期間です。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装は常に TRUE を返します。 FALSE を返すオーバーライドして実装したイベントが失敗する場合。  
  
##  <a name="setinitialvalueandvelocity"></a>CCustomInterpolator::SetInitialValueAndVelocity  
 補間の初期値と速度を設定します。  
  
```  
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,  
    DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>パラメーター  
 `initialValue`  
 移行の開始時に変数の値。  
  
 `initialVelocity`  
 移行の開始時に変数の速度。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装を常に TRUE を返します。 FALSE を返すオーバーライドして実装したイベントが失敗する場合。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

