---
title: "ステータス バーの作成方法 | Microsoft Docs"
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
  - "CStatusBar クラス, および CStatusBarCtrl"
  - "CStatusBarCtrl クラス, 作成"
  - "CStatusBarCtrl クラス, および CStatusBar"
  - "メソッド [MFC]"
  - "メソッド [MFC], 作成 (ステータス バーを)"
  - "ステータス バー, 作成"
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ステータス バーの作成方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC がステータス バーを作成するための 2 種類のクラスが用意されています。: [CStatusBar](../mfc/reference/cstatusbar-class.md) と [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) \(Windows コモン コントロール API をラップする\)。  `CStatusBar` がステータス バー コモン コントロールの機能がすべて用意されている、メニュー、およびツール バーによって自動的にやり取りし、の必須のコモン コントロールの設定と構造の多くを処理します; ただし、生成された実行可能ファイルには、通常 `CStatusBarCtrl`を使用して作成された、より大きい。  
  
 `CStatusBarCtrl` は 通常は、実行可能ファイルになり、MFC アーキテクチャにステータス バーを統合する場合を除き `CStatusBarCtrl` を使用した方がよい場合があります。  `CStatusBarCtrl` を使用し、MFC アーキテクチャにステータス バーを統合する場合は、MFC とステータス バー コントロールの操作を伝える追加注意を払う必要があります。  この通信は困難ではありません; ただし、`CStatusBar`を使用する場合は、追加の不要な作業です。  
  
 Visual C\+\+ では、ステータス バー コモン コントロールを使用する 2 とおりの方法を示します。  
  
-   ステータス バーを `CStatusBar`を使用して作成し、`CStatusBarCtrl` のメンバー関数へのアクセスを取得するに [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md) を呼び出します。  
  
-   [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) のコンストラクターを使用して、ステータス バーを作成します。  
  
 どちらのメソッドはステータス バー コントロールのメンバー関数へのアクセスを提供します。  `CStatusBar::GetStatusBarCtrl`を呼び出すと、`CStatusBarCtrl` オブジェクトへの参照を返すため、メンバー関数のいずれかを使用して設定できます。  `CStatusBar`を使用して、ステータス バーを構築し、作成する方法については、" [CStatusBar](../mfc/reference/cstatusbar-class.md) を参照してください。  
  
## 参照  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)