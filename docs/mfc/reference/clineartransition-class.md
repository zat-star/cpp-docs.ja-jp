---
title: "CLinearTransition クラス | Microsoft Docs"
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
  - "CLinearTransition"
  - "afxanimationcontroller/CLinearTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLinearTransition クラス"
ms.assetid: 7fcb2dba-beb8-4933-9f5d-3b7fb1585ef0
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CLinearTransition クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

線形遷移をカプセル化します。  
  
## 構文  
  
```  
class CLinearTransition : public CBaseTransition;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CLinearTransition::CLinearTransition](../Topic/CLinearTransition::CLinearTransition.md)|線形遷移オブジェクトを構築し、継続期間と最終値で初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CLinearTransition::Create](../Topic/CLinearTransition::Create.md)|遷移ライブラリを呼び出して、カプセル化された遷移 COM オブジェクトを作成します   \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) をオーバーライドします\)。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CLinearTransition::m\_dblFinalValue](../Topic/CLinearTransition::m_dblFinalValue.md)|遷移の終了時のアニメーション変数の値。|  
|[CLinearTransition::m\_duration](../Topic/CLinearTransition::m_duration.md)|遷移の継続時間。|  
  
## 解説  
 線形遷移では、アニメーション変数の値が初期値から指定した最終値まで直線的に遷移します。  遷移はすべて自動的にクリアされるため、遷移の割り当てには new 演算子を使用することをお勧めします。  カプセル化された IUIAnimationTransition COM オブジェクトは CAnimationController::AnimateGroup によって作成され、作成されるまでは NULL になります。  この COM オブジェクトの作成後にメンバー変数を変更しても効力はありません。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransition](../../mfc/reference/clineartransition-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)