---
title: "タブ コントロールの通知メッセージの処理 | Microsoft Docs"
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
  - "CTabCtrl クラス, 処理 (通知を)"
  - "通知, 処理 (CTabCtrl での)"
  - "通知, タブ コントロール"
  - "処理 (通知を)"
  - "タブ コントロール, 処理 (通知を)"
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# タブ コントロールの通知メッセージの処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーがタブまたはボタンをクリックすると、タブ コントロール \([CTabCtrl](../Topic/CTabCtrl%20Class.md)\) が親ウィンドウに通知メッセージを送信します。  応答の操作を実行する場合は、このメッセージを処理してください。  たとえば、ユーザーがタブをクリックすると、表示する前に、ページのコントロール データを事前設定することもできます。  
  
 ビューやダイアログ クラスのタブ コントロールの **WM\_NOTIFY** プロセス メッセージ。  どの通知メッセージが switch ステートメントに基づいて作成にプロパティ ウィンドウを処理されていると [OnChildNotify](../Topic/CWnd::OnChildNotify.md) のハンドラー関数を使用します。  タブ コントロールの親ウィンドウに送信できる広告リストに [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [タブ コントロールの参照](http://msdn.microsoft.com/library/windows/desktop/bb760548) の **通知** "を参照してください。  
  
## 参照  
 [CTabCtrl の使い方](../mfc/using-ctabctrl.md)   
 [コントロール](../mfc/controls-mfc.md)