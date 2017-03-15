---
title: "CSinusoidalTransitionFromRange クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CSinusoidalTransitionFromRange
- CSinusoidalTransitionFromRange
dev_langs:
- C++
helpviewer_keywords:
- CSinusoidalTransitionFromRange class
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f9dd0e236207c0b4139de42f4c616aaad9dcad28
ms.lasthandoff: 02/24/2017

---
# <a name="csinusoidaltransitionfromrange-class"></a>CSinusoidalTransitionFromRange クラス
振幅が指定の範囲である正弦波範囲遷移をカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSinusoidalTransitionFromRange : public CBaseTransition;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange](#csinusoidaltransitionfromrange)|遷移のオブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::m_dblMaximumValue](#m_dblmaximumvalue)|正弦波のピーク時のアニメーション変数の値。|  
|[CSinusoidalTransitionFromRange::m_dblMinimumValue](#m_dblminimumvalue)|正弦波の谷のアニメーション変数の値。|  
|[CSinusoidalTransitionFromRange::m_duration](#m_duration)|遷移の期間です。|  
|[CSinusoidalTransitionFromRange::m_period](#m_period)|秒単位で正弦波形の振幅の期間。|  
|[CSinusoidalTransitionFromRange::m_slope](#m_slope)|移行の開始時に傾斜します。|  
  
## <a name="remarks"></a>コメント  
 アニメーション変数の値は、正弦波範囲遷移の期間全体にわたって指定した最小値と最大値の間で変動します。 傾斜パラメーターは、その他のパラメーターで指定された&2; つの可能な正弦波の間で区別するために使用されます。 すべての遷移が自動的にクリアされますが、することが推奨に割り当てられている新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、NULL がまで CAnimationController::AnimateGroup、によって作成されます。 この COM オブジェクトの作成には影響を与えません後は、メンバー変数を変更します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="a-namecreatea--csinusoidaltransitionfromrangecreate"></a><a name="create"></a>CSinusoidalTransitionFromRange::Create  
 カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>パラメーター  
 `pLibrary`  
 これは標準的な遷移の作成を担当する遷移ライブラリへのポインター。  
  
### <a name="return-value"></a>戻り値  
 移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="a-namecsinusoidaltransitionfromrangea--csinusoidaltransitionfromrangecsinusoidaltransitionfromrange"></a><a name="csinusoidaltransitionfromrange"></a>CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange  
 遷移のオブジェクトを構築します。  
  
```  
CSinusoidalTransitionFromRange(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE dblMinimumValue,  
    DOUBLE dblMaximumValue,  
    UI_ANIMATION_SECONDS period,  
    UI_ANIMATION_SLOPE slope);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 遷移の期間です。  
  
 `dblMinimumValue`  
 正弦波の谷のアニメーション変数の値。  
  
 `dblMaximumValue`  
 正弦波のピーク時のアニメーション変数の値。  
  
 `period`  
 秒単位で正弦波形の振幅の期間。  
  
 `slope`  
 移行の開始時に傾斜します。  
  
##  <a name="a-namemdblmaximumvaluea--csinusoidaltransitionfromrangemdblmaximumvalue"></a><a name="m_dblmaximumvalue"></a>CSinusoidalTransitionFromRange::m_dblMaximumValue  
 正弦波のピーク時のアニメーション変数の値。  
  
```  
DOUBLE m_dblMaximumValue;  
```  
  
##  <a name="a-namemdblminimumvaluea--csinusoidaltransitionfromrangemdblminimumvalue"></a><a name="m_dblminimumvalue"></a>CSinusoidalTransitionFromRange::m_dblMinimumValue  
 正弦波の谷のアニメーション変数の値。  
  
```  
DOUBLE m_dblMinimumValue;  
```  
  
##  <a name="a-namemdurationa--csinusoidaltransitionfromrangemduration"></a><a name="m_duration"></a>CSinusoidalTransitionFromRange::m_duration  
 遷移の期間です。  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="a-namemperioda--csinusoidaltransitionfromrangemperiod"></a><a name="m_period"></a>CSinusoidalTransitionFromRange::m_period  
 秒単位で正弦波形の振幅の期間。  
  
```  
UI_ANIMATION_SECONDS m_period;  
```  
  
##  <a name="a-namemslopea--csinusoidaltransitionfromrangemslope"></a><a name="m_slope"></a>CSinusoidalTransitionFromRange::m_slope  
 移行の開始時に傾斜します。  
  
```  
UI_ANIMATION_SLOPE m_slope;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

