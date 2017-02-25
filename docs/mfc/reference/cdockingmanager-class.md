---
title: "CDockingManager クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockingManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockingManager クラス"
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
caps.latest.revision: 37
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 39
---
# CDockingManager クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メイン フレーム ウィンドウのドッキング レイアウトを制御するコア機能を実装します。  
  
## 構文  
  
```  
class CDockingManager : public CObject  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDockingManager::AddDockSite](../Topic/CDockingManager::AddDockSite.md)|ドッキング ペインを作成し、それをコントロール バーのリストに追加します。|  
|[CDockingManager::AddHiddenMDITabbedBar](../Topic/CDockingManager::AddHiddenMDITabbedBar.md)|バー ペインへのハンドルを非表示の MDI タブ付きバー ペインのリストに追加します。|  
|[CDockingManager::AddMiniFrame](../Topic/CDockingManager::AddMiniFrame.md)|ミニフレームの一覧にフレームを追加します。|  
|[CDockingManager::AddPane](../Topic/CDockingManager::AddPane.md)|ペインをドッキング マネージャーに登録します。|  
|[CDockingManager::AdjustDockingLayout](../Topic/CDockingManager::AdjustDockingLayout.md)|フレーム ウィンドウ内のすべてのペインのレイアウトを再計算して調整します。|  
|[CDockingManager::AdjustPaneFrames](../Topic/CDockingManager::AdjustPaneFrames.md)|すべてのペインおよび `CPaneFrameWnd` ウィンドウに `WM_NCCALCSIZE` メッセージを送信します。|  
|[CDockingManager::AdjustRectToClientArea](../Topic/CDockingManager::AdjustRectToClientArea.md)|四角形の配置を調整します。|  
|[CDockingManager::AlignAutoHidePane](../Topic/CDockingManager::AlignAutoHidePane.md)|自動非表示モードのドッキング ペインのサイズを、ドッキング サイトで囲まれたフレームのクライアント領域全体の幅または高さになるように変更します。|  
|[CDockingManager::AutoHidePane](../Topic/CDockingManager::AutoHidePane.md)|自動非表示ツール バーを作成します。|  
|[CDockingManager::BringBarsToTop](../Topic/CDockingManager::BringBarsToTop.md)|指定された配置を持つドッキング バーを一番上に置きます。|  
|[CDockingManager::BuildPanesMenu](../Topic/CDockingManager::BuildPanesMenu.md)|ドッキング ペインおよびツール バーの名前をメニューに追加します。|  
|[CDockingManager::CalcExpectedDockedRect](../Topic/CDockingManager::CalcExpectedDockedRect.md)|ドッキング ウィンドウの予想される四角形を計算します|  
|[CDockingManager::Create](../Topic/CDockingManager::Create.md)|ドッキング マネージャーを作成します。|  
|[CDockingManager::DeterminePaneAndStatus](../Topic/CDockingManager::DeterminePaneAndStatus.md)|指定した点とドッキング ステータスを含むペインを判断します。|  
|[CDockingManager::DisableRestoreDockState](../Topic/CDockingManager::DisableRestoreDockState.md)|レジストリからのドッキング レイアウトの読み込みを有効または無効にします。|  
|[CDockingManager::DockPane](../Topic/CDockingManager::DockPane.md)|ペインを別のペインまたはフレーム ウィンドウにドッキングします。|  
|[CDockingManager::DockPaneLeftOf](../Topic/CDockingManager::DockPaneLeftOf.md)|ペインを別のペインの左側にドッキングします。|  
|[CDockingManager::EnableAutoHidePanes](../Topic/CDockingManager::EnableAutoHidePanes.md)|ペインのメイン フレームへのドッキングを有効にし、ドッキング ペインを作成し、それをコントロール バーのリストに追加します。|  
|[CDockingManager::EnableDocking](../Topic/CDockingManager::EnableDocking.md)|ドッキング ペインを作成し、メイン フレームへのペインのドッキングを有効にします。|  
|[CDockingManager::EnableDockSiteMenu](../Topic/CDockingManager::EnableDockSiteMenu.md)|すべてのドッキング ペインのキャプションにポップアップ メニューを開く、追加のボタンを表示します。|  
|[CDockingManager::EnablePaneContextMenu](../Topic/CDockingManager::EnablePaneContextMenu.md)|ユーザーが右マウス ボタンをクリックし、ライブラリが WM\_CONTEXTMENU メッセージを処理している場合に、ライブラリに対して、アプリケーションのツール バーとドッキング ペインがリストされる特別なコンテキスト メニューを表示するよう指示します。|  
|[CDockingManager::FindDockSite](../Topic/CDockingManager::FindDockSite.md)|指定された位置にあり、指定された配置を持つバー ペインを取得します。|  
|[CDockingManager::FindDockSiteByPane](../Topic/CDockingManager::FindDockSiteByPane.md)|対象のバー ペインの ID を持つバー ペインを返します。|  
|[CDockingManager::FindPaneByID](../Topic/CDockingManager::FindPaneByID.md)|指定したコントロール ID でペインを検索します。|  
|[CDockingManager::FixupVirtualRects](../Topic/CDockingManager::FixupVirtualRects.md)|現在のすべてのツール バーの位置を仮想四角形にコミットします。|  
|[CDockingManager::FrameFromPoint](../Topic/CDockingManager::FrameFromPoint.md)|指定した点を含むフレームを返します。|  
|[CDockingManager::GetClientAreaBounds](../Topic/CDockingManager::GetClientAreaBounds.md)|クライアント領域の境界を含む四角形を取得します。|  
|[CDockingManager::GetDockingMode](../Topic/CDockingManager::GetDockingMode.md)|現在のドッキング モードを返します。|  
|[CDockingManager::GetDockSiteFrameWnd](../Topic/CDockingManager::GetDockSiteFrameWnd.md)|親ウィンドウ フレームへのポインターを取得します。|  
|[CDockingManager::GetEnabledAutoHideAlignment](../Topic/CDockingManager::GetEnabledAutoHideAlignment.md)|ペインの有効な配置を返します。|  
|[CDockingManager::GetMiniFrames](../Topic/CDockingManager::GetMiniFrames.md)|ミニフレームの一覧を取得します。|  
|[CDockingManager::GetOuterEdgeBounds](../Topic/CDockingManager::GetOuterEdgeBounds.md)|フレームの外縁を含む四角形を取得します。|  
|[CDockingManager::GetPaneList](../Topic/CDockingManager::GetPaneList.md)|ドッキング マネージャーに属するペインの一覧を返します。  これには、すべての浮動ペインが含まれます。|  
|[CDockingManager::GetSmartDockingManager](../Topic/CDockingManager::GetSmartDockingManager.md)|スマート ドッキング マネージャーへのポインターを取得します。|  
|[CDockingManager::GetSmartDockingManagerPermanent](../Topic/CDockingManager::GetSmartDockingManagerPermanent.md)|スマート ドッキング マネージャーへのポインターを取得します。|  
|[CDockingManager::GetSmartDockingParams](../Topic/CDockingManager::GetSmartDockingParams.md)|ドッキング マネージャーのスマート ドッキングのパラメーターを返します。|  
|[CDockingManager::GetSmartDockingTheme](../Topic/CDockingManager::GetSmartDockingTheme.md)|スマート ドッキング マーカーの表示に使用されるテーマを返す静的メソッド。|  
|[CDockingManager::HideAutoHidePanes](../Topic/CDockingManager::HideAutoHidePanes.md)|自動的に隠すモードのペインを非表示にします。|  
|[CDockingManager::InsertDockSite](../Topic/CDockingManager::InsertDockSite.md)|ドッキング ペインを作成し、それをコントロール バーのリストに挿入します。|  
|[CDockingManager::InsertPane](../Topic/CDockingManager::InsertPane.md)|コントロール ペインをコントロール バーのリストに挿入します。|  
|[CDockingManager::IsDockSiteMenu](../Topic/CDockingManager::IsDockSiteMenu.md)|すべてのペインのキャプションにポップアップ メニューが表示されるかどうかを指定します。|  
|[CDockingManager::IsInAdjustLayout](../Topic/CDockingManager::IsInAdjustLayout.md)|すべてのペインのレイアウトが調整されているかどうかを確認します。|  
|[CDockingManager::IsOLEContainerMode](../Topic/CDockingManager::IsOLEContainerMode.md)|ドッキング マネージャーが OLE コンテナー モードであるかどうかを示します。|  
|[CDockingManager::IsPointNearDockSite](../Topic/CDockingManager::IsPointNearDockSite.md)|指定された点がドッキング サイトの近くにあるかどうかを判定します。|  
|[CDockingManager::IsPrintPreviewValid](../Topic/CDockingManager::IsPrintPreviewValid.md)|印刷プレビュー モードが設定されているかどうかを判定します。|  
|[CDockingManager::LoadState](../Topic/CDockingManager::LoadState.md)|レジストリからドッキング マネージャーの状態を読み込みます。|  
|[CDockingManager::LockUpdate](../Topic/CDockingManager::LockUpdate.md)|指定されたウィンドウをロックします。|  
|[CDockingManager::OnActivateFrame](../Topic/CDockingManager::OnActivateFrame.md)|フレーム ウィンドウがアクティブまたは非アクティブになるときに、フレームワークによって呼び出されます。|  
|[CDockingManager::OnClosePopupMenu](../Topic/CDockingManager::OnClosePopupMenu.md)|アクティブなポップアップ メニューが WM\_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CDockingManager::OnMoveMiniFrame](../Topic/CDockingManager::OnMoveMiniFrame.md)|ミニフレーム ウィンドウを移動するために、フレームワークによって呼び出されます。|  
|[CDockingManager::OnPaneContextMenu](../Topic/CDockingManager::OnPaneContextMenu.md)|ペインのリストを持つメニューをビルドするときに、フレームワークによって呼び出されます。|  
|[CDockingManager::PaneFromPoint](../Topic/CDockingManager::PaneFromPoint.md)|指定した点を含むペインを返します。|  
|[CDockingManager::ProcessPaneContextMenuCommand](../Topic/CDockingManager::ProcessPaneContextMenuCommand.md)|指定されたコマンドのチェック ボックスをオンまたはオフにし、表示されるペインのレイアウトを再計算するために、フレームワークによって呼び出されます。|  
|[CDockingManager::RecalcLayout](../Topic/CDockingManager::RecalcLayout.md)|コントロールのリストに提示されるコントロールの内部レイアウトを再計算します。|  
|[CDockingManager::ReleaseEmptyPaneContainers](../Topic/CDockingManager::ReleaseEmptyPaneContainers.md)|空のペイン コンテナーを解放します。|  
|[CDockingManager::RemoveHiddenMDITabbedBar](../Topic/CDockingManager::RemoveHiddenMDITabbedBar.md)|指定された非表示のバー ペインを削除します。|  
|[CDockingManager::RemoveMiniFrame](../Topic/CDockingManager::RemoveMiniFrame.md)|指定したフレームをミニフレームの一覧から削除します。|  
|[CDockingManager::RemovePaneFromDockManager](../Topic/CDockingManager::RemovePaneFromDockManager.md)|ペインの登録を解除し、ドッキング マネージャーの一覧から削除します。|  
|[CDockingManager::ReplacePane](../Topic/CDockingManager::ReplacePane.md)|ペインを別のペインに置き換えます。|  
|[CDockingManager::ResortMiniFramesForZOrder](../Topic/CDockingManager::ResortMiniFramesForZOrder.md)|ミニフレームの一覧でフレームを再度並べ替えます。|  
|[CDockingManager::SaveState](../Topic/CDockingManager::SaveState.md)|レジストリにドッキング マネージャーの状態を保存します。|  
|[CDockingManager::SendMessageToMiniFrames](../Topic/CDockingManager::SendMessageToMiniFrames.md)|指定されたメッセージをすべてのミニフレームに送信します。|  
|[CDockingManager::Serialize](../Topic/CDockingManager::Serialize.md)|ドッキング マネージャーをアーカイブに書き込みます。  \([CObject::Serialize](../Topic/CObject::Serialize.md) をオーバーライドします。\)|  
|[CDockingManager::SetAutohideZOrder](../Topic/CDockingManager::SetAutohideZOrder.md)|コントロール バーと指定されたペインのサイズ、幅、および高さを設定します。|  
|[CDockingManager::SetDockingMode](../Topic/CDockingManager::SetDockingMode.md)|ドッキング モードを設定します。|  
|[CDockingManager::SetDockState](../Topic/CDockingManager::SetDockState.md)|コントロール バー、ミニ フレーム、および自動非表示バーのドッキング状態を設定します。|  
|[CDockingManager::SetPrintPreviewMode](../Topic/CDockingManager::SetPrintPreviewMode.md)|印刷プレビューに表示されるバーの印刷プレビュー モードを設定します。|  
|[CDockingManager::SetSmartDockingParams](../Topic/CDockingManager::SetSmartDockingParams.md)|スマート ドッキングの動作を定義するパラメーターを設定します。|  
|[CDockingManager::ShowDelayShowMiniFrames](../Topic/CDockingManager::ShowDelayShowMiniFrames.md)|ミニフレーム ウィンドウの表示と非表示を切り替えます。|  
|[CDockingManager::ShowPanes](../Topic/CDockingManager::ShowPanes.md)|コントロールと自動非表示のバーのペインの表示と非表示を切り替えます。|  
|[CDockingManager::StartSDocking](../Topic/CDockingManager::StartSDocking.md)|スマート ドッキング マネージャーの配置に従って指定されたウィンドウのスマート ドッキングを開始します。|  
|[CDockingManager::StopSDocking](../Topic/CDockingManager::StopSDocking.md)|スマート ドッキングを停止します。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CDockingManager::m\_bHideDockingBarsInContainerMode](../Topic/CDockingManager::m_bHideDockingBarsInContainerMode.md)|OLE コンテナー モードの場合にドッキング マネージャーがペインを非表示にするかどうかを指定します。|  
|[CDockingManager::m\_dockModeGlobal](../Topic/CDockingManager::m_dockModeGlobal.md)|グローバル ドッキング モードを指定します。|  
|[CDockingManager::m\_nDockSensitivity](../Topic/CDockingManager::m_nDockSensitivity.md)|ドッキング感度を指定します。|  
|[CDockingManager::m\_nTimeOutBeforeDockingBarDock](../Topic/CDockingManager::m_nTimeOutBeforeDockingBarDock.md)|即時ドッキング モードでドッキング ペインがドッキングするまでの待機時間をミリ秒単位で指定します。|  
|[CDockingManager::m\_nTimeOutBeforeToolBarDock](../Topic/CDockingManager::m_nTimeOutBeforeToolBarDock.md)|ツール バーがメイン フレーム ウィンドウにドッキングされるまでの時間をミリ秒単位で指定します。|  
  
## 解説  
 メイン フレーム ウィンドウは、このクラスを自動的に作成および初期化します。  
  
 ドッキング マネージャー オブジェクトは、ドッキング レイアウト内にあるすべてのペインのリスト、およびメイン フレーム ウィンドウに属するすべての [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) ウィンドウのリストも保持します。  
  
 `CDockingManager` クラスは、ペインまたは `CPaneFrameWnd` ウィンドウを検索するために使用できるサービスを実装します。  これらのサービスはメイン フレーム ウィンドウのオブジェクトにラップされるので、通常は直接呼び出しません。  詳細については、「[CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)」を参照してください。  
  
## カスタマイズのヒント  
 次のヒントは `CDockingManager` オブジェクトに適用されます。  
  
-   [CDockingManager Class](../../mfc/reference/cdockingmanager-class.md)は、次のドッキング モードをサポートします。  
  
    -   `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    -   `AFX_DOCK_TYPE::DT_STANDARD`  
  
    -   `AFX_DOCK_TYPE::DT_SMART`  
  
     これらのドッキング モードは [CDockingManager::m\_dockModeGlobal](../Topic/CDockingManager::m_dockModeGlobal.md) により定義され、[CDockingManager::SetDockingMode](../Topic/CDockingManager::SetDockingMode.md) を呼び出すことにより設定されます。  
  
-   非フローティングのサイズ変更できないペインを作成するには、[CDockingManager::AddPane](../Topic/CDockingManager::AddPane.md) メソッドを呼び出します。  このメソッドは、ペインのレイアウトを制御するドッキング マネージャーにペインを登録します。  
  
## 使用例  
 `CDockingManager` クラスのさまざまなメソッドを使用して `CDockingManager` オブジェクトを構成する方法を次の例に示します。  例では、すべてのドッキング ペインのキャプションでポップアップ メニューを開く追加のボタンを表示する方法、およびオブジェクトのドッキング モードを設定する方法を示しています。  このコード スニペットは [Visual Studio のデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/reference/codesnippet/CPP/cdockingmanager-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## 必要条件  
 **ヘッダー :** afxDockingManager.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CObject クラス](../Topic/CObject%20Class.md)   
 [CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)   
 [CDockablePane クラス](../Topic/CDockablePane%20Class.md)   
 [CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)