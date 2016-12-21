---
title: "CAnimationValue クラス | Microsoft Docs"
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
  - "afxanimationcontroller/CAnimationValue"
  - "CAnimationValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationValue クラス"
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationValue クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

1 つの値を持つアニメーション オブジェクトの機能を実装します。  
  
## 構文  
  
```  
class CAnimationValue : public CAnimationBaseObject;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAnimationValue::CAnimationValue](../Topic/CAnimationValue::CAnimationValue.md)|オーバーロードされます。  CAnimationValue オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationValue::AddTransition](../Topic/CAnimationValue::AddTransition.md)|値に適用する遷移を追加します。|  
|[CAnimationValue::GetValue](../Topic/CAnimationValue::GetValue.md)|オーバーロードされます。  現在の値を取得します。|  
|[CAnimationValue::GetVariable](../Topic/CAnimationValue::GetVariable.md)|カプセル化されたアニメーション変数にアクセスできるようにします。|  
|[CAnimationValue::SetDefaultValue](../Topic/CAnimationValue::SetDefaultValue.md)|既定値を設定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationValue::GetAnimationVariableList](../Topic/CAnimationValue::GetAnimationVariableList.md)|カプセル化されたアニメーション変数をリストに格納します。  \([CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md) をオーバーライドします\)。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CAnimationValue::operator DOUBLE](../Topic/CAnimationValue::operator%20DOUBLE.md)|CAnimationValue と DOUBLE の間で変換を行えるようにします。|  
|[CAnimationValue::operator INT32](../Topic/CAnimationValue::operator%20INT32.md)|CAnimationValue と INT32 の間で変換を行えるようにします。|  
|[CAnimationValue::operator\=](../Topic/CAnimationValue::operator=.md)|オーバーロードされます。  CAnimationValue に INT32 値を割り当てます。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAnimationValue::m\_value](../Topic/CAnimationValue::m_value.md)|アニメーションの値を表すカプセル化されたアニメーション変数。|  
  
## 解説  
 CAnimationValue クラスは、1 つの CAnimationVariable オブジェクトをカプセル化し、アニメーション化される単一の値をアプリケーションで表すことができます。  このクラスは、たとえば、アニメーション化される透明度 \(フェード効果\) や角度 \(オブジェクトを回転する場合\) など、アニメーション化される単一の値に依存するアニメーションを作成する必要がある場合に使用できます。  このクラスをアプリケーションで使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController::AddAnimationObject を使用してアニメーション コントローラーに追加し、値に適用する遷移ごとに AddTransition を呼び出します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationValue](../../mfc/reference/canimationvalue-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)