---
title: "CMFCDropDownToolBar クラス | Microsoft Docs"
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
  - "CMFCDropDownToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownToolBar クラス"
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
caps.latest.revision: 37
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDropDownToolBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユーザーがトップレベルのツール バー ボタンを押し続けたときに表示されるツール バーです。  
  
## 構文  
  
```  
class CMFCDropDownToolBar : public CMFCToolBar  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](../Topic/CMFCDropDownToolBar::AllowShowOnPaneMenu.md)|\(`CPane::AllowShowOnPaneMenu` をオーバーライドします。\)|  
|[CMFCDropDownToolBar::LoadBitmap](../Topic/CMFCDropDownToolBar::LoadBitmap.md)|\([CMFCToolBar::LoadBitmap](../Topic/CMFCToolBar::LoadBitmap.md) をオーバーライドします。\)|  
|[CMFCDropDownToolBar::LoadToolBar](../Topic/CMFCDropDownToolBar::LoadToolBar.md)|\([CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md) をオーバーライドします。\)|  
|[CMFCDropDownToolBar::OnLButtonUp](../Topic/CMFCDropDownToolBar::OnLButtonUp.md)||  
|[CMFCDropDownToolBar::OnMouseMove](../Topic/CMFCDropDownToolBar::OnMouseMove.md)||  
|[CMFCDropDownToolBar::OnSendCommand](../Topic/CMFCDropDownToolBar::OnSendCommand.md)|\(`CMFCToolBar::OnSendCommand` をオーバーライドします。\)|  
|[CMFCDropDownToolBar::OnUpdateCmdUI](../Topic/CMFCDropDownToolBar::OnUpdateCmdUI.md)|\([CMFCToolBar::OnUpdateCmdUI](http://msdn.microsoft.com/ja-jp/571a38ab-2a56-4968-9796-273516126f80) をオーバーライドします。\)|  
  
### 解説  
 `CMFCDropDownToolBar` オブジェクトは、ツール バーの外観をポップアップ メニューの動作と組み合わせます。  ユーザーがドロップダウン ツール バー ボタンを押し続けると \(「[CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)」を参照\)、ドロップダウン ツール バーが表示されます。ドロップダウン ツール バーを目的のボタンまでスクロールしてマウス ボタンを離すと、そのボタンを選択できます。  ドロップダウン ツール バーでユーザーがボタンを選択すると、そのボタンはトップレベル ツール バーの現在のボタンとして表示されます。  
  
 ドロップダウン ツール バーは、カスタマイズやドッキングができません。また、ティアオフ状態もありません。  
  
 次の図に、`CMFCDropDownToolBar` オブジェクトを示します。  
  
 ![CMFCDropDownToolbar の例](../../mfc/reference/media/cmfcdropdown.png "CMFCDropDown")  
  
 `CMFCDropDownToolBar` オブジェクトは、通常のツール バーを作成するときと同じ方法で作成します \(「[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)」を参照してください\)。  
  
 ドロップダウン ツール バーを親ツール バーに挿入するには  
  
 1.  親ツール バー リソースでボタンのダミー リソース ID を予約します。  
  
 2.  ドロップダウン ツール バーを含む `CMFCDropDownToolBarButton` オブジェクトを作成します \(詳細については、「[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../Topic/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton.md)」を参照してください\)。  
  
 3.  [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) を使用して、ダミー ボタンを `CMFCDropDownToolBarButton` オブジェクトに置き換えます。  
  
 ツール バー ボタンの詳細については、「[チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)」を参照してください。  ドロップダウン ツール バーの例については、サンプル プロジェクト VisualStudioDemo を参照してください。  
  
## 使用例  
 `CMFCDropDownToolBar` クラスでの `Create` メソッドの使用方法を示す例を次に示します。  このコード スニペットは [Visual Studio のデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/reference/codesnippet/CPP/cmfcdropdowntoolbar-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/reference/codesnippet/CPP/cmfcdropdowntoolbar-class_2.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)  
  
## 必要条件  
 **ヘッダー :** afxdropdowntoolbar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)   
 [チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)