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
- CDiscreteTransition [MFC], CDiscreteTransition
- CDiscreteTransition [MFC], Create
- CDiscreteTransition [MFC], m_dblFinalValue
- CDiscreteTransition [MFC], m_delay
- CDiscreteTransition [MFC], m_hold
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd4b1b7c868c13176d2cd99204b0bae1e2b9992d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
|[CDiscreteTransition::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移のライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDiscreteTransition::m_dblFinalValue](#m_dblfinalvalue)|遷移の終了時、アニメーション変数の値。|  
|[CDiscreteTransition::m_delay](#m_delay)|最終的な値に瞬間的なスイッチを遅延する時間数。|  
|[CDiscreteTransition::m_hold](#m_hold)|によって、最終的な値に変数を格納するための時間。|  
  
## <a name="remarks"></a>コメント  
 不連続遷移中に、アニメーション変数のまま初期値、指定された遅延時間では後で、指定した最終的な値とその値のままに瞬時に切り替えます。 保留中の指定した時間。 すべての遷移が自動的にクリアされますをお勧めして割り当てられた新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、NULL を指定してから、まで CAnimationController::AnimateGroup、によって作成されます。 この COM オブジェクトの作成も何も起こりません後は、メンバー変数を変更します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CDiscreteTransition](../../mfc/reference/cdiscretetransition-class.md)  
  
## <a name="requirements"></a>必要条件  
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
 遷移の終了時、アニメーション変数の値。  
  
 `hold`  
 によって、最終的な値に変数を格納するための時間。  
  
##  <a name="create"></a>CDiscreteTransition::Create  
 カプセル化された移行 COM オブジェクトを作成する遷移のライブラリを呼び出します。  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
`pLibrary`  
 ポインター、 [IUIAnimationTransitionLibrary インターフェイス](https://msdn.microsoft.com/library/windows/desktop/dd371897)、標準的な遷移のライブラリを定義します。  

  
### <a name="return-value"></a>戻り値  
 移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_dblfinalvalue"></a>CDiscreteTransition::m_dblFinalValue  
 遷移の終了時、アニメーション変数の値。  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_delay"></a>CDiscreteTransition::m_delay  
 最終的な値に瞬間的なスイッチを遅延する時間数。  
  
```  
UI_ANIMATION_SECONDS m_delay;  
```  
  
##  <a name="m_hold"></a>CDiscreteTransition::m_hold  
 によって、最終的な値に変数を格納するための時間。  
  
```  
UI_ANIMATION_SECONDS m_hold;  
```  
  
## <a name="see-also"></a>参照  
 [クラス](../../mfc/reference/mfc-classes.md)
