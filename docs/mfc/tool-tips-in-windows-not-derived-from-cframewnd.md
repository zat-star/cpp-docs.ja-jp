---
title: "CFrameWnd から派生していないウィンドウのツール ヒント | Microsoft Docs"
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
  - "コントロール [MFC], ツール ヒント"
  - "有効化 (ツール ヒントを)"
  - "ハンドラー関数, ツール ヒント"
  - "ヘルプ, ツール ヒント (コントロールの)"
  - "TOOLTIPTEXT 構造体"
  - "TTN_NEEDTEXT メッセージ"
ms.assetid: cad5ef0f-02e3-4151-ad0d-3d42e6932b0e
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFrameWnd から派生していないウィンドウのツール ヒント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この記事のファミリには [CFrameWnd](../mfc/reference/cframewnd-class.md)から派生されないウィンドウに含まれるコントロールのツールヒントを有効にする方法について説明します。  記事 [ツールバーのツール ヒント](../Topic/Toolbar%20Tool%20Tips.md) は `CFrameWnd`のコントロールにツール ヒントについて説明します。  
  
 この記事のファミリで説明するトピックは次のとおりです。:  
  
-   [ツール ヒントを有効にする](../mfc/enabling-tool-tips.md)  
  
-   [ツール ヒントの処理 TTN\_NEEDTEXT 通知](../Topic/Handling%20TTN_NEEDTEXT%20Notification%20for%20Tool%20Tips.md)  
  
-   [TOOLTIPTEXT 構造体](../mfc/tooltiptext-structure.md)  
  
 ツール ヒントは `CFrameWnd`から派生される親ウィンドウに含まれるボタンなどのコントロールに自動的に表示されます。  これは `CFrameWnd` にコントロールに関連付けられているツール ヒント コントロールの **TTN\_NEEDTEXT** の通知を処理する [TTN\_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760269) 通知の既定のハンドラーがあるためです。  
  
 ただし、この既定のハンドラーは、**TTN\_NEEDTEXT** 通知を `CFrameWnd`でないダイアログ ボックスやフォーム ビューのコントロールなどのウィンドウのコントロールに関連付けられているツール ヒント コントロールから送られる呼び出されません。  したがって、子コントロールのツールヒントを表示するに **TTN\_NEEDTEXT** 通知メッセージのハンドラー関数を提供する必要があります。  
  
 [CWnd::EnableToolTips](../Topic/CWnd::EnableToolTips.md) してウィンドウに用意されている既定のツール ヒントとそれに関連付けられたテキストはありません。  ツール ヒントのテキストを取得するには **TTN\_NEEDTEXT** の通知は、ツール ヒント コントロールの親ウィンドウに表示するには、ツール ヒント ウィンドウが表示される直前に送信されます。  **TOOLTIPTEXT** 構造体の **pszText** メンバーに値を割り当てるこのメッセージ ハンドラーがあるツール ヒントに表示されているテキストがありません。  
  
## 参照  
 [ツール ヒント](../mfc/tool-tips.md)