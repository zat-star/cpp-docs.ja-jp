---
title: "ヘッダー コントロール通知の処理 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CHeaderCtrl クラス, 処理 (通知を)"
  - "コントロール [MFC], ヘッダー"
  - "ヘッダー コントロール通知"
  - "ヘッダー コントロール, 処理 (通知を)"
  - "通知, 処理 (CHeaderCtrl の)"
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ヘッダー コントロール通知の処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ビューやダイアログ クラスで処理したいすべてのヘッダー コントロール[CHeaderCtrl](../Topic/CHeaderCtrl%20Class.md) \(\) の通知メッセージの switch ステートメントと [OnChildNotify](../Topic/CWnd::OnChildNotify.md) のハンドラー関数を作成するには、プロパティ ウィンドウを使用します。[関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)を参照してください。  通知が親ウィンドウにユーザーがヘッダー項目をクリックするか、ダブルクリックすると、インポートされた項目間の区分線が使用されます。  
  
 ヘッダー コントロールに関連付けられた通知メッセージが [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [ヘッダー コントロールの参照](http://msdn.microsoft.com/library/windows/desktop/bb775239) に一覧表示されます。  
  
## 参照  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)