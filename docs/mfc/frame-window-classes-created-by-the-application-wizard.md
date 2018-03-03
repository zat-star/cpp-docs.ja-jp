---
title: "フレーム ウィンドウ クラスがアプリケーションのウィザードによって作成された |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CMainFrame
dev_langs:
- C++
helpviewer_keywords:
- application wizards [MFC], frame window classes created by
- window classes [MFC]
- classes [MFC], frame-window
- CMDIFrameWnd class [MFC], frame windows
- window classes [MFC], frame
- CFrameWnd class [MFC], frame windows
- CMDIChildWnd class [MFC], frame windows
- frame window classes [MFC], created by application wizards
- CMainFrame class [MFC]
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 497dd21bba3e807349b793e3b37e774c833ccb40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>アプリケーション ウィザードで作成されるフレーム ウィンドウ クラス
使用すると、[アプリケーション ウィザード](../ide/creating-desktop-projects-by-using-application-wizards.md)アプリケーション、ドキュメント、およびビューのクラスだけでなく、スケルトン アプリケーションを作成するアプリケーションのウィザードが、アプリケーションのメイン フレーム ウィンドウのフレーム ウィンドウの派生クラスを作成します。 クラスが呼び出されます`CMainFrame`既定値、およびそれを含むファイルという名前がします。H とします。CPP です。  
  
 アプリケーションが SDI の場合、`CMainFrame`クラスから派生したクラスが[CFrameWnd](../mfc/reference/cframewnd-class.md)です。  
  
 場合は、アプリケーションは、MDI、`CMainFrame`クラスから派生した[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)です。 ここでは`CMainFrame`メニューのツールバー、およびステータス バーが保持されているメインのフレームを実装します。 アプリケーションのウィザードは、の新しいドキュメント フレーム ウィンドウ クラスを派生していません。 代わりの既定の実装を使用して[CMDIChildWnd クラス](../mfc/reference/cmdichildwnd-class.md)です。 MFC フレームワークが各ビューを含む子ウィンドウを作成 (型のこともある`CScrollView`、 `CEditView`、 `CTreeView`、`CListView`など)、アプリケーションに必要なです。 ドキュメント フレーム ウィンドウをカスタマイズする必要がある場合は、新しいドキュメント フレーム ウィンドウ クラスを作成することができます (を参照してください[クラスの追加](../ide/adding-a-class-visual-cpp.md))。  
  
 ツールバーをサポートするために選択すると、クラスが型のメンバー変数もは[CToolBar](../mfc/reference/ctoolbar-class.md)と[CStatusBar](../mfc/reference/cstatusbar-class.md)と`OnCreate`、2 つを初期化するためにメッセージ ハンドラー関数[コントロール バー](../mfc/control-bars.md)です。  
  
 作成されると、これらのフレーム ウィンドウ クラスが動作しますが、機能強化のため、メンバー変数とメンバー関数を追加する必要があります。 ウィンドウ クラスを他の Windows メッセージを処理することもできます。 詳細については、次を参照してください。 [MFC で作成したウィンドウのスタイルを変更する](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)です。  
  
## <a name="see-also"></a>参照  
 [フレーム ウィンドウ クラス](../mfc/frame-window-classes.md)   
 [MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル](../ide/mfc-program-or-control-source-and-header-files.md)

