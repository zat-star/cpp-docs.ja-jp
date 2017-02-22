---
title: "フレーム ウィンドウの機能 | Microsoft Docs"
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
  - "フレーム ウィンドウ, フレーム ウィンドウの概要"
  - "フレーム ウィンドウ, タスク"
  - "MFC, フレーム ウィンドウ"
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# フレーム ウィンドウの機能
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ビューを作成するだけでなく、フレーム ウィンドウとビューはアプリケーションとフレームの調整に関連する多くのタスクを行います。  [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) と [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) は [CFrameWnd](../mfc/reference/cframewnd-class.md)から継承します。したがって、追加する `CFrameWnd` の機能および新機能があります。  子ウィンドウの例として、ビュー、コントロール、およびツール バー、ステータス バー、ダイアログ バーを含むボタンやリスト ボックスなどのコントロール バーが含まれます。  
  
 フレーム ウィンドウまたは子ウィンドウのレイアウトを管理する必要があります。  MFC フレームワークでは、フレーム ウィンドウのクライアント領域内のコントロール バー、ビュー、およびそのほかの子ウィンドウを配置します。  
  
 フレーム ウィンドウは、ビューに順方向に並べて、コントロール ウィンドウからの通知メッセージに応答できます。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [\(フレーム ウィンドウに適用方法\) コントロール バー](../Topic/Control%20Bars.md)  
  
-   [\(フレーム ウィンドウに適用方法\) 管理メニュー、コントロール バーおよびアクセラレータ](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [Command Routing \(フレーム ウィンドウからビュー、およびそのほかのコマンド ターゲットへの\)](../mfc/command-routing.md)  
  
-   [ドキュメントの \/View アーキテクチャ](../Topic/Document-View%20Architecture.md)  
  
-   [コントロール バー](../Topic/Control%20Bars.md)  
  
-   [コントロール](../mfc/controls-mfc.md)  
  
## 参照  
 [フレーム ウィンドウ](../mfc/frame-windows.md)