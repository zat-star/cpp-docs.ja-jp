---
title: "CDiscreteTransition クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::Create
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_delay
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_hold
dev_langs:
- C++
helpviewer_keywords:
- CDiscreteTransition class
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: dcec642fede0ec6895c928925676232319099be7
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdiscretetransition-class"></a>CDiscreteTransition クラス
不連続遷移をカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDiscreteTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDiscreteTransition::CDiscreteTransition](#cdiscretetransition)|不連続遷移オブジェクトを構築し、そのパラメーターを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDiscreteTransition::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDiscreteTransition::m_dblFinalValue](#m_dblfinalvalue)|移行の最後にアニメーション変数の値。|  
|[CDiscreteTransition::m_delay](#m_delay)|最終的な値に瞬間的なスイッチを遅延する時間数。|  
|[CDiscreteTransition::m_hold](#m_hold)|最終値に変数を格納するための時間。|  
  
## <a name="remarks"></a>コメント  
 不連続遷移中にアニメーション変数のまま初期値、指定された遅延時間では後でスイッチとその値で指定された最終的な値を即座に保留中の指定した時間です。 すべての遷移が自動的にクリアされますが、することが推奨に割り当てられている新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、NULL がまで CAnimationController::AnimateGroup、によって作成されます。 この COM オブジェクトの作成には影響を与えません後は、メンバー変数を変更します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CDiscreteTransition](../../mfc/reference/cdiscretetransition-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="cdiscretetransition"></a>CDiscreteTransition::CDiscreteTransition  
 不連続遷移オブジェクトを構築し、そのパラメーターを初期化します。  
  
```  
CDiscreteTransition(
    UI_ANIMATION_SECONDS delay,  
    DOUBLE dblFinalValue,  
    UI_ANIMATION_SECONDS hold);
```  
  
### <a name="parameters"></a>パラメーター  
 `delay`  
 最終的な値に瞬間的なスイッチを遅延する時間数。  
  
 `dblFinalValue`  
 移行の最後にアニメーション変数の値。  
  
 `hold`  
 最終値に変数を格納するための時間。  
  
##  <a name="create"></a>CDiscreteTransition::Create  
 カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
`pLibrary`  
 ポインター、 [IUIAnimationTransitionLibrary インターフェイス](https://msdn.microsoft.com/library/windows/desktop/dd371897)、標準の遷移のライブラリを定義します。  

  
### <a name="return-value"></a>戻り値  
 移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_dblfinalvalue"></a>CDiscreteTransition::m_dblFinalValue  
 移行の最後にアニメーション変数の値。  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_delay"></a>CDiscreteTransition::m_delay  
 最終的な値に瞬間的なスイッチを遅延する時間数。  
  
```  
UI_ANIMATION_SECONDS m_delay;  
```  
  
##  <a name="m_hold"></a>CDiscreteTransition::m_hold  
 最終値に変数を格納するための時間。  
  
```  
UI_ANIMATION_SECONDS m_hold;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

