---
title: "フレーム ウィンドウ クラス | Microsoft Docs"
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
  - "クラス [C++], ウィンドウ"
  - "ドキュメント フレーム ウィンドウ, クラス"
  - "フレーム ウィンドウ クラス"
  - "フレーム ウィンドウ クラス, フレーム ウィンドウ クラスの概要"
  - "MDI [C++], フレーム ウィンドウ"
  - "MFC [C++], フレーム ウィンドウ"
  - "シングル ドキュメント インターフェイス (SDI), フレーム ウィンドウ"
  - "ウィンドウ クラス, フレーム"
  - "ウィンドウ [C++], MDI"
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# フレーム ウィンドウ クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

各アプリケーションに 1 文字の「メイン フレーム ウィンドウは、通常は」キャプションにアプリケーション名がデスクトップ ウィンドウです。  通常、各ドキュメントに 1 文字の「ドキュメント フレーム ウィンドウである」ドキュメント フレーム ウィンドウは、ドキュメントのデータを示す 1 文字以上のビューが含まれます。  
  
## SDI、MDI アプリケーションのフレーム ウィンドウ  
 SDI アプリケーションでは、[CFrameWnd](../mfc/reference/cframewnd-class.md)クラスから派生される 1 フレーム ウィンドウがあります。  このウィンドウはメイン フレーム ウィンドウとドキュメント フレーム ウィンドウもあります。  MDI アプリケーションでは、メイン フレーム ウィンドウで [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)クラスから派生され、MDI 子ウィンドウであるドキュメント フレーム ウィンドウは [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)クラスから派生されます。  
  
## フレーム ウィンドウを使用するか、から派生してください。  
 これらのクラスには、アプリケーションに必要なフレーム ウィンドウの機能のほとんどを提供します。  通常の状況では、指定された外観および既定の動作は、必要に応じてします。  追加機能が必要な場合は、これらのクラスから派生してください。  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [アプリケーション ウィザードで作成されるフレーム ウィンドウ クラス](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [フレーム ウィンドウ スタイル](../Topic/Frame-Window%20Styles%20\(C++\).md)  
  
-   [MFC によって作成されたウィンドウのスタイルを変更する](../Topic/Changing%20the%20Styles%20of%20a%20Window%20Created%20by%20MFC.md)  
  
## 参照  
 [フレーム ウィンドウ](../mfc/frame-windows.md)