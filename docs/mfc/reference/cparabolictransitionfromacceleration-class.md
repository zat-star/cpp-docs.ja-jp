---
title: "CParabolicTransitionFromAcceleration クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CParabolicTransitionFromAcceleration"
  - "CParabolicTransitionFromAcceleration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CParabolicTransitionFromAcceleration クラス"
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CParabolicTransitionFromAcceleration クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

放物線加速遷移をカプセル化します。  
  
## 構文  
  
```  
class CParabolicTransitionFromAcceleration : public CBaseTransition;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration](../Topic/CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration.md)|放物線加速遷移を構築し、指定したパラメーターで初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CParabolicTransitionFromAcceleration::Create](../Topic/CParabolicTransitionFromAcceleration::Create.md)|遷移ライブラリを呼び出して、カプセル化された遷移 COM オブジェクトを作成します   \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) をオーバーライドします\)。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CParabolicTransitionFromAcceleration::m\_dblAcceleration](../Topic/CParabolicTransitionFromAcceleration::m_dblAcceleration.md)|遷移中のアニメーション変数の加速度。|  
|[CParabolicTransitionFromAcceleration::m\_dblFinalValue](../Topic/CParabolicTransitionFromAcceleration::m_dblFinalValue.md)|遷移の終了時のアニメーション変数の値。|  
|[CParabolicTransitionFromAcceleration::m\_dblFinalVelocity](../Topic/CParabolicTransitionFromAcceleration::m_dblFinalVelocity.md)|遷移の終了時のアニメーション変数の速度。|  
  
## 解説  
 放物線加速遷移では、アニメーション変数の値が初期値から最終値まで遷移し、指定した速度で終了します。  加速度を指定することにより、変数が最終値に到達するまでの時間を制御できます。  遷移はすべて自動的にクリアされるため、遷移の割り当てには new 演算子を使用することをお勧めします。  カプセル化された IUIAnimationTransition COM オブジェクトは CAnimationController::AnimateGroup によって作成され、作成されるまでは NULL になります。  この COM オブジェクトの作成後にメンバー変数を変更しても効力はありません。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CParabolicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)