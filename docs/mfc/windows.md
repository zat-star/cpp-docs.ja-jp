---
title: "Windows | Microsoft Docs"
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
  - "MFC [C++], ウィンドウ"
  - "オブジェクト [C++], ウィンドウ"
  - "ウィンドウ オブジェクト [C++], MFC フレームワーク"
  - "ウィンドウ [C++]"
ms.assetid: dd92bf34-842e-40fe-8aea-3028b55314d5
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、MFC フレームワーク ウィンドウ オブジェクトについて説明します。  すべての MFC ウィンドウは、フレーム ウィンドウ、ビュー、ダイアログ ボックスやコントロールなど、[CWnd](../Topic/CWnd%20Class.md)クラスから派生します。  
  
 記事の最初のグループは [ウィンドウ オブジェクト](../mfc/window-objects.md) を表します。  子ウィンドウなど、独自のウィンドウを作成する場合、HWND をカプセル化する方法、およびそれらを使用するか、C\+\+ ウィンドウ オブジェクトに関する一般的な情報については、この Groups "を参照してください。  
  
 記事の 2 番目のグループはコンテンツにフレームを囲む [フレーム ウィンドウ](../mfc/frame-windows.md)—ウィンドウ \(機能について説明します。  MFC フレームワークは構築内容とコントロール バーとビューを含むフレーム ウィンドウをどのように管理するかについての詳細については、この Groups "を参照してください。  
  
## さらに詳しくは次のトピックをクリックしてください  
 *一般に、ウィンドウ オブジェクトのトピック*  
  
-   [ウィンドウ オブジェクト](../mfc/window-objects.md)  
  
-   [C \+\+.のウィンドウ オブジェクトに HWND のハンドル間の関係](../Topic/Relationship%20Between%20a%20C++%20Window%20Object%20and%20an%20HWND.md)  
  
-   [派生クラスのウィンドウ](../Topic/Derived%20Window%20Classes.md)  
  
-   [ウィンドウ オブジェクトの作成](../Topic/Creating%20Windows.md)  
  
-   [分割ウィンドウ オブジェクト](../mfc/destroying-window-objects.md)  
  
-   [ウィンドウに、「登録は設定します」。](../mfc/registering-window-classes.md)  
  
-   [ウィンドウ オブジェクトの使用](../Topic/Working%20with%20Window%20Objects.md)  
  
-   [デバイス コンテキスト](../Topic/Device%20Contexts.md): デバイスに依存しないの描画を行う Windows オブジェクト  
  
-   [グラフィック オブジェクト](../mfc/graphic-objects.md): ペン、ブラシ、フォント、ビットマップ、パレット、領域  
  
 *フレーム ウィンドウに関するトピック*  
  
-   [フレーム ウィンドウ](../mfc/frame-windows.md): フレーム ウィンドウ オブジェクトを提供します。  
  
-   [フレーム ウィンドウとビュー](../mfc/frame-windows.md)  
  
-   [フレームウィンドウ クラス](../mfc/frame-window-classes.md)  
  
-   [フレーム ウィンドウ スタイル](../Topic/Frame-Window%20Styles%20\(C++\).md)  
  
-   [MFC によって作成されたウィンドウのスタイルを変更する](../Topic/Changing%20the%20Styles%20of%20a%20Window%20Created%20by%20MFC.md)  
  
-   [どのフレーム ウィンドウです。](../mfc/what-frame-windows-do.md)  
  
-   [フレーム ウィンドウを使用する](../Topic/Using%20Frame%20Windows.md)  
  
-   [管理 MD\/Child ウィンドウ \(MDICLIENT ウィンドウ\)](../mfc/managing-mdi-child-windows.md)  
  
-   [管理メニュー、コントロール バーおよびアクセラレータ](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [CFrameWnd](../mfc/reference/cframewnd-class.md)  
  
-   [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
  
-   [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
  
-   [ビューを使用する](../mfc/using-views.md)  
  
-   [複数のドキュメントの種類、ビュー、およびフレーム ウィンドウ \(分割ウィンドウ\)](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [メッセージ マップ \(およびハンドラー関数\)](../mfc/messages.md)  
  
 *Windows の作成と破棄します。*  
  
-   [概要ウィンドウの作成手順](../mfc/general-window-creation-sequence.md)  
  
-   [ウィンドウ オブジェクトを破棄します。](../mfc/destroying-window-objects.md)  
  
-   [ドキュメント フレーム ウィンドウを作成します。](../Topic/Creating%20Document%20Frame%20Windows.md)  
  
-   [フレーム ウィンドウを破棄します。](../mfc/destroying-frame-windows.md)  
  
 *分割ウィンドウを作成します。*  
  
-   [分割ウィンドウを作成します。](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
 *子ウィンドウ、現在のビューを管理します。*  
  
-   [MDI 子ウィンドウを管理します。](../mfc/managing-mdi-child-windows.md)  
  
-   [現在のビューを管理します。](../mfc/managing-the-current-view.md)  
  
-   [メニュー コントロール バーとアクセラレータを管理します。](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
 *デバイス コンテキストの Window Styles を使用します。*  
  
-   [デバイス コンテキストのペンなどのグラフィック オブジェクトを使用します。](../mfc/graphic-objects.md)  
  
-   [MFC によって作成されたウィンドウのスタイルを変更します。](../Topic/Changing%20the%20Styles%20of%20a%20Window%20Created%20by%20MFC.md)  
  
## 参照  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)   
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [ツール バー](../mfc/toolbars.md)   
 [ステータス バー](../mfc/status-bars.md)   
 [ダイアログ バー](../mfc/dialog-bars.md)