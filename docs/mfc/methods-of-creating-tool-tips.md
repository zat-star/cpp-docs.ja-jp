---
title: "ツール ヒントの作成方法 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolTipCtrl クラス, 作成 (ツール ヒントを)"
  - "ツール ヒント [C++], 作成"
  - "ツール ヒント [C++], ツール ヒント コントロール"
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ツール ヒントの作成方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC では、ツール ヒント コントロールを作成および管理するための 3 種類のクラスが用意されています。: [CWnd](../Topic/CWnd%20Class.md)、[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)、[CToolTipCtrl](../Topic/CToolTipCtrl%20Class.md) と [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md)。  これらのクラスのツール ヒントのメンバー関数は、Windows コモン コントロール API をラップします。  クラス `CToolBarCtrl` とクラス `CToolTipCtrl` は `CWnd`クラスから派生されます。  
  
 `CWnd` は ツール ヒントを作成および管理するための 4 種類のメンバー関数を提供し、T: [EnableToolTips](../Topic/CWnd::EnableToolTips.md)、[CancelToolTips](../Topic/CWnd::CancelToolTips.md)、[FilterToolTipMessage](../Topic/CWnd::FilterToolTipMessage.md)と [OnToolHitTest](../Topic/CWnd::OnToolHitTest.md)。  ユーザーがツール ヒントをどのように実装する方法については、これらの各メンバー関数を参照してください。  
  
 `CToolBarCtrl`を使用してツール バーを作成する場合は、次のメンバー関数を使用してツール バーのツール ヒントを直接実装する: [GetToolTips](../Topic/CToolBarCtrl::GetToolTips.md) と [SetToolTips](../Topic/CToolBarCtrl::SetToolTips.md)。  ユーザーがツール ヒントをどのように実装する方法については、これらの各メンバー関数と [処理のツール ヒントの通知](../mfc/handling-tool-tip-notifications.md) を参照してください。  
  
 `CToolTipCtrl` クラスは、Windows のツール ヒント コントロールの機能を提供します。  単一のツール ヒント コントロールは、複数のツールに情報を提供できます。  ツール ウィンドウは、子ウィンドウまたはコントロールなど\) またはウィンドウのクライアント領域のアプリケーション定義の四角形領域です。  [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md) クラスは `CToolTipCtrl` から派生し、追加 visual スタイルと機能を提供します。  
  
## 参照  
 [CToolTipCtrl の使い方](../mfc/using-ctooltipctrl.md)   
 [コントロール](../mfc/controls-mfc.md)