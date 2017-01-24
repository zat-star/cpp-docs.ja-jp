---
title: "MFC で使用するスタイル | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.styles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ボタン, MFC ツール バー"
  - "コンボ ボックス, スタイル"
  - "エディット スタイル [MFC]"
  - "拡張ウィンドウ スタイル"
  - "フレーム ウィンドウ, スタイル"
  - "リスト ボックス, スタイル"
  - "メッセージ ボックス スタイル"
  - "スクロール バー スタイル [MFC]"
  - "静的なスタイル"
  - "スタイル"
  - "スタイル, MFC"
  - "ウィンドウ スタイル, MFC で"
ms.assetid: d3b9af37-31b5-4c97-a8ad-189fd724b04c
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC で使用するスタイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

以下のスタイルを使用して、対応する MFC オブジェクトを作成します。  ほとんどの場合、以下のスタイルはクラスの **Create** 関数の `dwStyle` パラメーターで設定します。  
  
### MFC スタイル  
  
|スタイル|説明|  
|----------|--------|  
|[ボタン スタイル](../../mfc/reference/button-styles.md)|オプション ボタン、チェック ボックス、プッシュ ボタンなどの [CButton クラス](../../mfc/reference/cbutton-class.md) オブジェクトに適用されます。  [CButton::Create](../Topic/CButton::Create.md) の `dwStyle` パラメーターに、スタイルを組み合わせて指定します。|  
|[コンボ ボックス スタイル](../../mfc/reference/combo-box-styles.md)|[CComboBox クラス](../../mfc/reference/ccombobox-class.md) オブジェクトに適用されます。  [CComboBox::Create](../Topic/CComboBox::Create.md) の `dwStyle` パラメーターに、スタイルを組み合わせて指定します。|  
|[エディット スタイル](../../mfc/reference/edit-styles.md)|[CEdit クラス](../Topic/CEdit%20Class.md) オブジェクトに適用されます。  [CEdit::Create](../Topic/CEdit::Create.md) の `dwStyle` パラメーターに、スタイルを組み合わせて指定します。|  
|[フレーム ウィンドウ スタイル](../../mfc/reference/frame-window-styles-mfc.md)|[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md) オブジェクトに適用されます。  [CFrameWnd::Create](../Topic/CFrameWnd::Create.md) の `dwStyle` パラメーターに、スタイルを組み合わせて指定します。|  
|[リスト ボックス スタイル](../../mfc/reference/list-box-styles.md)|[CListBox クラス](../Topic/CListBox%20Class.md) オブジェクトに適用されます。  [CListBox::Create](../Topic/CListBox::Create.md) の `dwStyle` パラメーターに、スタイルを組み合わせて指定します。|  
|[メッセージ ボックス スタイル](../../mfc/reference/message-box-styles.md)|[AfxMessageBox](../Topic/AfxMessageBox.md) アイテムに適用されます。  `AfxMessageBox` の `nType` パラメーターに、スタイルを組み合わせて指定します。|  
|[スクロール バー スタイル](../../mfc/reference/scroll-bar-styles.md)|[CScrollBar クラス](../../mfc/reference/cscrollbar-class.md) オブジェクトに適用されます。  [CScrollBar::Create](../Topic/CScrollBar::Create.md) の `dwStyle` パラメーターに、スタイルを組み合わせて指定します。|  
|[静的コントロール スタイル](../../mfc/reference/static-styles.md)|[CStatic クラス](../Topic/CStatic%20Class.md) オブジェクトに適用されます。  [CStatic::Create](../Topic/CStatic::Create.md) の `dwStyle` パラメーターに、スタイルを組み合わせて指定します。|  
|[ウィンドウ スタイル](../Topic/Window%20Styles.md)|[CWnd クラス](../Topic/CWnd%20Class.md) オブジェクトに適用されます。  [CWnd::Create](../Topic/CWnd::Create.md) または [CWnd::CreateEx](../Topic/CWnd::CreateEx.md) の `dwStyle` パラメーターに、スタイルを組み合わせて指定します。|  
|[拡張ウィンドウ スタイル](../Topic/Extended%20Window%20Styles.md)|[CWnd クラス](../Topic/CWnd%20Class.md) オブジェクトに適用されます。  [CWnd::CreateEx](../Topic/CWnd::CreateEx.md) の `dwExStyle` パラメーターに、スタイルを組み合わせて指定します。|  
  
## 参照  
 [クラスの概要](../../mfc/class-library-overview.md)