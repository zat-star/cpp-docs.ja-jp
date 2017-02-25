---
title: "CMFCColorMenuButton クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorMenuButton クラス"
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CMFCColorMenuButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCColorMenuButton` クラスは、カラー ピッカー ダイアログ ボックスを起動するメニュー コマンドまたはツール バーのボタンをサポートします。  
  
## 構文  
  
```  
class CMFCColorMenuButton : public CMFCToolBarMenuButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorMenuButton::CMFCColorMenuButton](../Topic/CMFCColorMenuButton::CMFCColorMenuButton.md)|`CMFCColorMenuButton` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorMenuButton::EnableAutomaticButton](../Topic/CMFCColorMenuButton::EnableAutomaticButton.md)|標準のカラー ボタンの上にある "自動" ボタンを有効または無効にします   \(標準システムの自動ボタンのラベルは **\[自動\]** です\)。|  
|[CMFCColorMenuButton::EnableDocumentColors](../Topic/CMFCColorMenuButton::EnableDocumentColors.md)|システム カラーの代わりにドキュメント固有の色を表示できるようにします。|  
|[CMFCColorMenuButton::EnableOtherButton](../Topic/CMFCColorMenuButton::EnableOtherButton.md)|標準のカラー ボタンの下にある "その他" ボタンを有効または無効にします   \(標準的なシステムの "その他" ボタンのラベルは **\[More Colors\]** です\)。|  
|[CMFCColorMenuButton::EnableTearOff](../Topic/CMFCColorMenuButton::EnableTearOff.md)|カラー ペインのティアオフ機能を有効にします。|  
|[CMFCColorMenuButton::GetAutomaticColor](../Topic/CMFCColorMenuButton::GetAutomaticColor.md)|現在の自動設定の色を取得します。|  
|[CMFCColorMenuButton::GetColor](../Topic/CMFCColorMenuButton::GetColor.md)|現在のボタンの色を取得します。|  
|[CMFCColorMenuButton::GetColorByCmdID](../Topic/CMFCColorMenuButton::GetColorByCmdID.md)|指定されたコマンド ID に対応する色を取得します。|  
|[CMFCColorMenuButton::OnChangeParentWnd](../Topic/CMFCColorMenuButton::OnChangeParentWnd.md)|親ウィンドウが変更されたときに、フレームワークによって呼び出されます。|  
|[CMFCColorMenuButton::OpenColorDialog](../Topic/CMFCColorMenuButton::OpenColorDialog.md)|色を選択するためのダイアログ ボックスを開きます。|  
|[CMFCColorMenuButton::SetColor](../Topic/CMFCColorMenuButton::SetColor.md)|現在のカラー ボタンの色を設定します。|  
|[CMFCColorMenuButton::SetColorByCmdID](../Topic/CMFCColorMenuButton::SetColorByCmdID.md)|指定されたカラー メニュー ボタンの色を設定します。|  
|[CMFCColorMenuButton::SetColorName](../Topic/CMFCColorMenuButton::SetColorName.md)|指定した色の新しい名前を設定します。|  
|[CMFCColorMenuButton::SetColumnsNumber](../Topic/CMFCColorMenuButton::SetColumnsNumber.md)|`CMFCColorBar` オブジェクトにより表示される列数を設定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorMenuButton::CopyFrom](../Topic/CMFCColorMenuButton::CopyFrom.md)|別のツール バー ボタンを現在のボタンにコピーします。|  
|[CMFCColorMenuButton::CreatePopupMenu](../Topic/CMFCColorMenuButton::CreatePopupMenu.md)|カラー ピッカー ダイアログ ボックスを作成します。|  
|[CMFCColorMenuButton::IsEmptyMenuAllowed](../Topic/CMFCColorMenuButton::IsEmptyMenuAllowed.md)|空のメニューがサポートされるかどうかを示します。|  
|[CMFCColorMenuButton::OnDraw](../Topic/CMFCColorMenuButton::OnDraw.md)|ボタンのイメージを表示するために、フレームワークによって呼び出されます。|  
|[CMFCColorMenuButton::OnDrawOnCustomizeList](../Topic/CMFCColorMenuButton::OnDrawOnCustomizeList.md)|ツール バー カスタマイズ ダイアログ ボックスの一覧に `CMFCColorMenuButton` オブジェクトが表示される前に、フレームワークによって呼び出されます。|  
  
## 解説  
 元のメニュー コマンドまたはツール バー ボタンを `CMFCColorMenuButton` オブジェクトと置き換えるには、`CMFCColorMenuButton` オブジェクトを作成して適切な [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md) スタイルを設定し、[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md) クラスの `ReplaceButton` メソッドを呼び出します。  ツール バーをカスタマイズする場合は、[CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md) メソッドを呼び出します。  
  
 [CMFCColorMenuButton::CreatePopupMenu](../Topic/CMFCColorMenuButton::CreatePopupMenu.md) イベント ハンドラーの処理中に、カラー ピッカー ダイアログ ボックスが作成されます。  イベント ハンドラーは、`WM_COMMAND` メッセージによって親フレームに通知します。  `CMFCColorMenuButton` オブジェクトは、元のメニュー コマンドまたはツール バー ボタンに割り当てられたコントロール ID を送信します。  
  
## 使用例  
 `CMFCColorMenuButton` クラスのさまざまなメソッドを使用して、カラー メニュー ボタンを作成して設定する方法を次の例に示します。  この例では、まず `CPalette` オブジェクトを作成した後、このオブジェクトを使用して `CMFCColorMenuButton` クラスのオブジェクトを構築します。  次に、"自動" ボタンと "その他" ボタンを有効にしてその色と列数を設定することで、`CMFCColorMenuButton` オブジェクトを設定します。  このコードは [Word のスペースのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/CPP/cmfccolormenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/CPP/cmfccolormenubutton-class_2.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
 [CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)  
  
## 必要条件  
 **ヘッダー :** afxcolormenubutton.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)   
 [CMFCColorButton クラス](../../mfc/reference/cmfccolorbutton-class.md)