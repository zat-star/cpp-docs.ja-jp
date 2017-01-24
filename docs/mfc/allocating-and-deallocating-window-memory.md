---
title: "ウィンドウ メモリの割り当てと解放 | Microsoft Docs"
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
  - "メモリの割り当て, ウィンドウ オブジェクト"
  - "メモリ解放"
  - "メモリ解放, ウィンドウ メモリ"
  - "ストレージ (ウィンドウ オブジェクトの)"
  - "ストレージ (ウィンドウ オブジェクトの), 割り当て"
  - "ウィンドウ オブジェクト, 解放 (メモリを)"
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ウィンドウ メモリの割り当てと解放
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

フレーム ウィンドウまたはビューを破棄するには、C\+\+ **delete** の演算子を使用しないでください。  代わりに、`CWnd` のメンバー関数 `DestroyWindow`を呼び出します。  したがって、フレーム ウィンドウで演算子を含む **new**ヒープに割り当てる必要があります。  のまたはグローバルのフレーム ウィンドウをスタック フレームの場合は注意してください。  他のウィンドウがスタック フレームに可能な限り割り当てます。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [ウィンドウの作成](../Topic/Creating%20Windows.md)  
  
-   [ウィンドウの破棄シーケンス](../mfc/window-destruction-sequence.md)  
  
-   [HWND から CWnd をデタッチする](../Topic/Detaching%20a%20CWnd%20from%20Its%20HWND.md)  
  
## 参照  
 [ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)