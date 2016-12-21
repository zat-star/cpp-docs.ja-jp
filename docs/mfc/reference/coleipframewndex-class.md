---
title: "COleIPFrameWndEx クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleIPFrameWndEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleIPFrameWndEx クラス"
ms.assetid: ebff1560-a1eb-4854-af00-95d4a192bd55
caps.latest.revision: 34
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleIPFrameWndEx クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`COleIPFrameWndEx` クラスは、MFC をサポートする OLE コンテナーを実装します。 アプリケーションの埋め込み先フレーム ウィンドウ クラスを、[COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) クラスからではなく、`COleIPFrameWndEx` クラスから派生させる必要があります  
  
## 構文  
  
```  
class COleIPFrameWndEx : public COleIPFrameWnd  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleIPFrameWndEx::AddDockSite](../Topic/COleIPFrameWndEx::AddDockSite.md)||  
|[COleIPFrameWndEx::AddPane](../Topic/COleIPFrameWndEx::AddPane.md)||  
|[COleIPFrameWndEx::AdjustDockingLayout](../Topic/COleIPFrameWndEx::AdjustDockingLayout.md)||  
|[COleIPFrameWndEx::DockPane](../Topic/COleIPFrameWndEx::DockPane.md)||  
|[COleIPFrameWndEx::DockPaneLeftOf](../Topic/COleIPFrameWndEx::DockPaneLeftOf.md)|ウィンドウを別のウィンドウの左側にドッキングします。|  
|[COleIPFrameWndEx::EnableAutoHidePanes](../Topic/COleIPFrameWndEx::EnableAutoHidePanes.md)||  
|[COleIPFrameWndEx::EnableDocking](../Topic/COleIPFrameWndEx::EnableDocking.md)||  
|[COleIPFrameWndEx::EnablePaneMenu](../Topic/COleIPFrameWndEx::EnablePaneMenu.md)||  
|[COleIPFrameWndEx::GetActivePopup](../Topic/COleIPFrameWndEx::GetActivePopup.md)|現在表示されているポップアップ メニューへのポインターを返します。|  
|[COleIPFrameWndEx::GetContainerFrameWindow](../Topic/COleIPFrameWndEx::GetContainerFrameWindow.md)||  
|[COleIPFrameWndEx::GetDefaultResId](../Topic/COleIPFrameWndEx::GetDefaultResId.md)|ウィンドウが読み込まれるときに指定した、フレーム ウィンドウのリソース ID を返します。|  
|[COleIPFrameWndEx::GetDockFrame](../Topic/COleIPFrameWndEx::GetDockFrame.md)||  
|[COleIPFrameWndEx::GetDockingManager](../Topic/COleIPFrameWndEx::GetDockingManager.md)||  
|[COleIPFrameWndEx::GetMainFrame](../Topic/COleIPFrameWndEx::GetMainFrame.md)||  
|[COleIPFrameWndEx::GetMenuBar](../Topic/COleIPFrameWndEx::GetMenuBar.md)|フレーム ウィンドウにアタッチされているメニュー バーのオブジェクトへのポインターを返します。|  
|[COleIPFrameWndEx::GetPane](../Topic/COleIPFrameWndEx::GetPane.md)||  
|[COleIPFrameWndEx::GetTearOffBars](../Topic/COleIPFrameWndEx::GetTearOffBars.md)|ティアオフ状態にあるウィンドウ オブジェクトの一覧を返します。|  
|[COleIPFrameWndEx::GetToolbarButtonToolTipText](../Topic/COleIPFrameWndEx::GetToolbarButtonToolTipText.md)|ボタンのツールヒントが表示される前に、フレームワークによって呼び出されます。|  
|[COleIPFrameWndEx::InsertPane](../Topic/COleIPFrameWndEx::InsertPane.md)||  
|[COleIPFrameWndEx::IsMenuBarAvailable](../Topic/COleIPFrameWndEx::IsMenuBarAvailable.md)|メニュー バーのオブジェクトへのポインターが `NULL` ではないかどうかを判断します。|  
|[COleIPFrameWndEx::IsPointNearDockSite](../Topic/COleIPFrameWndEx::IsPointNearDockSite.md)||  
|[COleIPFrameWndEx::LoadFrame](../Topic/COleIPFrameWndEx::LoadFrame.md)|\(`COleIPFrameWnd::LoadFrame` をオーバーライドします\)。|  
|[COleIPFrameWndEx::OnCloseDockingPane](../Topic/COleIPFrameWndEx::OnCloseDockingPane.md)||  
|[COleIPFrameWndEx::OnCloseMiniFrame](../Topic/COleIPFrameWndEx::OnCloseMiniFrame.md)||  
|[COleIPFrameWndEx::OnClosePopupMenu](../Topic/COleIPFrameWndEx::OnClosePopupMenu.md)|アクティブなポップアップ メニューが WM\_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[COleIPFrameWndEx::OnCmdMsg](../Topic/COleIPFrameWndEx::OnCmdMsg.md)|\(`CFrameWnd::OnCmdMsg` をオーバーライドします\)。|  
|[COleIPFrameWndEx::OnDrawMenuImage](../Topic/COleIPFrameWndEx::OnDrawMenuImage.md)|メニュー項目に関連付けられているイメージが描画されるときに、フレームワークによって呼び出されます。|  
|[COleIPFrameWndEx::OnDrawMenuLogo](../Topic/COleIPFrameWndEx::OnDrawMenuLogo.md)|[CMFCPopupMenu](../Topic/CMFCPopupMenu%20Class.md) オブジェクトが WM\_PAINT メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[COleIPFrameWndEx::OnMenuButtonToolHitTest](../Topic/COleIPFrameWndEx::OnMenuButtonToolHitTest.md)|[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) オブジェクトが WM\_NCHITTEST Microsoft を処理するときに、フレームワークによって呼び出されます。|  
|[COleIPFrameWndEx::OnMoveMiniFrame](../Topic/COleIPFrameWndEx::OnMoveMiniFrame.md)||  
|[COleIPFrameWndEx::OnSetPreviewMode](../Topic/COleIPFrameWndEx::OnSetPreviewMode.md)|印刷プレビュー モードの内外にアプリケーションのメイン フレーム ウィンドウを設定するには、このメンバー関数を呼び出します。 \([CFrameWnd::OnSetPreviewMode](../Topic/CFrameWnd::OnSetPreviewMode.md) をオーバーライドします\)。|  
|[COleIPFrameWndEx::OnShowCustomizePane](../Topic/COleIPFrameWndEx::OnShowCustomizePane.md)||  
|[COleIPFrameWndEx::OnShowPanes](../Topic/COleIPFrameWndEx::OnShowPanes.md)||  
|[COleIPFrameWndEx::OnShowPopupMenu](../Topic/COleIPFrameWndEx::OnShowPopupMenu.md)|ポップアップ メニューがアクティブにされるときにフレームワークによって呼び出されます。|  
|[COleIPFrameWndEx::OnTearOffMenu](../Topic/COleIPFrameWndEx::OnTearOffMenu.md)|ティアオフ バーのあるメニューがアクティブ化されるときにフレームワークによって呼び出されます。|  
|[COleIPFrameWndEx::PaneFromPoint](../Topic/COleIPFrameWndEx::PaneFromPoint.md)||  
|[COleIPFrameWndEx::PreTranslateMessage](../Topic/COleIPFrameWndEx::PreTranslateMessage.md)|\(`COleIPFrameWnd::PreTranslateMessage` をオーバーライドします\)。|  
|[COleIPFrameWndEx::RecalcLayout](../Topic/COleIPFrameWndEx::RecalcLayout.md)|\(`COleIPFrameWnd::RecalcLayout` をオーバーライドします\)。|  
|[COleIPFrameWndEx::RemovePaneFromDockManager](../Topic/COleIPFrameWndEx::RemovePaneFromDockManager.md)||  
|[COleIPFrameWndEx::SetDockState](../Topic/COleIPFrameWndEx::SetDockState.md)|フレーム ウィンドウに属しているウィンドウに、指定のドッキング状態を適用します。|  
|[COleIPFrameWndEx::SetupToolbarMenu](../Topic/COleIPFrameWndEx::SetupToolbarMenu.md)|ダミーの項目を検索して、指定されたユーザー定義の項目で置き換えることで、ツールバーのオブジェクトを変更します。|  
|[COleIPFrameWndEx::ShowPane](../Topic/COleIPFrameWndEx::ShowPane.md)||  
|[COleIPFrameWndEx::WinHelp](../Topic/COleIPFrameWndEx::WinHelp.md)|WinHelp アプリケーションまたはコンテキスト ヘルプを起動するために、フレームワークによって呼び出されます。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleIPFrameWndEx::InitUserToobars](../Topic/COleIPFrameWndEx::InitUserToobars.md)|ユーザー定義のツールバーに割り当てられているコントロールの ID の範囲を初期化するようフレームワークに指示します。|  
  
## 使用例  
 次の例は、`COleIPFrameWndEx` クラスのインスタンスをサブクラス化して、メソッドをオーバーライドする方法を示しています。`OnDestory` メソッド、`RepositionFrame` メソッド、`RecalcLayout` メソッド、および `CalcWindowRect` メソッドをオーバーライドする方法を例に示します。 このコード スニペットは、[Word パッド サンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_WordPad#1](../../mfc/reference/codesnippet/CPP/coleipframewndex-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)  
  
 [COleIPFrameWndEx](../../mfc/reference/coleipframewndex-class.md)  
  
## 必要条件  
 **ヘッダー:** afxoleipframewndex.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)   
 [CMDIFrameWndEx クラス](../Topic/CMDIFrameWndEx%20Class.md)