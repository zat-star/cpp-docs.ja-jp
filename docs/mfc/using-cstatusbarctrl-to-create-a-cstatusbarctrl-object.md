---
title: "CStatusBarCtrl を使用して CStatusBarCtrl オブジェクトを作成する方法 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl クラス, 作成"
  - "ステータス バー コントロール, 作成"
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CStatusBarCtrl を使用して CStatusBarCtrl オブジェクトを作成する方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)の一般的な使用方法の例を次に示します。:  
  
### パーツとのステータス バー コントロールを使用するには  
  
1.  `CStatusBarCtrl` オブジェクトを構築します。  
  
2.  ステータス バー コントロールの描画領域の最小の高さを設定するには、呼び出し [SetMinHeight](../Topic/CStatusBarCtrl::SetMinHeight.md)。  
  
3.  ステータス バー コントロールの背景色を設定する呼び出し [SetBkColor](../Topic/CStatusBarCtrl::SetBkColor.md)。  
  
4.  ステータス バー コントロールの一部の数と各部分の右端の座標を設定する呼び出し [SetParts](../Topic/CStatusBarCtrl::SetParts.md)。  
  
5.  ステータス バー コントロールの特定の部分のテキストを設定する呼び出し [SetText](../Topic/CStatusBarCtrl::SetText.md)。  メッセージは、次のコントロールが `WM_PAINT` メッセージを受け取ったときに新しいテキストを表示し、変更したコントロールの部分が無効になります。  
  
 場合によっては、ステータス バーのテキスト行を表示するだけです。  この場合、[SetSimple](../Topic/CStatusBarCtrl::SetSimple.md)に呼び出しを行ってください。  これは、単一行のテキストを表示する「単純な」モードでは、ステータス バー コントロールを送信します。  
  
## 参照  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)