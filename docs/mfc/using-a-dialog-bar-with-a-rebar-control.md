---
title: "Rebar コントロールでのダイアログ バーの使い方 | Microsoft Docs"
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
  - "WM_EX_TRANSPARENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ダイアログ バー, 使用 (rebar バンドで)"
  - "rebar コントロール, ダイアログ バー"
  - "WS_EX_TRANSPARENT スタイル"
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Rebar コントロールでのダイアログ バーの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Rebar コントロールとバンド](../mfc/rebar-controls-and-bands.md)に記述されているように、各バンドに 1 個の子ウィンドウできます \(またはコントロールのみ\) が含まれます。  これは、バンドごとに複数の子ウィンドウが場合に制限がある場合があります。  便利な代替手段は、ダイアログ バーのリソースを複数のコントロールを作成し、rebar コントロールへの rebar バンド \(ダイアログ バーを含む\) を追加します。  
  
 通常、ダイアログ バー バンドは透明に表示され、ダイアログ バー オブジェクトの **WS\_EX\_TRANSPARENT** の拡張スタイルを設定します。  ただし、**WS\_EX\_TRANSPARENT** に正しくダイアログ バーの背景を描画するための問題があるため、必要な効果を得るために、追加の作業を少しする必要があります。  
  
 次の手順では **WS\_EX\_TRANSPARENT** の拡張スタイルを使用せずに透過性を設定するために必要な手順を詳しく説明します。  
  
### rebar バンドの透明ダイアログ バーを実装するには  
  
1.  [クラスの追加ダイアログ ボックスを追加します。](../mfc/reference/adding-an-mfc-class.md)を使用して、新しいクラス \(`CMyDlgBar`\) 実装ダイアログ バーのオブジェクトを追加します。  
  
2.  `WM_ERASEBKGND` メッセージのハンドラーを追加します。  
  
3.  new ハンドラーで、次の例に示すように既存のコードを変更する:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/CPP/using-a-dialog-bar-with-a-rebar-control_1.cpp)]  
  
4.  `WM_MOVE` メッセージのハンドラーを追加します。  
  
5.  new ハンドラーで、次の例に示すように既存のコードを変更する:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/CPP/using-a-dialog-bar-with-a-rebar-control_2.cpp)]  
  
 new ハンドラーは `WM_ERASEBKGND` メッセージを親ウィンドウに転送し、再描画を強制することにより、ダイアログ バーのオブジェクトが移動するたびに、ダイアログ バーの透過性をシミュレートします。  
  
## 参照  
 [CReBarCtrl の使い方](../Topic/Using%20CReBarCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)