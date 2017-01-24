---
title: "CCustomTransition クラス | Microsoft Docs"
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
  - "afxanimationcontroller/CCustomTransition"
  - "CCustomTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCustomTransition クラス"
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCustomTransition クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

カスタム遷移を実装します。  
  
## 構文  
  
```  
class CCustomTransition : public CBaseTransition;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CCustomTransition::CCustomTransition](../Topic/CCustomTransition::CCustomTransition.md)|カスタムの遷移オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CCustomTransition::Create](../Topic/CCustomTransition::Create.md)|遷移ライブラリを呼び出して、カプセル化された遷移 COM オブジェクトを作成します   \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) をオーバーライドします\)。|  
|[CCustomTransition::SetInitialValue](../Topic/CCustomTransition::SetInitialValue.md)|この遷移に関連付けられたアニメーション変数に適用する初期値を設定します。|  
|[CCustomTransition::SetInitialVelocity](../Topic/CCustomTransition::SetInitialVelocity.md)|この遷移に関連付けられたアニメーション変数に適用する初期速度を設定します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CCustomTransition::m\_bInitialValueSpecified](../Topic/CCustomTransition::m_bInitialValueSpecified.md)|SetInitialValue で初期値が指定されているかどうかを示します。|  
|[CCustomTransition::m\_bInitialVelocitySpecified](../Topic/CCustomTransition::m_bInitialVelocitySpecified.md)|SetInitialVelocity で初期速度が指定されているかどうかを示します。|  
|[CCustomTransition::m\_initialValue](../Topic/CCustomTransition::m_initialValue.md)|初期値を格納します。|  
|[CCustomTransition::m\_initialVelocity](../Topic/CCustomTransition::m_initialVelocity.md)|初期速度を格納します。|  
|[CCustomTransition::m\_pInterpolator](../Topic/CCustomTransition::m_pInterpolator.md)|カスタムのインターポレータへのポインターを格納します。|  
  
## 解説  
 CCustomTransitions クラスを使用すると、カスタムの遷移を実装できます。  このクラスは、標準の遷移として作成および使用されますが、コンストラクターはカスタムのインターポレータへのポインターをパラメーターとして受け取ります。  カスタムの遷移を使用するには、次の手順を実行します。1.   CCustomInterpolator の派生クラスを作成し、少なくとも InterpolateValue メソッドは実装します。  2.  カスタムのインターポレータ オブジェクトの有効期間が、これを使用するアニメーションの継続時間より長くなるようにします。  3.  CCustomTransition オブジェクトをインスタンス化し \(new 演算子を使用します\)、コンストラクターでカスタムのインターポレータへのポインターを渡します。  4.  CCustomTransition::SetInitialValue と CCustomTransition::SetInitialVelocity を呼び出します \(カスタムの補間でこれらのパラメーターが必要な場合\)。  5.  カスタムの遷移へのポインターを、カスタム アルゴリズムを使用して値をアニメーション化するアニメーション オブジェクトの AddTransition メソッドに渡します。  6.  アニメーション オブジェクトの値を変更する必要が生じると、Windows Animation API によって CCustomInterpolator の InterpolateValue \(およびその他の関連メソッド\) が呼び出されます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CCustomTransition](../../mfc/reference/ccustomtransition-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)