---
title: "CReversalTransition クラス | Microsoft Docs"
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
  - "afxanimationcontroller/CReversalTransition"
  - "CReversalTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReversalTransition クラス"
ms.assetid: e89516be-2d07-4885-95a8-fc278f46e3ad
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CReversalTransition クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

逆遷移をカプセル化します。  
  
## 構文  
  
```  
class CReversalTransition : public CBaseTransition;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CReversalTransition::CReversalTransition](../Topic/CReversalTransition::CReversalTransition.md)|逆遷移オブジェクトを構築し、その継続時間を初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CReversalTransition::Create](../Topic/CReversalTransition::Create.md)|遷移ライブラリを呼び出して、カプセル化された遷移 COM オブジェクトを作成します   \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) をオーバーライドします\)。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CReversalTransition::m\_duration](../Topic/CReversalTransition::m_duration.md)|遷移の継続時間。|  
  
## 解説  
 逆遷移では、指定した継続時間にわたって方向が滑らかに変化します。  最終値は初期値と同じになり、最終速度は初期速度の負数になります。  遷移はすべて自動的にクリアされるため、遷移の割り当てには new 演算子を使用することをお勧めします。  カプセル化された IUIAnimationTransition COM オブジェクトは CAnimationController::AnimateGroup によって作成され、作成されるまでは NULL になります。  この COM オブジェクトの作成後にメンバー変数を変更しても効力はありません。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CReversalTransition](../../mfc/reference/creversaltransition-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)