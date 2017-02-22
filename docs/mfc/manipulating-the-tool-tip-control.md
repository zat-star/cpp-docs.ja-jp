---
title: "ツール ヒント コントロールの操作 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolTipCtrl クラス, 操作 (ツール ヒント属性を)"
  - "ツール ヒント [C++], 属性"
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ツール ヒント コントロールの操作
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス `CToolTipCtrl` は `CToolTipCtrl` オブジェクトとツール ヒント ウィンドウのさまざまな属性を制御するメンバー関数のグループが用意されています。  
  
 ツール ヒント ウィンドウの初期ウィンドウ、ポップアップ ウィンドウ、および reshow の長さは [GetDelayTime](../Topic/CToolTipCtrl::GetDelayTime.md) と [SetDelayTime](../Topic/CToolTipCtrl::SetDelayTime.md)への呼び出しに設定され、取得することができます。  
  
 次の関数のツール ヒント ウィンドウの外観を変更する:  
  
-   [GetMargin](../Topic/CToolTipCtrl::GetMargin.md) と [SetMargin](../Topic/CToolTipCtrl::SetMargin.md)はツール ヒントの境界とツールヒント テキストの間で幅を取得し、設定します。  
  
-   [GetMaxTipWidth](../Topic/CToolTipCtrl::GetMaxTipWidth.md) と [SetMaxTipWidth](../Topic/CToolTipCtrl::SetMaxTipWidth.md)はツール ヒント ウィンドウの最大幅を取得し、設定します。  
  
-   [GetTipBkColor](../Topic/CToolTipCtrl::GetTipBkColor.md) と [SetTipBkColor](../Topic/CToolTipCtrl::SetTipBkColor.md)はツール ヒント ウィンドウの背景色を取得し、設定します。  
  
-   [GetTipTextColor](../Topic/CToolTipCtrl::GetTipTextColor.md) と [SetTipTextColor](../Topic/CToolTipCtrl::SetTipTextColor.md)はツール ヒント ウィンドウのテキストの色を取得し、設定します。  
  
 重要なメッセージが、**WM\_LBUTTONXXX** メッセージなどの通知されるツール ヒント コントロールにツール ヒント コントロールにメッセージを中継に送る必要があります。  この中継の最適なメソッドは、オーナー ウィンドウの `PreTranslateMessage` 関数 [CToolTipCtrl::RelayEvent](../Topic/CToolTipCtrl::RelayEvent.md)への呼び出しを行うことです。  次の例は、1 種類の可能なメソッドを示しています。\(ツール ヒント コントロールを `m_ToolTip`と呼ばれます\) とする:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#41](../mfc/codesnippet/CPP/manipulating-the-tool-tip-control_1.cpp)]  
  
 このツール ヒント ウィンドウを削除するには、[pop](../Topic/CToolTipCtrl::Pop.md) メンバー関数を呼び出します。  
  
## 参照  
 [CToolTipCtrl の使い方](../mfc/using-ctooltipctrl.md)   
 [コントロール](../mfc/controls-mfc.md)