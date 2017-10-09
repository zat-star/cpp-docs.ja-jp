---
title: "CConstantTransition クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::Create
- AFXANIMATIONCONTROLLER/CConstantTransition::m_duration
dev_langs:
- C++
helpviewer_keywords:
- CConstantTransition [MFC], CConstantTransition
- CConstantTransition [MFC], Create
- CConstantTransition [MFC], m_duration
ms.assetid: f6fa4780-a71b-4cd6-80aa-d4792ace36c2
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: ebf6536421814ba9e08e497b1c29eed7e17ede06
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="cconstanttransition-class"></a>CConstantTransition クラス
連続的遷移をカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CConstantTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CConstantTransition::CConstantTransition](#cconstanttransition)|移行のオブジェクトを構築し、その継続時間を初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CConstantTransition::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移のライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CConstantTransition::m_duration](#m_duration)|移行の期間です。|  
  
## <a name="remarks"></a>コメント  
 アニメーション変数の値は、連続的遷移中に、遷移の期間にわたって初期値でままです。 すべての遷移が自動的にクリアされますをお勧めして割り当てられた新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、NULL を指定してから、まで CAnimationController::AnimateGroup、によって作成されます。 この COM オブジェクトの作成も何も起こりません後は、メンバー変数を変更します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CConstantTransition`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="cconstanttransition"></a>CConstantTransition::CConstantTransition  
 移行のオブジェクトを構築し、その継続時間を初期化します。  
  
```  
CConstantTransition (UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 移行の期間です。  
  
##  <a name="create"></a>CConstantTransition::Create  
 カプセル化された移行 COM オブジェクトを作成する遷移のライブラリを呼び出します。  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>パラメーター  
 `pLibrary`  
 ポインター、 [IUIAnimationTransitionLibrary インターフェイス](https://msdn.microsoft.com/library/windows/desktop/dd371897)、標準的な遷移のライブラリを定義します。  

### <a name="return-value"></a>戻り値  
 移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_duration"></a>CConstantTransition::m_duration  
 移行の期間です。  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

