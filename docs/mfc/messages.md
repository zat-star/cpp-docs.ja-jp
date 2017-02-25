---
title: "メッセージ | Microsoft Docs"
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
  - "メッセージ"
  - "メッセージ, MFC"
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# メッセージ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス `CWinApp` の **実行** のメンバー関数のメッセージ ループはさまざまなイベントによって生成されたキューに配置されたメッセージを取得します。  たとえば、ユーザーがマウスをクリックしたときに、Windows は、マウスの左ボタンを離すと、マウスの左ボタンを押すと `WM_LBUTTONUP``WM_LBUTTONDOWN` などのマウス関連のメッセージは送信します。  フレームワークによってアプリケーションのメッセージ ループの実装は適切なウィンドウにメッセージをディスパッチします。  
  
 メッセージの重要なカテゴリは [メッセージの分類項目](../mfc/message-categories.md)で説明します。  
  
## 参照  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)