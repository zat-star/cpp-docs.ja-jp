---
title: "ツール バーの作成方法 | Microsoft Docs"
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
  - "CToolBar クラス, 作成 (ツール バーを)"
  - "CToolBarCtrl クラス, および CToolBar クラス"
  - "CToolBarCtrl クラス, 作成 (ツール バーを)"
  - "MFC ツール バー"
  - "ツール バー コントロール [MFC]"
  - "ツール バー コントロール [MFC], 作成"
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ツール バーの作成方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC では、ツール バーを作成するための 2 種類のクラスが用意されています。: [CToolBar](../mfc/reference/ctoolbar-class.md) と [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) \(Windows コモン コントロール API をラップする\)。  `CToolBar` は バー コモン コントロールの機能を提供し、の必須のコモン コントロールの設定と構造の多くを処理します; ただし、生成された実行可能ファイルには、通常 `CToolBarCtrl`を使用して作成された、より大きい。  
  
 `CToolBarCtrl` は 通常は、実行可能ファイルになり、MFC アーキテクチャにツール バーを統合する場合を除き `CToolBarCtrl` を使用した方がよい場合があります。  `CToolBarCtrl` を使用し、MFC アーキテクチャをツール バーに統合する場合は、MFC とツール バー コントロールの操作を伝える追加注意を払う必要があります。  この通信は困難ではありません; ただし、`CToolBar`を使用する場合は、追加の不要な作業です。  
  
 Visual C\+\+ では、バー コモン コントロールを使用する 2 とおりの方法を示します。  
  
-   ツール バーを `CToolBar`を使用して作成し、`CToolBarCtrl` のメンバー関数へのアクセスを取得するに [CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md) を呼び出します。  
  
-   [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) のコンストラクターを使用してツール バーを作成します。  
  
 どちらのメソッドは、ツール バー コントロールのメンバー関数にアクセスできます。  `CToolBar::GetToolBarCtrl`を呼び出すと、`CToolBarCtrl` オブジェクトへの参照を返すため、メンバー関数のいずれかを使用して設定できます。  `CToolBar`を使用してツール バーを作成し、それを作成する方法については、" [CToolBar](../mfc/reference/ctoolbar-class.md) を参照してください。  
  
## 参照  
 [CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)