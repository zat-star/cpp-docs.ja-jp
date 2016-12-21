---
title: "CReBar と CReBarCtrl の比較 | Microsoft Docs"
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
  - "CReBar"
  - "CReBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBar クラス, および CReBarCtrl"
  - "GetReBarCtrl クラス"
  - "rebar コントロール, CReBarCtrl クラス"
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CReBar と CReBarCtrl の比較
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC は rebars を作成するための 2 種類のクラスが用意されています。: [CReBar](../mfc/reference/crebar-class.md) と [CReBarCtrl](../mfc/reference/crebarctrl-class.md) \(Windows コモン コントロール API をラップする\)。  **CReBar** は Rebar コモン コントロールの機能を提供し、の必須のコモン コントロールの設定と構造の多くを処理します。  
  
 したがって`CReBarCtrl` は MFC アーキテクチャに Rebar を統合する場合を除き、Win32 rebar のコントロールのラッパー クラスで、より実装し簡単に場合があります。  `CReBarCtrl` を使用し、MFC アーキテクチャに Rebar を統合する場合は、MFC と rebar コントロール操作を伝える追加注意を払う必要があります。  この通信は困難ではありません; ただし、**CReBar**を使用する場合は、追加の不要な作業です。  
  
 Visual C\+\+ は、Rebar コモン コントロールを使用する 2 とおりの方法を示します。  
  
-   Rebar の **CReBar**を使用して作成し、`CReBarCtrl` のメンバー関数へのアクセスを取得するに [CReBar::GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md) を呼び出します。  
  
    > [!NOTE]
    >  `CReBar::GetReBarCtrl` は Rebar オブジェクトの **this** のポインターをキャストするインライン メンバー関数です。  これは、実行時、関数呼び出しのオーバーヘッドがないことを意味します。  
  
-   [CReBarCtrl](../mfc/reference/crebarctrl-class.md) のコンストラクターを使用して rebar を作成します。  
  
 どちらのメソッドは、Rebar コントロールのメンバー関数にアクセスできます。  `CReBar::GetReBarCtrl`を呼び出すと、`CReBarCtrl` オブジェクトへの参照を返すため、メンバー関数のいずれかを使用して設定できます。  **CReBar**を使用して rebar を構築し、作成する方法については、" [CReBar](../mfc/reference/crebar-class.md) を参照してください。  
  
## 参照  
 [CReBarCtrl の使い方](../Topic/Using%20CReBarCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)