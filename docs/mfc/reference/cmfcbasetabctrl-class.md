---
title: "CMFCBaseTabCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCBaseTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCBaseTabCtrl クラス"
ms.assetid: 7270c55f-6f6e-4dd2-b0d2-291afeac3882
caps.latest.revision: 41
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCBaseTabCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

タブ付きウィンドウの基本的な機能を実装します。  
  
## 構文  
  
```  
class CMFCBaseTabCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCBaseTabCtrl::AddIcon](../Topic/CMFCBaseTabCtrl::AddIcon.md)||  
|[CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md)|タブ付きウィンドウに新しいタブを追加します。|  
|[CMFCBaseTabCtrl::ApplyRestoredTabInfo](../Topic/CMFCBaseTabCtrl::ApplyRestoredTabInfo.md)||  
|[CMFCBaseTabCtrl::AutoDestroyWindow](../Topic/CMFCBaseTabCtrl::AutoDestroyWindow.md)||  
|[CMFCBaseTabCtrl::CalcRectEdit](../Topic/CMFCBaseTabCtrl::CalcRectEdit.md)||  
|[CMFCBaseTabCtrl::CleanUp](../Topic/CMFCBaseTabCtrl::CleanUp.md)||  
|[CMFCBaseTabCtrl::ClearImageList](../Topic/CMFCBaseTabCtrl::ClearImageList.md)||  
|[CMFCBaseTabCtrl::DetachTab](../Topic/CMFCBaseTabCtrl::DetachTab.md)|タブ付きウィンドウからタブをデタッチします。|  
|[CMFCBaseTabCtrl::EnableActivateLastActive](../Topic/CMFCBaseTabCtrl::EnableActivateLastActive.md)||  
|[CMFCBaseTabCtrl::EnableAutoColor](../Topic/CMFCBaseTabCtrl::EnableAutoColor.md)|タブの色の自動設定を有効または無効にします。|  
|[CMFCBaseTabCtrl::EnableCustomToolTips](../Topic/CMFCBaseTabCtrl::EnableCustomToolTips.md)|タブのカスタム ツールヒントを有効または無効にします。|  
|[CMFCBaseTabCtrl::EnableInPlaceEdit](../Topic/CMFCBaseTabCtrl::EnableInPlaceEdit.md)|タブ ラベルの直接編集を有効または無効にします。|  
|[CMFCBaseTabCtrl::EnableTabDetach](../Topic/CMFCBaseTabCtrl::EnableTabDetach.md)|切り離し可能なタブを有効にします。|  
|[CMFCBaseTabCtrl::EnableTabSwap](../Topic/CMFCBaseTabCtrl::EnableTabSwap.md)|ユーザーがマウスを使用してタブ オーダーを変更できる機能を有効または無効にします。|  
|[CMFCBaseTabCtrl::EnsureVisible](../Topic/CMFCBaseTabCtrl::EnsureVisible.md)|指定したタブが表示されるまでタブをスクロールします。 指定したタブが既に表示されている場合、このメソッドの効果はありません。|  
|[CMFCBaseTabCtrl::EnterDragMode](../Topic/CMFCBaseTabCtrl::EnterDragMode.md)||  
|[CMFCBaseTabCtrl::FindTargetWnd](../Topic/CMFCBaseTabCtrl::FindTargetWnd.md)|指定したポイントを含むウィンドウを返します。|  
|[CMFCBaseTabCtrl::FireChangeActiveTab](../Topic/CMFCBaseTabCtrl::FireChangeActiveTab.md)||  
|[CMFCBaseTabCtrl::FireChangingActiveTab](../Topic/CMFCBaseTabCtrl::FireChangingActiveTab.md)||  
|[CMFCBaseTabCtrl::GetActiveTab](../Topic/CMFCBaseTabCtrl::GetActiveTab.md)|アクティブなタブのインデックスを返します。|  
|[CMFCBaseTabCtrl::GetActiveTabColor](../Topic/CMFCBaseTabCtrl::GetActiveTabColor.md)|アクティブなタブの背景色を返します。|  
|[CMFCBaseTabCtrl::GetActiveTabTextColor](../Topic/CMFCBaseTabCtrl::GetActiveTabTextColor.md)|アクティブなタブのテキストの色を返します。|  
|[CMFCBaseTabCtrl::GetActiveWnd](../Topic/CMFCBaseTabCtrl::GetActiveWnd.md)|タブ コントロールのアクティブ ページのポインターを返します。|  
|[CMFCBaseTabCtrl::GetAutoColors](../Topic/CMFCBaseTabCtrl::GetAutoColors.md)|色の自動設定に使用される色の配列への参照を返します。|  
|[CMFCBaseTabCtrl::GetFirstVisibleTab](../Topic/CMFCBaseTabCtrl::GetFirstVisibleTab.md)|最初に表示されているタブへのポインターを返します。|  
|[CMFCBaseTabCtrl::GetFirstVisibleTabNum](../Topic/CMFCBaseTabCtrl::GetFirstVisibleTabNum.md)||  
|[CMFCBaseTabCtrl::GetHighlightedTab](../Topic/CMFCBaseTabCtrl::GetHighlightedTab.md)|現在強調表示されているタブのインデックスを返します。|  
|[CMFCBaseTabCtrl::GetImageList](../Topic/CMFCBaseTabCtrl::GetImageList.md)||  
|[CMFCBaseTabCtrl::GetImageSize](../Topic/CMFCBaseTabCtrl::GetImageSize.md)||  
|[CMFCBaseTabCtrl::GetLastVisibleTab](../Topic/CMFCBaseTabCtrl::GetLastVisibleTab.md)||  
|[CMFCBaseTabCtrl::GetLocation](../Topic/CMFCBaseTabCtrl::GetLocation.md)|タブ コントロールに合わせてタブ領域が配置されている位置を示す LOCATION データ型の変数を返します。 たとえば、一番上または一番下です。|  
|[CMFCBaseTabCtrl::GetMaxWindowSize](../Topic/CMFCBaseTabCtrl::GetMaxWindowSize.md)||  
|[CMFCBaseTabCtrl::GetTabArea](../Topic/CMFCBaseTabCtrl::GetTabArea.md)|タブ付きウィンドウ内のタブ領域のサイズと位置を返します。 タブ領域の位置は座標を使用して定義されます。|  
|[CMFCBaseTabCtrl::GetTabBkColor](../Topic/CMFCBaseTabCtrl::GetTabBkColor.md)|指定したタブの背景色を返します。|  
|[CMFCBaseTabCtrl::GetTabBorderSize](../Topic/CMFCBaseTabCtrl::GetTabBorderSize.md)|タブ コントロールにおけるタブ境界線のサイズを返します。|  
|[CMFCBaseTabCtrl::GetTabByID](../Topic/CMFCBaseTabCtrl::GetTabByID.md)|指定した ID で識別されるタブのインデックスを返します。|  
|[CMFCBaseTabCtrl::GetTabCloseButton](../Topic/CMFCBaseTabCtrl::GetTabCloseButton.md)||  
|[CMFCBaseTabCtrl::GetTabFromHwnd](../Topic/CMFCBaseTabCtrl::GetTabFromHwnd.md)|指定した HWND オブジェクトを含むタブのインデックスを返します。|  
|[CMFCBaseTabCtrl::GetTabFromPoint](../Topic/CMFCBaseTabCtrl::GetTabFromPoint.md)|指定したポイントを含むタブを返します。|  
|[CMFCBaseTabCtrl::GetTabFullWidth](../Topic/CMFCBaseTabCtrl::GetTabFullWidth.md)||  
|[CMFCBaseTabCtrl::GetTabHicon](../Topic/CMFCBaseTabCtrl::GetTabHicon.md)|指定したタブに関連付けられたアイコンを返します。|  
|[CMFCBaseTabCtrl::GetTabID](../Topic/CMFCBaseTabCtrl::GetTabID.md)|タブのインデックスを使用して、タブの ID を返します。|  
|[CMFCBaseTabCtrl::GetTabIcon](../Topic/CMFCBaseTabCtrl::GetTabIcon.md)|指定したタブのアイコン ID を返します。|  
|[CMFCBaseTabCtrl::GetTabLabel](../Topic/CMFCBaseTabCtrl::GetTabLabel.md)|指定したタブのテキストを返します。|  
|[CMFCBaseTabCtrl::GetTabRect](../Topic/CMFCBaseTabCtrl::GetTabRect.md)|指定したタブのサイズと位置を取得します。|  
|[CMFCBaseTabCtrl::GetTabsHeight](../Topic/CMFCBaseTabCtrl::GetTabsHeight.md)||  
|[CMFCBaseTabCtrl::GetTabsRect](../Topic/CMFCBaseTabCtrl::GetTabsRect.md)||  
|[CMFCBaseTabCtrl::GetTabTextColor](../Topic/CMFCBaseTabCtrl::GetTabTextColor.md)|指定したタブのテキストの色を返します。|  
|[CMFCBaseTabCtrl::GetTabWnd](../Topic/CMFCBaseTabCtrl::GetTabWnd.md)|指定したタブ ページ上に存在するウィンドウへのポインターを返します。|  
|[CMFCBaseTabCtrl::GetTabWndNoWrapper](../Topic/CMFCBaseTabCtrl::GetTabWndNoWrapper.md)|コントロールにラッパーがある場合でも、指定したタブ ページ上に存在するコントロールへの直接のポインターを返します。|  
|[CMFCBaseTabCtrl::GetTabsNum](../Topic/CMFCBaseTabCtrl::GetTabsNum.md)|タブ コントロールに含まれているタブの数を返します。|  
|[CMFCBaseTabCtrl::GetToolTipCtrl](../Topic/CMFCBaseTabCtrl::GetToolTipCtrl.md)|`CMFCBaseTabCtrl` オブジェクトに関連付けられているツールヒント コントロールへの参照を返します。|  
|[CMFCBaseTabCtrl::GetVisibleTabsNum](../Topic/CMFCBaseTabCtrl::GetVisibleTabsNum.md)|表示されるタブの数を返します。|  
|[CMFCBaseTabCtrl::HasImage](../Topic/CMFCBaseTabCtrl::HasImage.md)||  
|[CMFCBaseTabCtrl::HideSingleTab](../Topic/CMFCBaseTabCtrl::HideSingleTab.md)|ウィンドウ タブを非表示にするオプションを設定します。ただし、タブ付きウィンドウに表示されるタブが 1 つのみの場合に限ります。|  
|[CMFCBaseTabCtrl::InsertTab](../Topic/CMFCBaseTabCtrl::InsertTab.md)|新しいタブを挿入します。|  
|[CMFCBaseTabCtrl::InvalidateTab](../Topic/CMFCBaseTabCtrl::InvalidateTab.md)||  
|[CMFCBaseTabCtrl::IsActiveTabCloseButton](../Topic/CMFCBaseTabCtrl::IsActiveTabCloseButton.md)||  
|[CMFCBaseTabCtrl::IsAutoColor](../Topic/CMFCBaseTabCtrl::IsAutoColor.md)|タブ付きウィンドウが自動設定色のモードであるかどうかを示す値を返します。|  
|[CMFCBaseTabCtrl::IsAutoDestroyWindow](../Topic/CMFCBaseTabCtrl::IsAutoDestroyWindow.md)||  
|[CMFCBaseTabCtrl::IsColored](../Topic/CMFCBaseTabCtrl::IsColored.md)||  
|[CMFCBaseTabCtrl::IsDialogControl](../Topic/CMFCBaseTabCtrl::IsDialogControl.md)||  
|[CMFCBaseTabCtrl::IsDrawNoPrefix](../Topic/CMFCBaseTabCtrl::IsDrawNoPrefix.md)||  
|[CMFCBaseTabCtrl::IsFlatFrame](../Topic/CMFCBaseTabCtrl::IsFlatFrame.md)|タブ領域のフレームがフラットであるか 3D であるかを示す値を返します。|  
|[CMFCBaseTabCtrl::IsFlatTab](../Topic/CMFCBaseTabCtrl::IsFlatTab.md)||  
|[CMFCBaseTabCtrl::IsHideSingleTab](../Topic/CMFCBaseTabCtrl::IsHideSingleTab.md)|タブ コントロールがタブを非表示にするように構成されているかどうかを示す値を返します。ただし、タブ付きウィンドウに表示されるタブが 1 つのみの場合に限ります。|  
|[CMFCBaseTabCtrl::IsIconAdded](../Topic/CMFCBaseTabCtrl::IsIconAdded.md)||  
|[CMFCBaseTabCtrl::IsInPlaceEdit](../Topic/CMFCBaseTabCtrl::IsInPlaceEdit.md)|ユーザーがタブ上のラベルを変更できるかどうかを示します。|  
|[CMFCBaseTabCtrl::IsLeftRightRounded](../Topic/CMFCBaseTabCtrl::IsLeftRightRounded.md)||  
|[CMFCBaseTabCtrl::IsMDITab](../Topic/CMFCBaseTabCtrl::IsMDITab.md)||  
|[CMFCBaseTabCtrl::IsOneNoteStyle](../Topic/CMFCBaseTabCtrl::IsOneNoteStyle.md)|タブ付きウィンドウに Microsoft OneNote スタイルでタブが表示されるかどうかを示します。|  
|[CMFCBaseTabCtrl::IsPtInTabArea](../Topic/CMFCBaseTabCtrl::IsPtInTabArea.md)|指定したポイントがタブ領域に存在するかどうかを確認します。|  
|[CMFCBaseTabCtrl::IsTabCloseButtonHighlighted](../Topic/CMFCBaseTabCtrl::IsTabCloseButtonHighlighted.md)||  
|[CMFCBaseTabCtrl::IsTabCloseButtonPressed](../Topic/CMFCBaseTabCtrl::IsTabCloseButtonPressed.md)||  
|[CMFCBaseTabCtrl::IsTabDetachable](../Topic/CMFCBaseTabCtrl::IsTabDetachable.md)|タブが切り離し可能であるかどうかを示します。|  
|[CMFCBaseTabCtrl::IsTabIconOnly](../Topic/CMFCBaseTabCtrl::IsTabIconOnly.md)|タブにラベルではなくアイコンが表示されるかどうかを示します。|  
|[CMFCBaseTabCtrl::IsTabSwapEnabled](../Topic/CMFCBaseTabCtrl::IsTabSwapEnabled.md)|タブをドラッグして、ユーザーがタブをドラッグすることでタブ位置を変更できるかどうかを示します。|  
|[CMFCBaseTabCtrl::IsTabVisible](../Topic/CMFCBaseTabCtrl::IsTabVisible.md)|指定したタブが表示されるかどうかを示します。|  
|[CMFCBaseTabCtrl::IsVS2005Style](../Topic/CMFCBaseTabCtrl::IsVS2005Style.md)||  
|[CMFCBaseTabCtrl::MoveTab](../Topic/CMFCBaseTabCtrl::MoveTab.md)||  
|[CMFCBaseTabCtrl::OnChangeTabs](../Topic/CMFCBaseTabCtrl::OnChangeTabs.md)|タブの数が変化したときにフレームワークによって呼び出されます。|  
|[CMFCBaseTabCtrl::OnDragEnter](../Topic/CMFCBaseTabCtrl::OnDragEnter.md)||  
|[CMFCBaseTabCtrl::OnDragLeave](../Topic/CMFCBaseTabCtrl::OnDragLeave.md)||  
|[CMFCBaseTabCtrl::OnDragOver](../Topic/CMFCBaseTabCtrl::OnDragOver.md)||  
|[CMFCBaseTabCtrl::OnDrop](../Topic/CMFCBaseTabCtrl::OnDrop.md)||  
|[CMFCBaseTabCtrl::OnRenameTab](../Topic/CMFCBaseTabCtrl::OnRenameTab.md)||  
|[CMFCBaseTabCtrl::PreTranslateMessage](../Topic/CMFCBaseTabCtrl::PreTranslateMessage.md)|[TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) および [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) の各 Windows 関数にディスパッチされる前に、ウィンドウ メッセージを変換するためにクラス [CWinApp](../../mfc/reference/cwinapp-class.md) で使用されます。 \([CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md) をオーバーライドします\)。|  
|[CMFCBaseTabCtrl::RecalcLayout](../Topic/CMFCBaseTabCtrl::RecalcLayout.md)|タブ付きウィンドウの内部レイアウトを再計算します。|  
|[CMFCBaseTabCtrl::RemoveAllTabs](../Topic/CMFCBaseTabCtrl::RemoveAllTabs.md)|タブ付きウィンドウからタブをすべて削除します。|  
|[CMFCBaseTabCtrl::RemoveTab](../Topic/CMFCBaseTabCtrl::RemoveTab.md)|タブ付きウィンドウからタブを 1 つ削除します。|  
|[CMFCBaseTabCtrl::RenameTab](../Topic/CMFCBaseTabCtrl::RenameTab.md)||  
|[CMFCBaseTabCtrl::ResetImageList](../Topic/CMFCBaseTabCtrl::ResetImageList.md)|タブ付きウィンドウにアタッチされているイメージ リストをリセットします。|  
|[CMFCBaseTabCtrl::Serialize](../Topic/CMFCBaseTabCtrl::Serialize.md)|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。 \([CObject::Serialize](../Topic/CObject::Serialize.md) をオーバーライドします\)。|  
|[CMFCBaseTabCtrl::SetActiveTab](../Topic/CMFCBaseTabCtrl::SetActiveTab.md)|タブをアクティブにします。|  
|[CMFCBaseTabCtrl::SetActiveTabColor](../Topic/CMFCBaseTabCtrl::SetActiveTabColor.md)|現在アクティブなタブの背景色を設定します。|  
|[CMFCBaseTabCtrl::SetActiveTabTextColor](../Topic/CMFCBaseTabCtrl::SetActiveTabTextColor.md)|アクティブなタブのテキストの色を設定します。|  
|[CMFCBaseTabCtrl::SetAutoColors](../Topic/CMFCBaseTabCtrl::SetAutoColors.md)|自動設定色のモードで適用されるタブ コントロールの色を設定します。|  
|[CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../Topic/CMFCBaseTabCtrl::SetDockingBarWrapperRTC.md)|[CDockablePane クラス](../Topic/CDockablePane%20Class.md) から派生しているのではない任意のオブジェクトに使用するラッパー クラスを設定します。|  
|[CMFCBaseTabCtrl::SetDrawNoPrefix](../Topic/CMFCBaseTabCtrl::SetDrawNoPrefix.md)|タブ ラベルの描画時に、接頭文字の処理を有効または無効にします。|  
|[CMFCBaseTabCtrl::SetImageList](../Topic/CMFCBaseTabCtrl::SetImageList.md)|アイコン イメージ リストを設定します。|  
|[CMFCBaseTabCtrl::SetLocation](../Topic/CMFCBaseTabCtrl::SetLocation.md)||  
|[CMFCBaseTabCtrl::SetTabBkColor](../Topic/CMFCBaseTabCtrl::SetTabBkColor.md)|指定したタブの背景色を設定します。|  
|[CMFCBaseTabCtrl::SetTabBorderSize](../Topic/CMFCBaseTabCtrl::SetTabBorderSize.md)|新しいタブ境界線のサイズを設定します。|  
|[CMFCBaseTabCtrl::SetTabHicon](../Topic/CMFCBaseTabCtrl::SetTabHicon.md)|タブ アイコンを設定します。|  
|[CMFCBaseTabCtrl::SetTabIcon](../Topic/CMFCBaseTabCtrl::SetTabIcon.md)|タブ アイコン ID を設定します。|  
|[CMFCBaseTabCtrl::SetTabIconOnly](../Topic/CMFCBaseTabCtrl::SetTabIconOnly.md)|指定したタブの "アイコンのみ" のモードを有効または無効にします。|  
|[CMFCBaseTabCtrl::SetTabLabel](../Topic/CMFCBaseTabCtrl::SetTabLabel.md)|タブ ラベルを指定した文字列値と同じに設定します。|  
|[CMFCBaseTabCtrl::SetTabsHeight](../Topic/CMFCBaseTabCtrl::SetTabsHeight.md)||  
|[CMFCBaseTabCtrl::SetTabTextColor](../Topic/CMFCBaseTabCtrl::SetTabTextColor.md)|指定したタブのテキストの色を設定します。|  
|[CMFCBaseTabCtrl::SetTabsOrder](../Topic/CMFCBaseTabCtrl::SetTabsOrder.md)|指定した順序でタブを配置します。|  
|[CMFCBaseTabCtrl::ShowTab](../Topic/CMFCBaseTabCtrl::ShowTab.md)|指定したタブを表示または非表示にします。|  
|[CMFCBaseTabCtrl::StartRenameTab](../Topic/CMFCBaseTabCtrl::StartRenameTab.md)||  
|[CMFCBaseTabCtrl::SwapTabs](../Topic/CMFCBaseTabCtrl::SwapTabs.md)||  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCBaseTabCtrl::CreateWrapper](../Topic/CMFCBaseTabCtrl::CreateWrapper.md)|`CDockablePane` から派生しているのではない [CWnd](../Topic/CWnd%20Class.md) から派生したオブジェクトのラッパーを作成します。`CMFCBaseTabCtrl` オブジェクトをドッキングするには、埋め込まれた各コントロールがドッキング ラッパーを持つか、`CDockablePane` から派生する必要があります。<br /><br /> `SetDockingBayWrapperRTC` を使用して、ラッパーのクラスを設定します。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCBaseTabCtrl::m\_bActivateTabOnRightClick](../Topic/CMFCBaseTabCtrl::m_bActivateTabOnRightClick.md)|タブを選択する場合にマウスの左クリックを使用するのか右クリックを使用するのかを指定します。|  
|[CMFCBaseTabCtrl::m\_bAutoDestroyWindow](../Topic/CMFCBaseTabCtrl::m_bAutoDestroyWindow.md)|タブに含まれているウィンドウを自動的に破棄するかどうかを指定します。|  
  
## 解説  
 `CMFCBaseTabCtrl` クラスは抽象クラスです。 したがって、インスタンス化できません。 タブ付きウィンドウを作成するには、`CMFCBaseTabCtrl` からクラスを派生する必要があります。 MFC ライブラリには派生クラスの例がいくつか含まれており、そのうちの 2 つは [CMFCTabCtrl クラス](../../mfc/reference/cmfctabctrl-class.md) と [CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md) です。  
  
 [!INCLUDE[vs_dev14](../../mfc/includes/vs_dev14_md.md)] 以降では、このクラスは Microsoft Active Accessibility をサポートします。  
  
## カスタマイズのヒント  
 以下のヒントは、[CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)、およびそこから継承するクラスに関連するものです。  
  
-   切り離し可能なタブを有効にした場合は、ポインターがタブ付きウィンドウを指したままにしないでください。 これらの切り離し可能なタブは、動的に作成および破棄できます。 したがって、ポインターは無効になる場合があります。  
  
-   マウスを使用することによってユーザーがタブ コントロールでタブを動的に移動できるように、タブ コントロールを構成できます。 この機能は、`CMFCBaseTabCtrl` クラスに組み込まれています。 有効にするには、[CMFCBaseTabCtrl::EnableTabSwap](../Topic/CMFCBaseTabCtrl::EnableTabSwap.md) を呼び出します。  
  
-   既定では、タブは、タブ コントロールに追加するときに切り離し可能です。[CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md) を使用すると、切り離し不可能なタブを追加することもできます。 パラメーター `bDetachable` を `FALSE` に設定した場合、タブは切り離し可能になりません。 メソッド [CMFCBaseTabCtrl::EnableTabDetach](../Topic/CMFCBaseTabCtrl::EnableTabDetach.md) を呼び出すことで、タブが切り離し可能であるかどうかを変更することもできます。  
  
-   [CWnd クラス](../Topic/CWnd%20Class.md) から派生したオブジェクトは、ドッキング可能なコントロール バーまたはドッキング可能なタブに配置できます。 ドッキングするコントロール全体に対して、`CWnd` オブジェクトをドッキング可能にする必要があります。 これを実現するために、MFC ではラッパー クラスを使用します。 このラッパー クラスは [CDockablePaneAdapter クラス](../../mfc/reference/cdockablepaneadapter-class.md) です。 ドッキング可能なコントロール バーまたはドッキング可能なタブに追加された `CWnd` オブジェクトはいずれも、`CDockablePaneAdapter` オブジェクト内で折り返されます。`CMFCBaseTablCtrl` オブジェクトのパラメーター `m_bEnableWrapping` を `FALSE` に設定すると、自動折り返しを無効にできます。 メソッド [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../Topic/CMFCBaseTabCtrl::SetDockingBarWrapperRTC.md) を使用すると、アプリケーションでラッパーとして使用されるクラスを変更することもできます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
## 必要条件  
 **ヘッダー:** afxbasetabctrl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCTabCtrl クラス](../../mfc/reference/cmfctabctrl-class.md)   
 [CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)