---
title: "ウィンドウ オブジェクトの破棄 | Microsoft Docs"
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
  - "フレーム ウィンドウ, 破棄"
  - "ウィンドウ オブジェクト, 削除"
  - "ウィンドウ オブジェクト, 破棄"
  - "ウィンドウ オブジェクト, 削除"
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ウィンドウ オブジェクトの破棄
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

注意が独自の子ウィンドウによってユーザーがウィンドウで終了すると C\+\+ ウィンドウ オブジェクトを破棄する必要があります。  これらのオブジェクトが破棄され、アプリケーションがメモリを復元します。  しかし、フレームワークは、フレーム ウィンドウ、ビューとダイアログ ボックスのウィンドウの破棄、または作成を管理します。  他のウィンドウを作成する場合、その破棄する必要があります。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [ウィンドウの破棄シーケンス](../mfc/window-destruction-sequence.md)  
  
-   [ウィンドウのメモリの割り当てと解放します](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [HWND から CWnd をデタッチする](../Topic/Detaching%20a%20CWnd%20from%20Its%20HWND.md)  
  
-   [概要ウィンドウの作成手順](../mfc/general-window-creation-sequence.md)  
  
-   [破棄のフレーム ウィンドウ](../mfc/destroying-frame-windows.md)  
  
## 参照  
 [ウィンドウ オブジェクト](../mfc/window-objects.md)