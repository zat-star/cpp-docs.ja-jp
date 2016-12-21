---
title: "CSinusoidalTransitionFromVelocity クラス | Microsoft Docs"
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
  - "CSinusoidalTransitionFromVelocity"
  - "afxanimationcontroller/CSinusoidalTransitionFromVelocity"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSinusoidalTransitionFromVelocity クラス"
ms.assetid: cc885f17-b84b-45ee-8f1f-36a8bbb7adad
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSinusoidalTransitionFromVelocity クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アニメーション変数の初期速度によって振幅が決まる正弦波速度遷移をカプセル化します。  
  
## 構文  
  
```  
class CSinusoidalTransitionFromVelocity : public CBaseTransition;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity](../Topic/CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity.md)|遷移オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSinusoidalTransitionFromVelocity::Create](../Topic/CSinusoidalTransitionFromVelocity::Create.md)|遷移ライブラリを呼び出して、カプセル化された遷移 COM オブジェクトを作成します   \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) をオーバーライドします\)。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CSinusoidalTransitionFromVelocity::m\_duration](../Topic/CSinusoidalTransitionFromVelocity::m_duration.md)|遷移の継続時間。|  
|[CSinusoidalTransitionFromVelocity::m\_period](../Topic/CSinusoidalTransitionFromVelocity::m_period.md)|正弦波の振動の周期 \(秒\)。|  
  
## 解説  
 正弦波範囲遷移では、遷移の継続時間全体にわたって、アニメーション変数の値が初期値を挟んで振幅します。  振幅は、遷移の開始時のアニメーション変数の速度によって決まります。  遷移はすべて自動的にクリアされるため、遷移の割り当てには new 演算子を使用することをお勧めします。  カプセル化された IUIAnimationTransition COM オブジェクトは CAnimationController::AnimateGroup によって作成され、作成されるまでは NULL になります。  この COM オブジェクトの作成後にメンバー変数を変更しても効力はありません。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromVelocity](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)