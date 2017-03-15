---
title: "OnIdle メンバー関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OnIdle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinApp クラス, OnIdle メソッド"
  - "アイドル ループ処理"
  - "メッセージ処理, OnIdle メソッド"
  - "OnIdle メソッド"
  - "処理 (メッセージを)"
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OnIdle メンバー関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows メッセージが処理されていないと、フレームワークは [CWinApp](../mfc/reference/cwinapp-class.md) のメンバー関数 [OnIdle](../Topic/CWinApp::OnIdle.md) を呼び出します \(MFC ライブラリの"で説明されている\)。  
  
 バックグラウンド タスクを実行 `OnIdle` オーバーライド。  既定のバージョンは、ツール バー ボタンのようなユーザー インターフェイス オブジェクトの状態を更新し、操作中にフレームワークによって作成される一時オブジェクトのクリーンアップを実行します。  次の図は、キューにメッセージがない場合、メッセージ ループが `OnIdle` を呼び出す方法について説明します。  
  
 ![メッセージ ループ プロセス](../mfc/media/vc387c1.gif "vc387C1")  
メッセージ ループ  
  
 アイドル ループで実行できる機能の詳細については [アイドル ループ処理](../Topic/Idle%20Loop%20Processing.md)を参照します。  
  
## 参照  
 [CWinApp : アプリケーション クラス](../Topic/CWinApp:%20The%20Application%20Class.md)