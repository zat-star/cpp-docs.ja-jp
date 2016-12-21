---
title: "CSinusoidalTransitionFromRange クラス | Microsoft Docs"
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
  - "afxanimationcontroller/CSinusoidalTransitionFromRange"
  - "CSinusoidalTransitionFromRange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSinusoidalTransitionFromRange クラス"
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSinusoidalTransitionFromRange クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

振幅が指定の範囲である正弦波範囲遷移をカプセル化します。  
  
## 構文  
  
```  
class CSinusoidalTransitionFromRange : public CBaseTransition;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange](../Topic/CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange.md)|遷移オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSinusoidalTransitionFromRange::Create](../Topic/CSinusoidalTransitionFromRange::Create.md)|遷移ライブラリを呼び出して、カプセル化された遷移 COM オブジェクトを作成します   \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) をオーバーライドします\)。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CSinusoidalTransitionFromRange::m\_dblMaximumValue](../Topic/CSinusoidalTransitionFromRange::m_dblMaximumValue.md)|正弦波のピーク時のアニメーション変数の値。|  
|[CSinusoidalTransitionFromRange::m\_dblMinimumValue](../Topic/CSinusoidalTransitionFromRange::m_dblMinimumValue.md)|正弦波のトラフ時のアニメーション変数の値。|  
|[CSinusoidalTransitionFromRange::m\_duration](../Topic/CSinusoidalTransitionFromRange::m_duration.md)|遷移の継続時間。|  
|[CSinusoidalTransitionFromRange::m\_period](../Topic/CSinusoidalTransitionFromRange::m_period.md)|正弦波の振動の周期 \(秒\)。|  
|[CSinusoidalTransitionFromRange::m\_slope](../Topic/CSinusoidalTransitionFromRange::m_slope.md)|遷移の開始時の傾き。|  
  
## 解説  
 正弦波範囲遷移では、遷移の継続時間全体にわたって、アニメーション変数の値が指定した最小値と最大値の間で変動します。  slope パラメーターは、他のパラメーターで指定される 2 つの正弦波の間のあいまいさを解消するために使用されます。  遷移はすべて自動的にクリアされるため、遷移の割り当てには new 演算子を使用することをお勧めします。  カプセル化された IUIAnimationTransition COM オブジェクトは CAnimationController::AnimateGroup によって作成され、作成されるまでは NULL になります。  この COM オブジェクトの作成後にメンバー変数を変更しても効力はありません。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)