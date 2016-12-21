---
title: "CAnimationColor クラス | Microsoft Docs"
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
  - "CAnimationColor"
  - "afxanimationcontroller/CAnimationColor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationColor クラス"
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationColor クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

赤、緑、および青の各色要素をアニメーション化できる機能を実装します。  
  
## 構文  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAnimationColor::CAnimationColor](../Topic/CAnimationColor::CAnimationColor.md)|オーバーロードされます。  アニメーション色オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationColor::AddTransition](../Topic/CAnimationColor::AddTransition.md)|赤、緑、および青の各要素の遷移を追加します。|  
|[CAnimationColor::GetB](../Topic/CAnimationColor::GetB.md)|青の要素を表す CAnimationVariable にアクセスできるようにします。|  
|[CAnimationColor::GetDefaultValue](../Topic/CAnimationColor::GetDefaultValue.md)|色要素の既定値を返します。|  
|[CAnimationColor::GetG](../Topic/CAnimationColor::GetG.md)|緑の要素を表す CAnimationVariable にアクセスできるようにします。|  
|[CAnimationColor::GetR](../Topic/CAnimationColor::GetR.md)|赤の要素を表す CAnimationVariable にアクセスできるようにします。|  
|[CAnimationColor::GetValue](../Topic/CAnimationColor::GetValue.md)|現在の値を返します。|  
|[CAnimationColor::SetDefaultValue](../Topic/CAnimationColor::SetDefaultValue.md)|既定値を設定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationColor::GetAnimationVariableList](../Topic/CAnimationColor::GetAnimationVariableList.md)|カプセル化されたアニメーション変数をリストに格納します。  \([CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md) をオーバーライドします\)。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CAnimationColor::operator COLORREF](../Topic/CAnimationColor::operator%20COLORREF.md)||  
|[CAnimationColor::operator\=](../Topic/CAnimationColor::operator=.md)|CAnimationColor に色を割り当てます。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAnimationColor::m\_bValue](../Topic/CAnimationColor::m_bValue.md)|アニメーションの青の色要素を表すカプセル化されたアニメーション変数。|  
|[CAnimationColor::m\_gValue](../Topic/CAnimationColor::m_gValue.md)|アニメーションの緑の色要素を表すカプセル化されたアニメーション変数。|  
|[CAnimationColor::m\_rValue](../Topic/CAnimationColor::m_rValue.md)|アニメーションの赤の色要素を表すカプセル化されたアニメーション変数。|  
  
## 解説  
 CAnimationColor クラスは、3 つの CAnimationVariable オブジェクトをカプセル化し、アプリケーションで色を表すことができます。  たとえば、このクラスを使用して、画面上のオブジェクトの色 \(テキストの色や背景色など\) をアニメーション化することができます。  このクラスをアプリケーションで使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController::AddAnimationObject を使用してアニメーション コントローラーに追加し、赤、緑、および青の各要素に適用する遷移ごとに AddTransition を呼び出します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationColor](../../mfc/reference/canimationcolor-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)