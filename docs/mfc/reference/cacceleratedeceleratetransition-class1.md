---
title: "CAccelerateDecelerateTransition Class1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
dev_langs:
- C++
helpviewer_keywords:
- CAccelerateDecelerateTransition class
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
caps.latest.revision: 16
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f11dc96b48695b998fb17c33735e8f56bce517b7
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cacceleratedeceleratetransition-class"></a>CAccelerateDecelerateTransition クラス
加速減速遷移を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAccelerateDecelerateTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|遷移のオブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|期間の短縮に費やした時間の比率です。|  
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|存続時間に減速に費やした時間の比率です。|  
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|遷移の期間です。|  
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|移行の最後にアニメーション変数の値。|  
  
## <a name="remarks"></a>コメント  
 加速中-/減速の遷移は、アニメーション変数を高速化し、速度が低下し、指定した値で終わる、切り替え効果の再生時間にわたるします。 変数がどの程度の速度を短縮し、さまざまな加速と減速の比率を指定することによって、独立してに減速を制御できます。 アクセラレータの比率が加速; 変数に要する時間の割合が初期速度が&0; の場合同様に、減速比のです。 初期速度が&0; 以外の場合は、velocity を&0; と遷移の末尾に到達するまでの時間の割合を勧めします。 アクセラレータ比と減速率を合計すると 1.0 の最大数。 すべての遷移が自動的にクリアされますが、することが推奨に割り当てられている新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、NULL がまで CAnimationController::AnimateGroup、によって作成されます。 この COM オブジェクトの作成には影響を与えません後は、メンバー変数を変更します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CAccelerateDecelerateTransition`   
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="cacceleratedeceleratetransition"></a>CAccelerateDecelerateTransition::CAccelerateDecelerateTransition  
 遷移のオブジェクトを構築します。  
  
```  
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue,  
    DOUBLE accelerationRatio = 0.3,  
    DOUBLE decelerationRatio = 0.3);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 遷移の期間です。  
  
 `finalValue`  
 移行の最後にアニメーション変数の値。  
  
 `accelerationRatio`  
 期間の短縮に費やした時間の比率です。  
  
 `decelerationRatio`  
 存続時間に減速に費やした時間の比率です。  
  
##  <a name="create"></a>CAccelerateDecelerateTransition::Create  
 カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* *\not used*\);
```  
  
### <a name="parameters"></a>パラメーター  
`pLibrary`  
 ポインター、 [IUIAnimationTransitionLibrary インターフェイス](https://msdn.microsoft.com/library/windows/desktop/dd371897)、標準の遷移のライブラリを定義します。  
  
### <a name="return-value"></a>戻り値  
 移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_accelerationratio"></a>CAccelerateDecelerateTransition::m_accelerationRatio  
 期間の短縮に費やした時間の比率です。  
  
```  
DOUBLE m_accelerationRatio;  
```  
  
##  <a name="m_decelerationratio"></a>CAccelerateDecelerateTransition::m_decelerationRatio  
 存続時間に減速に費やした時間の比率です。  
  
```  
DOUBLE m_decelerationRatio;  
```  
  
##  <a name="m_duration"></a>CAccelerateDecelerateTransition::m_duration  
 遷移の期間です。  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_finalvalue"></a>CAccelerateDecelerateTransition::m_finalValue  
 移行の最後にアニメーション変数の値。  
  
```  
DOUBLE m_finalValue;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

