---
title: "アニメーション コントロールによる通知の送信 | Microsoft Docs"
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
  - "アニメーション コントロール [C++], 通知"
  - "CAnimateCtrl クラス, 通知"
  - "コントロール [MFC], アニメーション"
  - "通知, アニメーション コントロール"
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# アニメーション コントロールによる通知の送信
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アニメーション コントロール \([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)\) は通知メッセージの 2 種類を送信します。  通知は [WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) メッセージの形式で送信されます。  
  
 [ACN\_START](http://msdn.microsoft.com/library/windows/desktop/bb761891) メッセージがアニメーション コントロールがクリップを開始して送信されます。  [ACN\_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893) メッセージがアニメーション コントロールがクリップを終了または止めたら送信されます。  
  
## 参照  
 [CAnimateCtrl の使い方](../Topic/Using%20CAnimateCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)