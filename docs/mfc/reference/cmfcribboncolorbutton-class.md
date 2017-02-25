---
title: "CMFCRibbonColorButton クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonColorButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonColorButton クラス"
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 38
---
# CMFCRibbonColorButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonColorButton` クラスは、リボン バーに追加できるカラー ボタンを実装します。 リボンのカラー ボタンは、1 つまたは複数のカラー パレットを含むドロップダウン メニューを表示します。  
  
## 構文  
  
```  
class CMFCRibbonColorButton : public CMFCRibbonGallery  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonColorButton::CMFCRibbonColorButton](../Topic/CMFCRibbonColorButton::CMFCRibbonColorButton.md)||  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonColorButton::AddColorsGroup](../Topic/CMFCRibbonColorButton::AddColorsGroup.md)|色のグループを通常の色領域に追加します。|  
|[CMFCRibbonColorButton::EnableAutomaticButton](../Topic/CMFCRibbonColorButton::EnableAutomaticButton.md)|**\[自動\]** ボタンを有効にするかどうかを指定します。|  
|[CMFCRibbonColorButton::EnableOtherButton](../Topic/CMFCRibbonColorButton::EnableOtherButton.md)|**\[その他\]** ボタンを有効にします。|  
|[CMFCRibbonColorButton::GetAutomaticColor](../Topic/CMFCRibbonColorButton::GetAutomaticColor.md)||  
|[CMFCRibbonColorButton::GetColor](../Topic/CMFCRibbonColorButton::GetColor.md)|現在選ばれている色を返します。|  
|[CMFCRibbonColorButton::GetColorBoxSize](../Topic/CMFCRibbonColorButton::GetColorBoxSize.md)|カラー バーに表示される色要素のサイズを返します。|  
|[CMFCRibbonColorButton::GetColumns](../Topic/CMFCRibbonColorButton::GetColumns.md)||  
|[CMFCRibbonColorButton::GetHighlightedColor](../Topic/CMFCRibbonColorButton::GetHighlightedColor.md)|ポップアップ カラー パレットで現在選ばれている要素の色を返します。|  
|[CMFCRibbonColorButton::RemoveAllColorGroups](../Topic/CMFCRibbonColorButton::RemoveAllColorGroups.md)|通常の色領域からすべての色グループを削除します。|  
|[CMFCRibbonColorButton::SetColor](../Topic/CMFCRibbonColorButton::SetColor.md)|通常の色領域から色を選びます。|  
|[CMFCRibbonColorButton::SetColorBoxSize](../Topic/CMFCRibbonColorButton::SetColorBoxSize.md)|カラー バーに表示されるすべての色要素のサイズを設定します。|  
|[CMFCRibbonColorButton::SetColorName](../Topic/CMFCRibbonColorButton::SetColorName.md)||  
|[CMFCRibbonColorButton::SetColumns](../Topic/CMFCRibbonColorButton::SetColumns.md)||  
|[CMFCRibbonColorButton::SetDocumentColors](../Topic/CMFCRibbonColorButton::SetDocumentColors.md)|ドキュメントの色領域に表示する RGB 値の一覧を指定します。|  
|[CMFCRibbonColorButton::SetPalette](../Topic/CMFCRibbonColorButton::SetPalette.md)||  
|[CMFCRibbonColorButton::UpdateColor](../Topic/CMFCRibbonColorButton::UpdateColor.md)||  
  
## 解説  
 ユーザーがリボンのカラー ボタンを押すと、カラー バーが表示されます。 既定では、このカラー バーには通常の色領域と呼ばれる色選択パレットが含まれます。 必要に応じて、カラー バーには **\[自動\]** ボタン \(これを使用するとユーザーは既定の色を選択できます\)、および **\[その他\]** ボタン \(追加の色を含むポップアップ カラー パレットが表示されます\) を表示できます。  
  
## 使用例  
 `CMFCRibbonColorButton` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、`CMFCRibbonColorButton` オブジェクトの構築、大きいイメージの設定、**\[自動\]** ボタンの有効化、**\[その他\]** ボタンの有効化、列数の設定、カラー バーに表示されるすべての色要素のサイズの設定、通常の色領域への色グループの追加、ドキュメントの色領域に表示する RGB 値の一覧の指定方法を示します。 このコード スニペットは、「[クライアント サンプルの描画](../../top/visual-cpp-samples.md)」の一部です。  
  
 [!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/CPP/cmfcribboncolorbutton-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)  
  
## 必要条件  
 **ヘッダー:** afxribboncolorbutton.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCRibbonGallery クラス](../../mfc/reference/cmfcribbongallery-class.md)