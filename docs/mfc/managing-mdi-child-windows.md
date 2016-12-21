---
title: "MDI 子ウィンドウの管理 | Microsoft Docs"
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
  - "MDICLIENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "子ウィンドウ"
  - "子ウィンドウ, および MDICLIENT ウィンドウ"
  - "フレーム ウィンドウ [C++], MDI 子ウィンドウ"
  - "MDI [C++], 子ウィンドウ"
  - "MDI [C++], フレーム ウィンドウ"
  - "[クイック ウォッチ] ウィンドウ"
  - "ウィンドウ [C++], MDI"
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MDI 子ウィンドウの管理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MDI メイン フレーム ウィンドウ \(アプリケーションごとに 1\) は **MDICLIENT** ウィンドウと呼ばれる特別な子ウィンドウが含まれています。  **MDICLIENT** ウィンドウは、メイン フレーム ウィンドウのクライアント領域自体を管理し、子ウィンドウを持つ: ドキュメント ウィンドウは、`CMDIChildWnd`から派生します。  ドキュメント ウィンドウがフレーム ウィンドウ自体 \(MDI 子ウィンドウ\) であるため、独自の子を持っている可能性があります。  これらすべてのケースでは、親ウィンドウでは、子ウィンドウ、前後にあるコマンドを管理します。  
  
 MDI フレーム ウィンドウで、フレーム ウィンドウ、コントロール バーとともにそれを再配置 **MDICLIENT** ウィンドウを管理します。  **MDICLIENT** ウィンドウは、すべての MDI 子フレーム ウィンドウを管理します。  次の図は、MDI フレーム ウィンドウ、**MDICLIENT** ウィンドウと子ドキュメント フレーム ウィンドウの関係を示します。  
  
 ![MDI フレーム ウィンドウの子ウィンドウ](../mfc/media/vc37gb1.gif "vc37GB1")  
MDI フレーム ウィンドウと子ウィンドウ  
  
 MDI フレーム ウィンドウには、現在の MDI 子ウィンドウとともに 1 がある場合は、それも使用できます。  MDI フレーム ウィンドウが MDI 子自体にそれらを処理する前にコマンド メッセージに委任します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [ドキュメント フレーム ウィンドウの作成](../Topic/Creating%20Document%20Frame%20Windows.md)  
  
-   [フレーム ウィンドウ スタイル](../Topic/Frame-Window%20Styles%20\(C++\).md)  
  
## 参照  
 [フレーム ウィンドウの使用](../Topic/Using%20Frame%20Windows.md)