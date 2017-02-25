---
title: "リスト コントロールでの通知メッセージの処理 | Microsoft Docs"
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
  - "CListCtrl クラス, 処理 (通知を)"
  - "処理 (通知を)"
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# リスト コントロールでの通知メッセージの処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーが列ヘッダーをクリックすると、アイコンを編集親ウィンドウにラベルなど、リスト コントロール \([CListCtrl](../Topic/CListCtrl%20Class.md)\) の通知を送信するメッセージ ドラッグします。  応答の操作を実行する場合は、このメッセージを処理してください。  たとえば、ユーザーが列ヘッダーをクリックすると、Microsoft Outlook のようにクリックした列の内容に基づいて項目を並べ替え場合もあります。  
  
 ビューやダイアログ クラスのリスト コントロールの **WM\_NOTIFY** プロセス メッセージ。  どの通知メッセージが switch ステートメントに基づいて作成にプロパティ ウィンドウを処理されていると [OnChildNotify](../Topic/CWnd::OnChildNotify.md) のハンドラー関数を使用します。  
  
 リスト コントロールを親ウィンドウに送信できる広告リストに [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [リスト ビュー コントロールの参照](http://msdn.microsoft.com/library/windows/desktop/bb774737) を参照してください。  
  
## 参照  
 [CListCtrl の使い方](../Topic/Using%20CListCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)