---
title: "CSmoothStopTransition クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::Create
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_maximumDuration
dev_langs:
- C++
helpviewer_keywords:
- CSmoothStopTransition class
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
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
ms.openlocfilehash: 60cdc3528d10270187dccd42a634f7483c58821f
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="csmoothstoptransition-class"></a>CSmoothStopTransition クラス
スムーズ停止遷移をカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSmoothStopTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSmoothStopTransition::CSmoothStopTransition](#csmoothstoptransition)|スムーズ停止遷移を構築して、その時間の上限と最終的な値を初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSmoothStopTransition::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CSmoothStopTransition::m_dblFinalValue](#m_dblfinalvalue)|移行の最後にアニメーション変数の値。|  
|[CSmoothStopTransition::m_maximumDuration](#m_maximumduration)|遷移の最大期間。|  
  
## <a name="remarks"></a>コメント  
 特定の最終的な値に近づくし、0 の velocity の使用に達すると、スムーズ停止遷移が低下します。 遷移の期間は、最初と最後の値と指定した最大期間の違い、初期速度によって決まります。 1 つの放物線を描く円弧から成るソリューションがない場合、このメソッドは、3 次遷移を作成します。 すべての遷移が自動的にクリアされますが、することが推奨に割り当てられている新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、NULL がまで CAnimationController::AnimateGroup、によって作成されます。 この COM オブジェクトの作成には影響を与えません後は、メンバー変数を変更します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSmoothStopTransition](../../mfc/reference/csmoothstoptransition-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="create"></a>CSmoothStopTransition::Create  
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
  
##  <a name="csmoothstoptransition"></a>CSmoothStopTransition::CSmoothStopTransition  
 スムーズ停止遷移を構築して、その時間の上限と最終的な値を初期化します。  
  
```  
CSmoothStopTransition(
    UI_ANIMATION_SECONDS maximumDuration,  
    DOUBLE dblFinalValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `maximumDuration`  
 遷移の最大期間。  
  
 `dblFinalValue`  
 移行の最後にアニメーション変数の値。  
  
##  <a name="m_dblfinalvalue"></a>CSmoothStopTransition::m_dblFinalValue  
 移行の最後にアニメーション変数の値。  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_maximumduration"></a>CSmoothStopTransition::m_maximumDuration  
 遷移の最大期間。  
  
```  
UI_ANIMATION_SECONDS m_maximumDuration;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

