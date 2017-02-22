---
title: "ツール バー コントロールでのドロップダウン ボタンの使い方 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TBN_DROPDOWN"
  - "TBSTYLE_EX_DRAWDDARROWS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl クラス, ドロップダウン ボタン"
  - "ドロップダウン ボタン (ツール バーの)"
  - "TBN_DROPDOWN 通知"
  - "TBSTYLE_EX_DRAWDDARROWS"
  - "ツール バー [C++], ドロップダウン ボタン"
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ツール バー コントロールでのドロップダウン ボタンの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ツール バーには、標準的なプッシュ ボタンだけでなく、ドロップダウン ボタンを含めることもできます。  通常、ドロップダウン ボタンは、下向きの矢印によって示されます。  
  
> [!NOTE]
>  この下向きの矢印は、`TBSTYLE_EX_DRAWDDARROWS` 拡張スタイルが設定されている場合にだけ表示されます。  
  
 ユーザーがこの矢印 \(矢印が表示されていない場合はボタン自体\) をクリックすると、`TBN_DROPDOWN` 通知メッセージがツール バー コントロールの親に送られます。  Internet Explorer の動作と同様、この通知によってポップアップ メニューを表示できます。  
  
 ポップアップ メニューを表示するドロップダウン ツール バー ボタンを実装する方法を示す手順は、次のとおりです。  
  
### ドロップダウン ボタンを実装するには  
  
1.  `CToolBarCtrl` オブジェクトが作成されたら、次のコードを使用して `TBSTYLE_EX_DRAWDDARROWS` スタイルを設定します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]  
  
2.  ドロップダウン ボタンにする新規のボタン \([InsertButton](../Topic/CToolBarCtrl::InsertButton.md) または [AddButtons](../Topic/CToolBarCtrl::AddButtons.md)\) あるいは既存のボタン \([SetButtonInfo](../Topic/CToolBarCtrl::SetButtonInfo.md)\) すべてに対して `TBSTYLE_DROPDOWN` スタイルを設定します。  次のコードは、`CToolBarCtrl` オブジェクトの既存のボタンを変更する例です。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]  
  
3.  `TBN_DROPDOWN` ハンドラーをツール バー オブジェクトの親クラスに追加します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]  
  
4.  新しいハンドラーでは、適切なポップアップ メニューを表示します。  その例を次に示します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/CPP/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]  
  
## 参照  
 [CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)