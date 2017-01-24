---
title: "ツール ヒントの通知の処理 | Microsoft Docs"
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
  - "CToolBarCtrl クラス, 処理 (通知を)"
  - "通知, ツール ヒント"
  - "ツール ヒント [C++], 通知"
  - "TOOLTIPTEXT 構造体"
ms.assetid: ddb93b5f-2e4f-4537-8053-3453c86e2bbb
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ツール ヒントの通知の処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`TBSTYLE_TOOLTIPS` スタイルを指定している場合、ツール バーではツール ヒント コントロールが作成され、管理されます。  ツール ヒントとは、ツール バー ボタンについて説明する 1 行のテキストを表示する小さなポップアップ ウィンドウのことです。  ツール ヒントは、ユーザーがツール バー ボタンの上にマウス ポインターを約 0.5 秒置いたままにしたときだけ表示され、通常は非表示になっています。  ツール ヒントはポインターの近くに表示されます。  
  
 ツール ヒントが表示される前に、ボタンの説明テキストを取得するために **TTN\_NEEDTEXT** 通知メッセージがツール バーのオーナー ウィンドウに送られます。  ツール バーのオーナー ウィンドウが `CFrameWnd` ウィンドウの場合、特に何もしなくてもツール ヒントは表示されます。`CFrameWnd` には既定で **TTN\_NEEDTEXT** 通知用のハンドラーが用意されているからです。  ツール バーのオーナー ウィンドウが、ダイアログ ボックスやフォーム ビューなど、`CFrameWnd` から派生されたものではない場合は、オーナー ウィンドウのメッセージ マップにエントリを追加して、メッセージ マップに通知ハンドラーを用意する必要があります。  オーナー ウィンドウのメッセージ マップのエントリは、次のようになります。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/CPP/handling-tool-tip-notifications_1.cpp)]  
  
## 解説  
 `memberFxn`  
 対象のボタンに対してテキストが必要になったときに呼び出すメンバー関数。  
  
 ツール ヒントの ID は常に 0 です。  
  
 **TTN\_NEEDTEXT** 通知のほかに、ツール ヒント コントロールは以下の通知をツール バー コントロールに送ることができます。  
  
|通知|説明|  
|--------|--------|  
|**TTN\_NEEDTEXTA**|ツール ヒント コントロールが ASCII テキストを使用することを示します \(Windows 95 のみ\)。|  
|**TTN\_NEEDTEXTW**|ツール ヒント コントロールが UNICODE テキストを使用することを示します \(Windows NT のみ\)。|  
|**TBN\_HOTITEMCHANGE**|ホット アイテム \(強調表示されている項目\) が変更されたことを示します。|  
|**NM\_RCLICK**|ユーザーがボタンを右クリックしたことを示します。|  
|**TBN\_DRAGOUT**|ユーザーがボタンをクリックし、ボタンからポインターをドラッグしたことを示します。  これにより、アプリケーションにツール バー ボタンからのドラッグ アンド ドロップを実装できるようになります。  この通知を受け取ると、アプリケーションはドラッグ アンド ドロップ操作を開始します。|  
|**TBN\_DROPDOWN**|**TBSTYLE\_DROPDOWN** スタイルを使用するボタンをユーザーがクリックしたことを示します。|  
|**TBN\_GETOBJECT**|**TBSTYLE\_DROPPABLE** スタイルを使用するボタン上にユーザーがポインターを移動したことを示します。|  
  
 ハンドラー関数の例とツール ヒントを有効にする詳細については、「[CFrameWnd から派生していないウィンドウのツール ヒント](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)」を参照してください。  
  
## 参照  
 [CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)