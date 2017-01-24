---
title: "CAnimationSize クラス | Microsoft Docs"
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
  - "afxanimationcontroller/CAnimationSize"
  - "CAnimationSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationSize クラス"
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationSize クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

サイズをアニメーション化できるサイズ オブジェクトの機能を実装します。  
  
## 構文  
  
```  
class CAnimationSize : public CAnimationBaseObject;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAnimationSize::CAnimationSize](../Topic/CAnimationSize::CAnimationSize.md)|オーバーロードされます。  アニメーション サイズ オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationSize::AddTransition](../Topic/CAnimationSize::AddTransition.md)|幅および高さの遷移を追加します。|  
|[CAnimationSize::GetCX](../Topic/CAnimationSize::GetCX.md)|幅を表す CAnimationVariable にアクセスできるようにします。|  
|[CAnimationSize::GetCY](../Topic/CAnimationSize::GetCY.md)|高さを表す CAnimationVariable にアクセスできるようにします。|  
|[CAnimationSize::GetDefaultValue](../Topic/CAnimationSize::GetDefaultValue.md)|幅および高さの既定値を返します。|  
|[CAnimationSize::GetValue](../Topic/CAnimationSize::GetValue.md)|現在の値を返します。|  
|[CAnimationSize::SetDefaultValue](../Topic/CAnimationSize::SetDefaultValue.md)|既定値を設定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationSize::GetAnimationVariableList](../Topic/CAnimationSize::GetAnimationVariableList.md)|カプセル化されたアニメーション変数をリストに格納します。  \([CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md) をオーバーライドします\)。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CAnimationSize::operator CSize](../Topic/CAnimationSize::operator%20CSize.md)|CAnimationSize を CSize に変換します。|  
|[CAnimationSize::operator\=](../Topic/CAnimationSize::operator=.md)|CAnimationSize に szSrc を割り当てます。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAnimationSize::m\_cxValue](../Topic/CAnimationSize::m_cxValue.md)|アニメーションのサイズの幅を表すカプセル化されたアニメーション変数。|  
|[CAnimationSize::m\_cyValue](../Topic/CAnimationSize::m_cyValue.md)|アニメーションのサイズの高さを表すカプセル化されたアニメーション変数。|  
  
## 解説  
 CAnimationSize クラスは、2 つの CAnimationVariable オブジェクトをカプセル化し、アプリケーションでサイズを表すことができます。  たとえば、このクラスを使用して、画面上の 2 次元オブジェクト \(四角形やコントロールなど\) のサイズをアニメーション化することができます。  このクラスをアプリケーションで使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController::AddAnimationObject を使用してアニメーション コントローラーに追加し、幅や高さに適用する遷移ごとに AddTransition を呼び出します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationSize](../../mfc/reference/canimationsize-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)