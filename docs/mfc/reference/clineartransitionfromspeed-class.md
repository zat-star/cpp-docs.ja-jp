---
title: "CLinearTransitionFromSpeed クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::Create
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::m_dblSpeed
dev_langs:
- C++
helpviewer_keywords:
- CLinearTransitionFromSpeed class
ms.assetid: 8f159a1c-8893-4017-951e-09e5758aba7d
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
ms.openlocfilehash: b96ed05e0fbed5fdb6d384f49ca634b4bc7d9269
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="clineartransitionfromspeed-class"></a>CLinearTransitionFromSpeed クラス
直線速度遷移をカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CLinearTransitionFromSpeed : public CBaseTransition;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CLinearTransitionFromSpeed::CLinearTransitionFromSpeed](#clineartransitionfromspeed)|直線速度遷移オブジェクトを構築し、速度と最終的な値で初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CLinearTransitionFromSpeed::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CLinearTransitionFromSpeed::m_dblFinalValue](#m_dblfinalvalue)|移行の最後にアニメーション変数の値。|  
|[CLinearTransitionFromSpeed::m_dblSpeed](#m_dblspeed)|変数の速度の絶対値。|  
  
## <a name="remarks"></a>コメント  
 直線速度遷移中に指定したレートでアニメーション変数の値を変更します。 遷移の時間は初期値と指定された最終的な値の間の違いによって決まります。 すべての遷移が自動的にクリアされますが、することが推奨に割り当てられている新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、NULL がまで CAnimationController::AnimateGroup、によって作成されます。 この COM オブジェクトの作成には影響を与えません後は、メンバー変数を変更します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransitionFromSpeed](../../mfc/reference/clineartransitionfromspeed-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="clineartransitionfromspeed"></a>CLinearTransitionFromSpeed::CLinearTransitionFromSpeed  
 直線速度遷移オブジェクトを構築し、速度と最終的な値で初期化します。  
  
```  
CLinearTransitionFromSpeed(
    DOUBLE dblSpeed,  
    DOUBLE dblFinalValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `dblSpeed`  
 変数の速度の絶対値。  
  
 `dblFinalValue`  
 移行の最後にアニメーション変数の値。  
  
##  <a name="create"></a>CLinearTransitionFromSpeed::Create  
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
  
##  <a name="m_dblfinalvalue"></a>CLinearTransitionFromSpeed::m_dblFinalValue  
 移行の最後にアニメーション変数の値。  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_dblspeed"></a>CLinearTransitionFromSpeed::m_dblSpeed  
 変数の速度の絶対値。  
  
```  
DOUBLE m_dblSpeed;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

