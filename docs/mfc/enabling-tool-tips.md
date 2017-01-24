---
title: "ツール ヒントを有効にする方法 | Microsoft Docs"
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
  - "有効化 (ツール ヒントを)"
  - "初期化 (ツール ヒントを)"
  - "ツール ヒント [C++], 有効化"
  - "ツール ヒント [C++], 初期化"
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ツール ヒントを有効にする方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ウィンドウの子コントロールのツール ヒントをサポートできるようにすることができます \(フォーム ビューまたはダイアログ ボックスのコントロールなど\)。  
  
### ウィンドウの子コントロールのツールヒントを有効にするには  
  
1.  、ツール ヒントを提供するウィンドウの `EnableToolTips` を呼び出します。  
  
2.  [TTN\_NEEDTEXT 通知](../Topic/Handling%20TTN_NEEDTEXT%20Notification%20for%20Tool%20Tips.md) ハンドラーの各コントロールに文字列を指定します。  ハンドラーは、子コントロール \(たとえば、フォーム ビュー クラス\) を含むウィンドウのメッセージ マップにあります。  このハンドラーでは、コントロールを識別し、ツール ヒント コントロールで使用されるテキストを指定するに **pszText** を設定する関数を呼び出す必要があります。  
  
## 参照  
 [CFrameWnd から派生していないウィンドウのツール ヒント](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)