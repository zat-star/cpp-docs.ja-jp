---
title: "CToolBarCtrl オブジェクトの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CToolBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl クラス, 作成 (ツール バーを)"
  - "ツール バー コントロール [MFC], 作成"
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CToolBarCtrl オブジェクトの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) オブジェクト を複数の内部のデータ構造—リスト、および `TBBUTTON` 構造体のボタンのラベルの文字列のボタン イメージのビットマップのリスト—をその関連ボタンの位置、スタイル、状態とコマンド ID を持つイメージや文字列が含まれます。  これらのデータ構造体の各要素は 0 から始まるインデックスで参照されます。  `CToolBarCtrl` オブジェクトを使用する前に、これらのデータ構造を設定する必要があります。  データ構造の一覧については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [ツールバー コントロール](https://msdn.microsoft.com/en-us/library/47xcww9x.aspx) を参照してください。  文字列の一覧にボタンのラベルにのみ使用できません; ツールバーから文字列を取得できません。  
  
 `CToolBarCtrl` オブジェクトを使用するには、通常、これらの手順を実行します。:  
  
### CToolBarCtrl オブジェクトを使用するには  
  
1.  [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) オブジェクトを構築します。  
  
2.  Windows ツール バー コモン コントロールを作成し、`CToolBarCtrl` オブジェクトに接続するに [作成](../Topic/CToolBarCtrl::Create.md) を呼び出します。  ボタンのビットマップ イメージが必要な場合は、[AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md)を呼び出して、ツール バーのボタンのビットマップを追加します。  ボタンの文字列ラベルが必要な場合は、[AddString](../Topic/CToolBarCtrl::AddString.md) と [AddStrings](../Topic/CToolBarCtrl::AddStrings.md)を呼び出して、ツール バーに文字列を追加します。  `AddString` と `AddStrings`を呼び出した後、表示する文字列を取得するに [自動サイズ調整](../Topic/CToolBarCtrl::AutoSize.md) を呼び出す必要があります。  
  
3.  [AddButtons](../Topic/CToolBarCtrl::AddButtons.md)を呼び出して、ツール バー ボタンに構造を追加します。  
  
4.  ツール ヒントが必要な場合は、[処理のツール ヒントの通知](../mfc/handling-tool-tip-notifications.md)"に説明されているように、ツール バーのオーナー ウィンドウの **TTN\_NEEDTEXT** メッセージを処理してください。  
  
5.  ユーザーがツール バーをカスタマイズできるよう [通知処理のカスタマイズ](../Topic/Handling%20Customization%20Notifications.md)"に説明されているように、オーナー ウィンドウのカスタマイズの通知メッセージを処理してください。  
  
## 参照  
 [CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)