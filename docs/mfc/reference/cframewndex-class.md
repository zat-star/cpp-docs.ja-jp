---
title: "CFrameWndEx クラス | Microsoft Docs"
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
  - "CFrameWndEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFrameWndEx クラス"
ms.assetid: 5830aca8-4a21-4f31-91f1-dd5477ffcc8d
caps.latest.revision: 39
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFrameWndEx クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のシングル ドキュメント インターフェイス \(SDI: Single Document Interface\) のオーバーラップ フレーム ウィンドウまたはポップアップ フレーム ウィンドウの機能を実装し、ウィンドウを管理するメンバーを提供します。  [CFrameWnd](../../mfc/reference/cframewnd-class.md) クラスを拡張します。  
  
## 構文  
  
```  
class CFrameWndEx : public CFrameWnd  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFrameWndEx::ActiveItemRecalcLayout](../Topic/CFrameWndEx::ActiveItemRecalcLayout.md)|OLE クライアント項目とフレームのクライアント領域のレイアウトを調整します。|  
|`CFrameWndEx::AddDockSite`|このメソッドは使用されません。|  
|[CFrameWndEx::AddPane](../Topic/CFrameWndEx::AddPane.md)|コントロール バーをドッキング マネージャーに登録します。|  
|[CFrameWndEx::AdjustDockingLayout](../Topic/CFrameWndEx::AdjustDockingLayout.md)|フレーム ウィンドウにドッキングされるすべてのペインのレイアウトを再計算します。|  
|[CFrameWndEx::DelayUpdateFrameMenu](../Topic/CFrameWndEx::DelayUpdateFrameMenu.md)|フレーム メニューを設定した後、コマンド処理がアイドルのときに更新します。|  
|[CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md)|指定されたペインをフレーム ウィンドウにドッキングします。|  
|[CFrameWndEx::DockPaneLeftOf](../Topic/CFrameWndEx::DockPaneLeftOf.md)|ペインを別のペインの左側にドッキングします。|  
|[CFrameWndEx::EnableAutoHidePanes](../Topic/CFrameWndEx::EnableAutoHidePanes.md)|ペインがメイン フレーム ウィンドウの指定した辺にドッキングされている場合に、ペインの自動非表示モードを有効にします。|  
|[CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md)|フレーム ウィンドウに属するペインのドッキングを有効にします。|  
|[CFrameWndEx::EnableFullScreenMainMenu](../Topic/CFrameWndEx::EnableFullScreenMainMenu.md)|全画面表示モードでのメイン メニューの表示と非表示を切り替えます。|  
|[CFrameWndEx::EnableFullScreenMode](../Topic/CFrameWndEx::EnableFullScreenMode.md)|フレーム ウィンドウの全画面表示モードを有効にします。|  
|[CFrameWndEx::EnableLoadDockState](../Topic/CFrameWndEx::EnableLoadDockState.md)|ドッキング状態の読み込みを有効または無効にします。|  
|[CFrameWndEx::EnablePaneMenu](../Topic/CFrameWndEx::EnablePaneMenu.md)|ペイン メニューの自動処理を有効または無効にします。|  
|[CFrameWndEx::GetActivePopup](../Topic/CFrameWndEx::GetActivePopup.md)|現在表示されているポップアップ メニューへのポインターを返します。|  
|[CFrameWndEx::GetDefaultResId](../Topic/CFrameWndEx::GetDefaultResId.md)|フレームワークによってフレーム ウィンドウが読み込まれたときにユーザーが指定したリソース ID を返します。|  
|[CFrameWndEx::GetDockingManager](../Topic/CFrameWndEx::GetDockingManager.md)|フレーム ウィンドウの [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md) オブジェクトを取得します。|  
|[CFrameWndEx::GetMenuBar](../Topic/CFrameWndEx::GetMenuBar.md)|フレーム ウィンドウに関連付けられているメニュー バー オブジェクトへのポインターを返します。|  
|[CFrameWndEx::GetPane](../Topic/CFrameWndEx::GetPane.md)|指定した ID を持つペインへのポインターを返します。|  
|[CFrameWndEx::GetRibbonBar](../Topic/CFrameWndEx::GetRibbonBar.md)|フレームのリボン バー コントロールを取得します。|  
|[CFrameWndEx::GetTearOffBars](../Topic/CFrameWndEx::GetTearOffBars.md)|ティアオフ状態になっているペイン オブジェクトのリストを返します。|  
|[CFrameWndEx::GetToolbarButtonToolTipText](../Topic/CFrameWndEx::GetToolbarButtonToolTipText.md)|アプリケーションがツール バー ボタンのツールヒントを表示するときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::InsertPane](../Topic/CFrameWndEx::InsertPane.md)|ペインをドッキング マネージャーに登録します。|  
|[CFrameWndEx::IsFullScreen](../Topic/CFrameWndEx::IsFullScreen.md)|フレーム ウィンドウが全画面表示モードかどうかを判断します。|  
|[CFrameWndEx::IsMenuBarAvailable](../Topic/CFrameWndEx::IsMenuBarAvailable.md)|メニュー バー オブジェクトへのポインターが有効かどうかを判定します。|  
|[CFrameWndEx::IsPointNearDockSite](../Topic/CFrameWndEx::IsPointNearDockSite.md)|点が配置ゾーンにあるかどうかを示します。|  
|[CFrameWndEx::IsPrintPreview](../Topic/CFrameWndEx::IsPrintPreview.md)|フレーム ウィンドウが印刷プレビュー モードかどうかを示します。|  
|[CFrameWndEx::LoadFrame](../Topic/CFrameWndEx::LoadFrame.md)|このメソッドは、フレーム ウィンドウを作成してそのリソースを読み込むために、構築の後に呼び出されます。|  
|[CFrameWndEx::NegotiateBorderSpace](../Topic/CFrameWndEx::NegotiateBorderSpace.md)|OLE クライアントの境界線の調整を実装します。|  
|[CFrameWndEx::OnActivate](../Topic/CFrameWndEx::OnActivate.md)|フレームワークは、ユーザー入力が切り替えられたとき、またはフレームから離れたときに、このメソッドを呼び出します。|  
|[CFrameWndEx::OnActivateApp](../Topic/CFrameWndEx::OnActivateApp.md)|アプリケーションが選択または選択解除されたときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnChangeVisualManager](../Topic/CFrameWndEx::OnChangeVisualManager.md)|フレームを変更するためにビジュアル マネージャーを変更する必要がある場合に、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnClose](../Topic/CFrameWndEx::OnClose.md)|フレームワークは、フレームを閉じるためにこのメソッドを呼び出します。|  
|[CFrameWndEx::OnCloseDockingPane](../Topic/CFrameWndEx::OnCloseDockingPane.md)|ドッキングできるペインの **\[閉じる\]** をユーザーがクリックしたときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnCloseMiniFrame](../Topic/CFrameWndEx::OnCloseMiniFrame.md)|ユーザーが浮動ミニフレーム ウィンドウの**閉じる**ボタンをクリックすると、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnClosePopupMenu](../Topic/CFrameWndEx::OnClosePopupMenu.md)|アクティブなポップアップ メニューが WM\_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnCmdMsg](../Topic/CFrameWndEx::OnCmdMsg.md)|コマンド メッセージをディスパッチします。|  
|[CFrameWndEx::OnContextHelp](../Topic/CFrameWndEx::OnContextHelp.md)|コンテキスト関連ヘルプを表示するために、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnCreate](../Topic/CFrameWndEx::OnCreate.md)|フレームが作成された後に、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnDestroy](../Topic/CFrameWndEx::OnDestroy.md)|フレームが破棄されるときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnDrawMenuImage](../Topic/CFrameWndEx::OnDrawMenuImage.md)|アプリケーションがメニュー項目に関連付けられたイメージを描画するときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnDrawMenuLogo](../Topic/CFrameWndEx::OnDrawMenuLogo.md)|`CMFCPopupMenu` オブジェクトが [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnDWMCompositionChanged](../Topic/CFrameWndEx::OnDWMCompositionChanged.md)|Desktop Window Manager \(DWM\) コンポジションが有効または無効になったときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnExitSizeMove](../Topic/CFrameWndEx::OnExitSizeMove.md)|フレームの移動またはサイズ変更が終了したときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnGetMinMaxInfo](../Topic/CFrameWndEx::OnGetMinMaxInfo.md)|ウィンドウのサイズ制限を設定するためにフレームのサイズが変更されると、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnIdleUpdateCmdUI](../Topic/CFrameWndEx::OnIdleUpdateCmdUI.md)|コマンド処理がアイドルのときにフレーム表示を更新するために、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnLButtonDown](../Topic/CFrameWndEx::OnLButtonDown.md)|ユーザーがマウスの左ボタンを押すと、フレームワークからこのメソッドが呼び出されます。|  
|[CFrameWndEx::OnLButtonUp](../Topic/CFrameWndEx::OnLButtonUp.md)|ユーザーがマウスの左ボタンを放すと、フレームワークによりこのメソッドが呼び出されます。|  
|[CFrameWndEx::OnMenuButtonToolHitTest](../Topic/CFrameWndEx::OnMenuButtonToolHitTest.md)|`CMFCToolBarButton` オブジェクトが `WM_NCHITTEST` メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnMenuChar](../Topic/CFrameWndEx::OnMenuChar.md)|メニューが表示され、ユーザーがコマンドに対応していないキーを押すと、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnMouseMove](../Topic/CFrameWndEx::OnMouseMove.md)|フレームワークは、ポインターを移動するときにこのメソッドを呼び出します。|  
|[CFrameWndEx::OnMoveMiniFrame](../Topic/CFrameWndEx::OnMoveMiniFrame.md)|ペイン ウィンドウが移動されたときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnNcActivate](../Topic/CFrameWndEx::OnNcActivate.md)|フレームの非クライアント領域を再描画して、アクティブ状態の変化を示すときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnNcCalcSize](../Topic/CFrameWndEx::OnNcCalcSize.md)|クライアント領域のサイズと位置を計算する必要があるときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnNcHitTest](../Topic/CFrameWndEx::OnNcHitTest.md)|ポインターを移動すると、またはマウス ボタンを押したり、放したりすると、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnNcMouseMove](../Topic/CFrameWndEx::OnNcMouseMove.md)|ポインターが非クライアント領域に移動すると、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnNcPaint](../Topic/CFrameWndEx::OnNcPaint.md)|非クライアント領域を描画する必要があるときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnPaneCheck](../Topic/CFrameWndEx::OnPaneCheck.md)|ペインの表示を制御するために、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnPostPreviewFrame](../Topic/CFrameWndEx::OnPostPreviewFrame.md)|ユーザーが印刷プレビュー モードを変更したときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnPowerBroadcast](../Topic/CFrameWndEx::OnPowerBroadcast.md)|電源管理イベントが発生したときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnSetMenu](../Topic/CFrameWndEx::OnSetMenu.md)|フレーム ウィンドウ メニューを置き換えるために、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnSetPreviewMode](../Topic/CFrameWndEx::OnSetPreviewMode.md)|フレームの印刷プレビュー モードを設定するために、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnSetText](../Topic/CFrameWndEx::OnSetText.md)|ウィンドウのテキストを設定するために、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnShowCustomizePane](../Topic/CFrameWndEx::OnShowCustomizePane.md)|簡易カスタマイズ ペインが有効になるときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnShowPanes](../Topic/CFrameWndEx::OnShowPanes.md)|ペインを表示または非表示にするために、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnShowPopupMenu](../Topic/CFrameWndEx::OnShowPopupMenu.md)|ポップアップ メニューが有効になるときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnSize](../Topic/CFrameWndEx::OnSize.md)|フレームワークは、フレームのサイズが変更された後にこのメソッドを呼び出します。|  
|[CFrameWndEx::OnSizing](../Topic/CFrameWndEx::OnSizing.md)|フレームワークは、ユーザーがフレームのサイズを変更したときにこのメソッドを呼び出します。|  
|[CFrameWndEx::OnSysColorChange](../Topic/CFrameWndEx::OnSysColorChange.md)|システム カラーが変更されたときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnTearOffMenu](../Topic/CFrameWndEx::OnTearOffMenu.md)|ティアオフ バーのあるメニューが有効になるときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnToolbarContextMenu](../Topic/CFrameWndEx::OnToolbarContextMenu.md)|ツール バーのコンテキスト メニューを構築するために、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnToolbarCreateNew](../Topic/CFrameWndEx::OnToolbarCreateNew.md)|フレームワークは、新しいツール バーを作成するためにこのメソッドを呼び出します。|  
|[CFrameWndEx::OnToolbarDelete](../Topic/CFrameWndEx::OnToolbarDelete.md)|ツール バーが削除されるときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnUpdateFrameMenu](../Topic/CFrameWndEx::OnUpdateFrameMenu.md)|フレーム メニューを設定するために、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnUpdateFrameTitle](../Topic/CFrameWndEx::OnUpdateFrameTitle.md)|フレームワークは、フレーム ウィンドウのタイトル バーを更新するときにこのメソッドを呼び出します。|  
|[CFrameWndEx::OnUpdatePaneMenu](../Topic/CFrameWndEx::OnUpdatePaneMenu.md)|ペイン メニューを更新するために、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnWindowPosChanged](../Topic/CFrameWndEx::OnWindowPosChanged.md)|ウィンドウ管理メソッドが呼び出されたためにフレーム サイズ、位置、または z オーダーが変化すると、フレームワークによって呼び出されます。|  
|[CFrameWndEx::PaneFromPoint](../Topic/CFrameWndEx::PaneFromPoint.md)|指定した点を含むドッキング ペインを返します。|  
|[CFrameWndEx::PreTranslateMessage](../Topic/CFrameWndEx::PreTranslateMessage.md)|特定のウィンドウ メッセージをディスパッチする前に処理します。|  
|[CFrameWndEx::RecalcLayout](../Topic/CFrameWndEx::RecalcLayout.md)|フレームと、その子ウィンドウのレイアウトを調整します。|  
|[CFrameWndEx::RemovePaneFromDockManager](../Topic/CFrameWndEx::RemovePaneFromDockManager.md)|ペインの登録を解除し、ドッキング マネージャーの内部リストから削除します。|  
|[CFrameWndEx::SetDockState](../Topic/CFrameWndEx::SetDockState.md)|ドッキング レイアウトをレジストリに保存されているドッキング状態に戻します。|  
|[CFrameWndEx::SetPrintPreviewFrame](../Topic/CFrameWndEx::SetPrintPreviewFrame.md)|印刷プレビュー フレーム ウィンドウを設定します。|  
|[CFrameWndEx::SetupToolbarMenu](../Topic/CFrameWndEx::SetupToolbarMenu.md)|ユーザー定義コマンドをツール バー メニューに挿入します。|  
|[CFrameWndEx::ShowFullScreen](../Topic/CFrameWndEx::ShowFullScreen.md)|メイン フレームの全画面表示モードと通常モードを切り替えます。|  
|[CFrameWndEx::ShowPane](../Topic/CFrameWndEx::ShowPane.md)|指定されたペインの表示と非表示を切り替えます。|  
|[CFrameWndEx::UpdateCaption](../Topic/CFrameWndEx::UpdateCaption.md)|ウィンドウ フレームのキャプションを更新するために、フレームワークによって呼び出されます。|  
|[CFrameWndEx::WinHelp](../Topic/CFrameWndEx::WinHelp.md)|`WinHelp` アプリケーションまたはコンテキスト関連ヘルプを起動します。|  
  
## 使用例  
 `CFrameWndEx` クラスからクラスを派生させる方法を次のコード例に示します。  この例では、サブクラスのメソッド シグネチャと、`OnShowPopupMenu` メソッドをオーバーライドする方法を示します。  このコード スニペットは [Word のスペースのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_WordPad#3](../../mfc/reference/codesnippet/CPP/cframewndex-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#4](../../mfc/reference/codesnippet/CPP/cframewndex-class_2.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CFrameWndEx](../../mfc/reference/cframewndex-class.md)  
  
## 必要条件  
 **ヘッダー :** afxframewndex.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)