---
title: "CAnimationPoint クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimationPoint"
  - "afxanimationcontroller/CAnimationPoint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationPoint クラス"
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CAnimationPoint クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

座標をアニメーション化できる点の機能を実装します。  
  
## 構文  
  
```  
class CAnimationPoint : public CAnimationBaseObject;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAnimationPoint::CAnimationPoint](../Topic/CAnimationPoint::CAnimationPoint.md)|オーバーロードされます。  CAnimationPoint オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationPoint::AddTransition](../Topic/CAnimationPoint::AddTransition.md)|X 座標および Y 座標の遷移を追加します。|  
|[CAnimationPoint::GetDefaultValue](../Topic/CAnimationPoint::GetDefaultValue.md)|X 座標および Y 座標の既定値を返します。|  
|[CAnimationPoint::GetValue](../Topic/CAnimationPoint::GetValue.md)|現在の値を返します。|  
|[CAnimationPoint::GetX](../Topic/CAnimationPoint::GetX.md)|X 座標の CAnimationVariable にアクセスできるようにします。|  
|[CAnimationPoint::GetY](../Topic/CAnimationPoint::GetY.md)|Y 座標の CAnimationVariable にアクセスできるようにします。|  
|[CAnimationPoint::SetDefaultValue](../Topic/CAnimationPoint::SetDefaultValue.md)|既定値を設定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationPoint::GetAnimationVariableList](../Topic/CAnimationPoint::GetAnimationVariableList.md)|カプセル化されたアニメーション変数をリストに格納します。  \([CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md) をオーバーライドします\)。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CAnimationPoint::operator CPoint](../Topic/CAnimationPoint::operator%20CPoint.md)|CAnimationPoint を CPoint に変換します。|  
|[CAnimationPoint::operator\=](../Topic/CAnimationPoint::operator=.md)|CAnimationPoint に ptSrc を割り当てます。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAnimationPoint::m\_xValue](../Topic/CAnimationPoint::m_xValue.md)|アニメーションの点の X 座標を表すカプセル化されたアニメーション変数。|  
|[CAnimationPoint::m\_yValue](../Topic/CAnimationPoint::m_yValue.md)|アニメーションの点の Y 座標を表すカプセル化されたアニメーション変数。|  
  
## 解説  
 CAnimationPoint クラスは、2 つの CAnimationVariable オブジェクトをカプセル化し、アプリケーションで点を表すことができます。  たとえば、このクラスを使用して、画面上のオブジェクト \(テキスト文字列、円、点など\) の位置をアニメーション化することができます。  このクラスをアプリケーションで使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController::AddAnimationObject を使用してアニメーション コントローラーに追加し、X 座標または Y 座標、あるいはその両方に適用する遷移ごとに AddTransition を呼び出します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationPoint](../../mfc/reference/canimationpoint-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)