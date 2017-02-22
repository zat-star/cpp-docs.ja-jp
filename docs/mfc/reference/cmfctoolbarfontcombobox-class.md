---
title: "CMFCToolBarFontComboBox クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarFontComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarFontComboBox クラス"
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CMFCToolBarFontComboBox クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

システム フォントの一覧からユーザーがフォントを選択するための、コンボ ボックス コントロールを含むツール バーのボタンです。  
  
## 構文  
  
```  
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](../Topic/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox.md)|`CMFCToolBarFontComboBox` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md)|コンボ ボックス内の指定されたインデックスに対応する `CMFCFontInfo` オブジェクトへのポインターを返します。|  
|[CMFCToolBarFontComboBox::SetFont](../Topic/CMFCToolBarFontComboBox::SetFont.md)|フォント名またはフォントのプレフィックスと文字セットに従って、フォント コンボ ボックス内のフォントを選択します。|  
  
### データ メンバー  
 [CMFCToolBarFontComboBox::m\_nFontHeight](../Topic/CMFCToolBarFontComboBox::m_nFontHeight.md)  
 フォント コンボ ボックスの文字の高さ。  
  
## 解説  
 ツール バーにフォント コンボ ボックス ボタンを追加するには、次の手順を実行します。  
  
1.  親ツール バー リソースでボタンのダミー リソース ID を予約します。  
  
2.  `CMFCToolBarFontComboBox` オブジェクトを構築します。  
  
3.  `AFX_WM_RESETTOOLBAR` メッセージを処理するメッセージ ハンドラーで、[CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) を使用して元のボタンを新しいコンボ ボックス ボタンに置き換えます。  
  
4.  [CMFCToolBarFontComboBox::SetFont](../Topic/CMFCToolBarFontComboBox::SetFont.md) メソッドを使用して、コンボ ボックスで選択されたフォントをどく内のフォントと同期させます。  
  
 ドキュメントのフォントをコンボ ボックスで選択されたフォントと同期させるには、[CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md) メソッドを使用して選択されたフォントの属性を取得し、その属性を使用して [CFont クラス](../../mfc/reference/cfont-class.md) オブジェクトを作成します。  
  
 フォント コンボ ボックス ボタンは Win32 関数の [EnumFontFamiliesEx](http://msdn.microsoft.com/library/windows/desktop/dd162620) を呼び出して、システムで使用できるスクリーン フォントとプリンター フォントを判断します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../Topic/CMFCToolBarComboBoxButton%20Class.md)  
  
 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)  
  
## 必要条件  
 **ヘッダー :** afxtoolbarfontcombobox.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton クラス](../Topic/CMFCToolBarComboBoxButton%20Class.md)   
 [CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)