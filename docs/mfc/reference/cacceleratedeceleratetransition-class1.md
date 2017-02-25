---
title: "CAccelerateDecelerateTransition Class1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAccelerateDecelerateTransition"
  - "afxanimationcontroller/CAccelerateDecelerateTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccelerateDecelerateTransition クラス"
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# CAccelerateDecelerateTransition クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

加速減速遷移を実装します。  
  
## 構文  
  
```  
class CAccelerateDecelerateTransition : public CBaseTransition;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](../Topic/CAccelerateDecelerateTransition::CAccelerateDecelerateTransition.md)|遷移オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAccelerateDecelerateTransition::Create](../Topic/CAccelerateDecelerateTransition::Create.md)|遷移ライブラリを呼び出して、カプセル化された遷移 COM オブジェクトを作成します   \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) をオーバーライドします\)。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAccelerateDecelerateTransition::m\_accelerationRatio](../Topic/CAccelerateDecelerateTransition::m_accelerationRatio.md)|加速に費やされる時間の継続時間に対する比率。|  
|[CAccelerateDecelerateTransition::m\_decelerationRatio](../Topic/CAccelerateDecelerateTransition::m_decelerationRatio.md)|減速に費やされる時間の継続時間に対する比率。|  
|[CAccelerateDecelerateTransition::m\_duration](../Topic/CAccelerateDecelerateTransition::m_duration.md)|遷移の継続時間。|  
|[CAccelerateDecelerateTransition::m\_finalValue](../Topic/CAccelerateDecelerateTransition::m_finalValue.md)|遷移の終了時のアニメーション変数の値。|  
  
## 解説  
 加速減速遷移では、アニメーション変数が遷移の継続時間にわたって加速した後に減速し、指定した値で終了します。  変数の加速度と減速度は、それぞれ加速率と減速率を指定して個別に制御できます。  初期速度がゼロの場合、加速率は、変数の加速に費やされる時間の割合です \(減速率についても同様\)。  初期速度がゼロ以外の場合は、速度がゼロに達してから遷移が終了するまでの時間の割合です。  加速率と減速率の合計は最大で 1.0 になります。  遷移はすべて自動的にクリアされるため、遷移の割り当てには new 演算子を使用することをお勧めします。  カプセル化された IUIAnimationTransition COM オブジェクトは CAnimationController::AnimateGroup によって作成され、作成されるまでは NULL になります。  この COM オブジェクトの作成後にメンバー変数を変更しても効力はありません。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CAccelerateDecelerateTransition](../../mfc/reference/cacceleratedeceleratetransition-class1.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)