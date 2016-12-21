---
title: "CWnd オブジェクトの初期化のタイミング | Microsoft Docs"
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
  - "CWnd オブジェクト, HWND が結び付けられるタイミング"
  - "CWnd オブジェクト, 初期化のタイミング"
  - "HWND, CWnd オブジェクトに結び付けられるタイミング"
  - "初期化 (CWnd オブジェクトを)"
  - "初期化 (オブジェクトを), CWnd"
  - "ウィンドウ オブジェクト, 初期化のタイミング (CWnd を)"
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWnd オブジェクトの初期化のタイミング
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

独自の子ウィンドウを作成するか、`CWnd`\-派生オブジェクトのコンストラクターで Windows API 関数を呼び出すことはできません。  これは `CWnd` オブジェクトの `HWND` がまだ作成されていないためです。  子ウィンドウの追加などのほとんどのウィンドウ固有の初期化は、[OnCreate](../Topic/CWnd::OnCreate.md) のメッセージ ハンドラーで、する必要があります。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [ドキュメント フレーム ウィンドウの作成](../Topic/Creating%20Document%20Frame%20Windows.md)  
  
-   [ドキュメント\/ビューの作成](../mfc/document-view-creation.md)  
  
## 参照  
 [フレーム ウィンドウの使用](../Topic/Using%20Frame%20Windows.md)