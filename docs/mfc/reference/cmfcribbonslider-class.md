---
title: "CMFCRibbonSlider クラス | Microsoft Docs"
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
  - "CMFCRibbonSlider"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonSlider クラス"
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
caps.latest.revision: 43
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonSlider クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonSlider` クラスは、リボン バーまたはリボン ステータス バーに追加できるスライダー コントロールを実装します。  リボン スライダー コントロールは、Office 2007 アプリケーションに表示されるズーム スライダーに似ています。  
  
## 構文  
  
```  
class CMFCRibbonSlider : public CMFCRibbonBaseElement  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonSlider::CMFCRibbonSlider](../Topic/CMFCRibbonSlider::CMFCRibbonSlider.md)|リボン スライダー コントロールを構築および初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonSlider::GetPos](../Topic/CMFCRibbonSlider::GetPos.md)|スライダー コントロールの現在の位置を返します。|  
|[CMFCRibbonSlider::GetRangeMax](../Topic/CMFCRibbonSlider::GetRangeMax.md)|スライダー内の最大値を返します。|  
|[CMFCRibbonSlider::GetRangeMin](../Topic/CMFCRibbonSlider::GetRangeMin.md)|スライダーの最小値を返します。|  
|[CMFCRibbonSlider::GetRegularSize](../Topic/CMFCRibbonSlider::GetRegularSize.md)|リボン要素の標準サイズを返します。  \([CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md) をオーバーライドします。\)|  
|[CMFCRibbonSlider::GetZoomIncrement](../Topic/CMFCRibbonSlider::GetZoomIncrement.md)|スライダー コントロールのズーム インクリメントのサイズを返します。|  
|[CMFCRibbonSlider::HasZoomButtons](../Topic/CMFCRibbonSlider::HasZoomButtons.md)|スライダーにズーム ボタンがあるかどうかを示します。|  
|[CMFCRibbonSlider::OnDraw](../Topic/CMFCRibbonSlider::OnDraw.md)|リボン要素を描画するために、フレームワークによって呼び出されます。  \([CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md) をオーバーライドします。\)|  
|[CMFCRibbonSlider::SetPos](../Topic/CMFCRibbonSlider::SetPos.md)|スライダー コントロールの現在の位置を設定します。|  
|[CMFCRibbonSlider::SetRange](../Topic/CMFCRibbonSlider::SetRange.md)|スライダー コントロールの範囲を、最大値と最小値を設定することによって指定します。|  
|[CMFCRibbonSlider::SetZoomButtons](../Topic/CMFCRibbonSlider::SetZoomButtons.md)|ズーム ボタンの表示と非表示を切り替えます。|  
|[CMFCRibbonSlider::SetZoomIncrement](../Topic/CMFCRibbonSlider::SetZoomIncrement.md)|スライダー コントロールのズーム インクリメントのサイズを設定します。|  
  
## 解説  
 `SetRange` メソッドを使用して、スライダーのズーム インクリメントの範囲を設定できます。  `SetPos` メソッドを使用することで、スライダーの現在の位置を設定できます。  
  
 `SetZoomButtons` メソッドを使用してスライダー コントロールの左側または右側に円形のズーム ボタンを表示できます。  既定では、スライダーは水平方向で、左のズーム ボタンにマイナス記号、右のズーム ボタンにプラス記号が表示されます。  
  
 `SetZoomIncrement` メソッドは、ユーザーがズーム ボタンをクリックしたときに現在の位置に対して増減するインクリメントを定義します。  
  
## 使用例  
 次の例は、スライダーのプロパティを設定する `CMFCRibbonSlider` クラスのさまざまなメソッドの使用方法を示しています。  `CMFCRibbonSlider` オブジェクトの構築、ズーム ボタンの表示、スライダー コントロールの現在位置の設定、スライダー コントロールの値の範囲の設定の方法を示しています。  
  
 [!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/CPP/cmfcribbonslider-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)  
  
## 必要条件  
 **ヘッダー :** afxribbonslider.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCRibbonBaseElement クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)