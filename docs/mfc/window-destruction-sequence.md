---
title: "ウィンドウの破棄順序 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "CWnd オブジェクト, 破棄の順序"
  - "破棄 (ウィンドウを)"
  - "破棄, ウィンドウ"
  - "手順 [C++]"
  - "手順 [C++], ウィンドウの破棄"
  - "ウィンドウ [C++], 破棄"
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ウィンドウの破棄順序
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC フレームワークでは、ユーザーがフレーム ウィンドウを閉じるときには、ウィンドウの既定の [OnClose](../Topic/CWnd::OnClose.md) ハンドラーは [DestroyWindow](../Topic/CWnd::DestroyWindow.md)を呼び出します。  ウィンドウが破棄される Windows のクリーンアップを実行するときに呼び出されるをクリーンアップする最後のメンバー関数は、[OnNcDestroy](../Topic/CWnd::OnNcDestroy.md)の呼び出し [既定](../Topic/CWnd::Default.md) メンバー関数で最後に仮想メンバー関数 [PostNcDestroy](../Topic/CWnd::PostNcDestroy.md)を呼び出します。  `PostNcDestroy` の [CFrameWnd](../mfc/reference/cframewnd-class.md) の実装は C\+\+ のウィンドウ オブジェクトを削除します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [ウィンドウのメモリの割り当てと解放します](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [HWND から CWnd をデタッチする](../Topic/Detaching%20a%20CWnd%20from%20Its%20HWND.md)  
  
## 参照  
 [ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)