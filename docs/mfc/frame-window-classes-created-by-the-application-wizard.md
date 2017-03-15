---
title: "アプリケーション ウィザードで作成されるフレーム ウィンドウ クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CMainFrame"
  - "CMainFrame::PreCreateWindow"
  - "CMainFrame.PreCreateWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプリケーション ウィザード [C++], フレーム ウィンドウ クラス (作成された)"
  - "CFrameWnd クラス, フレーム ウィンドウ"
  - "クラス [C++], フレーム ウィンドウ"
  - "CMainFrame クラス"
  - "CMDIChildWnd クラス, フレーム ウィンドウ"
  - "CMDIFrameWnd クラス, フレーム ウィンドウ"
  - "フレーム ウィンドウ クラス, 作成 (アプリケーション ウィザードで)"
  - "ウィンドウ クラス"
  - "ウィンドウ クラス, フレーム"
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# アプリケーション ウィザードで作成されるフレーム ウィンドウ クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーション、ドキュメント、ビュー クラスに加えてスケルトン アプリケーションを作成するために [アプリケーション ウィザード](../ide/creating-desktop-projects-by-using-application-wizards.md) を使用するときは、アプリケーション ウィザードでは、アプリケーションのメイン フレーム ウィンドウの派生のフレーム ウィンドウを作成します。  クラスは `CMainFrame` とともに呼び出され、それを含むファイルは MAINFRM.H と MAINFRM.CPP という名前です。  
  
 SDI アプリケーションでは、`CMainFrame` クラスは [CFrameWnd](../mfc/reference/cframewnd-class.md)クラスから派生されます。  
  
 MDI アプリケーションでは、`CMainFrame` は [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)クラスから派生されます。  この場合 `CMainFrame` は、メニュー、ツール バーとステータス バーを保持するメイン フレームを実装します。  アプリケーション ウィザードによって新しいドキュメント フレーム ウィンドウ クラスを派生しません。  代わりに、[CMDIChildWnd クラス](../mfc/reference/cmdichildwnd-class.md)の既定の実装を使用します。  MFC フレームワークは、その `CScrollView`、`CEditView`、`CTreeView`、`CListView`、含める各ビューに子ウィンドウを作成\) アプリケーションが必要です。  ドキュメント フレーム ウィンドウをカスタマイズする場合、新しいドキュメント フレーム ウィンドウを作成できます。[クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)を参照してください。  
  
 ツール バーをサポートしている場合は、クラス型 [CToolBar](../mfc/reference/ctoolbar-class.md) と [CStatusBar](../mfc/reference/cstatusbar-class.md) のメンバー変数と `OnCreate` メッセージハンドラー関数の 2 [コントロール バー](../Topic/Control%20Bars.md)を初期化するです。  
  
 これらのフレーム ウィンドウ クラスを作成できるようになっていますが、機能を強化するために、メンバー変数とメンバー関数を追加する必要があります。  また、ウィンドウ クラスを他の Windows メッセージを処理してようにすることもできます。  詳細については、「[MFC によって作成されたウィンドウのスタイルを変更する](../Topic/Changing%20the%20Styles%20of%20a%20Window%20Created%20by%20MFC.md)」を参照してください。  
  
## 参照  
 [フレーム ウィンドウ クラス](../mfc/frame-window-classes.md)   
 [MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル](../ide/mfc-program-or-control-source-and-header-files.md)