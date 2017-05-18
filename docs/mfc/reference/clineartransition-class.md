---
title: "CLinearTransition クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::Create
- AFXANIMATIONCONTROLLER/CLinearTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CLinearTransition::m_duration
dev_langs:
- C++
helpviewer_keywords:
- CLinearTransition class
ms.assetid: 7fcb2dba-beb8-4933-9f5d-3b7fb1585ef0
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: c39a3961600401f47f2f38d1a0cd735b1237813f
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="clineartransition-class"></a>CLinearTransition クラス
線形遷移をカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CLinearTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CLinearTransition::CLinearTransition](#clineartransition)|線形遷移オブジェクトを構築し、期間と最終的な値で初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CLinearTransition::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CLinearTransition::m_dblFinalValue](#m_dblfinalvalue)|移行の最後にアニメーション変数の値。|  
|[CLinearTransition::m_duration](#m_duration)|遷移の期間です。|  
  
## <a name="remarks"></a>コメント  
 線形遷移中には、アニメーション変数の値は、初期値から指定された最終的な値に直線的に移行します。 すべての遷移が自動的にクリアされますが、することが推奨に割り当てられている新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、NULL がまで CAnimationController::AnimateGroup、によって作成されます。 この COM オブジェクトの作成には影響を与えません後は、メンバー変数を変更します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransition](../../mfc/reference/clineartransition-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="clineartransition"></a>CLinearTransition::CLinearTransition  
 線形遷移オブジェクトを構築し、期間と最終的な値で初期化します。  
  
```  
CLinearTransition(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE dblFinalValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 遷移の期間です。  
  
 `dblFinalValue`  
 移行の最後にアニメーション変数の値。  
  
##  <a name="create"></a>CLinearTransition::Create  
 カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>パラメーター  
`pLibrary`  
 ポインター、 [IUIAnimationTransitionLibrary インターフェイス](https://msdn.microsoft.com/library/windows/desktop/dd371897)、標準の遷移のライブラリを定義します。  
  
### <a name="return-value"></a>戻り値  
 移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_dblfinalvalue"></a>CLinearTransition::m_dblFinalValue  
 移行の最後にアニメーション変数の値。  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_duration"></a>CLinearTransition::m_duration  
 遷移の期間です。  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

