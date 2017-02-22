---
title: "CBasePane クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBasePane::get_accKeyboardShortcut"
  - "CBasePane.get_accKeyboardShortcut"
  - "CBasePane.accSelect"
  - "get_accDefaultAction"
  - "accSelect"
  - "CBasePane.accHitTest"
  - "CBasePane.get_accRole"
  - "get_accKeyboardShortcut"
  - "CBasePane::Serialize"
  - "CBasePane"
  - "CBasePane::get_accDefaultAction"
  - "get_accParent"
  - "CBasePane::accSelect"
  - "accLocation"
  - "CBasePane.get_accDescription"
  - "get_accName"
  - "CBasePane::get_accChildCount"
  - "CBasePane.get_accChild"
  - "CBasePane::accHitTest"
  - "accHitTest"
  - "get_accHelp"
  - "CBasePane.get_accChildCount"
  - "CBasePane.get_accValue"
  - "CBasePane::get_accDescription"
  - "get_accChildCount"
  - "CBasePane.accLocation"
  - "CBasePane.PreTranslateMessage"
  - "CBasePane.get_accName"
  - "PreTranslateMessage"
  - "CBasePane::get_accFocus"
  - "get_accDescription"
  - "CBasePane::get_accRole"
  - "get_accValue"
  - "CBasePane.Serialize"
  - "CBasePane::accLocation"
  - "get_accRole"
  - "CBasePane::get_accChild"
  - "get_accFocus"
  - "CBasePane::get_accHelp"
  - "CBasePane.get_accDefaultAction"
  - "CBasePane.get_accHelp"
  - "CBasePane::PreTranslateMessage"
  - "CBasePane::get_accState"
  - "CBasePane.get_accParent"
  - "CBasePane::get_accParent"
  - "get_accChild"
  - "CBasePane::get_accValue"
  - "Serialize"
  - "get_accState"
  - "CBasePane.get_accState"
  - "CBasePane.get_accFocus"
  - "CBasePane::get_accName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accHitTest メソッド"
  - "accLocation メソッド"
  - "accSelect メソッド"
  - "CBasePane クラス"
  - "get_accChild メソッド"
  - "get_accChildCount メソッド"
  - "get_accDefaultAction メソッド"
  - "get_accDescription メソッド"
  - "get_accFocus メソッド"
  - "get_accHelp メソッド"
  - "get_accKeyboardShortcut メソッド"
  - "get_accName メソッド"
  - "get_accParent メソッド"
  - "get_accRole メソッド"
  - "get_accState メソッド"
  - "get_accValue メソッド"
  - "PreTranslateMessage メソッド"
  - "Serialize メソッド"
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
caps.latest.revision: 43
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 44
---
# CBasePane クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC のすべてのペインの基本クラス。  
  
## 構文  
  
```  
class CBasePane : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CBasePane::CBasePane`|既定のコンストラクターです。|  
|`CBasePane::~CBasePane`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|`CBasePane::accHitTest`|画面上の指定された位置にある子要素または子オブジェクトを取得するために、フレームワークによって呼び出されます   \([CWnd::accHitTest](../Topic/CWnd::accHitTest.md) をオーバーライドします\)。|  
|`CBasePane::accLocation`|指定されたオブジェクトの現在の画面位置を取得するために、フレームワークによって呼び出されます   \([CWnd::accLocation](../Topic/CWnd::accLocation.md) をオーバーライドします\)。|  
|[CBasePane::AccNotifyObjectFocusEvent](../Topic/CBasePane::AccNotifyObjectFocusEvent.md)|`CBasePane` は、このメソッドを使用しません。|  
|`CBasePane::accSelect`|選択を変更するため、または指定されたオブジェクトのキーボード フォーカスを移動するために、フレームワークによって呼び出されます   \([CWnd::accSelect](../Topic/CWnd::accSelect.md) をオーバーライドします\)。|  
|[CBasePane::AddPane](../Topic/CBasePane::AddPane.md)|ドッキング マネージャーにペインを追加します。|  
|[CBasePane::AdjustDockingLayout](../Topic/CBasePane::AdjustDockingLayout.md)|ドッキング マネージャーに呼び出しをリダイレクトしてドッキングのレイアウトを調整します。|  
|[CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md)|ペインの内部レイアウトを調整する必要がある場合に、フレームワークによって呼び出されます。|  
|[CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md)|コントロール バーの水平サイズを計算します|  
|[CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md)|このペインに別のペインをドッキングできるかどうかを判定します。|  
|[CBasePane::CanAutoHide](../Topic/CBasePane::CanAutoHide.md)|ペインが自動非表示モードをサポートするかどうかを判定します。|  
|[CBasePane::CanBeAttached](../Topic/CBasePane::CanBeAttached.md)|ペインを別のペインにドッキングできるかどうかを判断します。|  
|[CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md)|ペインを閉じることができるかどうかを判定します。|  
|[CBasePane::CanBeDocked](../Topic/CBasePane::CanBeDocked.md)|ペインを別のペインにドッキングできるかどうかを判断します。|  
|[CBasePane::CanBeResized](../Topic/CBasePane::CanBeResized.md)|ペインのサイズを変更できるかどうかを判定します。|  
|[CBasePane::CanBeTabbedDocument](../Topic/CBasePane::CanBeTabbedDocument.md)|ウィンドウが、MDI タブ付きドキュメントに変換できるかどうかを指定します。|  
|[CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md)|ペインをフローティングできるかどうかを判断します。|  
|[CBasePane::CanFocus](../Topic/CBasePane::CanFocus.md)|ペインがフォーカスを受け取ることができるかどうかを指定します。|  
|[CBasePane::CopyState](../Topic/CBasePane::CopyState.md)|指定されたペインの状態をコピーします。|  
|[CBasePane::CreateDefaultMiniframe](../Topic/CBasePane::CreateDefaultMiniframe.md)|ペインをフローティングできる場合、ミニフレーム ウィンドウを作成します。|  
|[CBasePane::CreateEx](../Topic/CBasePane::CreateEx.md)|ペイン コントロールを作成します。|  
|[CBasePane::DockPane](../Topic/CBasePane::DockPane.md)|ペインを別のペインまたはフレーム ウィンドウにドッキングします。|  
|[CBasePane::DockPaneUsingRTTI](../Topic/CBasePane::DockPaneUsingRTTI.md)|ランタイム型情報を使用することでペインをドッキングします。|  
|[CBasePane::DockToFrameWindow](../Topic/CBasePane::DockToFrameWindow.md)|ドッキング可能ペインをフレームにドッキングします。|  
|[CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md)|別のペインを現在のペインと親フレームの間に動的に挿入できるかどうかを判定します。|  
|[CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md)|メイン フレームへのペインのドッキングを有効にします。|  
|[CBasePane::EnableGripper](../Topic/CBasePane::EnableGripper.md)|グリップを有効または無効にします。  グリップを有効にすると、これをドラッグすることによってペインの位置を変更できるようになります。|  
|`CBasePane::FillWindowRect`|内部使用。|  
|[CBasePane::FloatPane](../Topic/CBasePane::FloatPane.md)|ペインをフローティング状態にします。|  
|`CBasePane::get_accChild`|指定された子の `IDispatch`インターフェイスのアドレスを取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accChild](../Topic/CWnd::get_accChild.md) をオーバーライドします\)。|  
|`CBasePane::get_accChildCount`|このオブジェクトに属する子の数を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accChildCount](../Topic/CWnd::get_accChildCount.md) をオーバーライドします\)。|  
|`CBasePane::get_accDefaultAction`|オブジェクトの既定のアクションを記述する文字列を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accDefaultAction](../Topic/CWnd::get_accDefaultAction.md) をオーバーライドします\)。|  
|`CBasePane::get_accDescription`|指定されたオブジェクトの外観を記述する文字列を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accDescription](../Topic/CWnd::get_accDescription.md) をオーバーライドします\)。|  
|`CBasePane::get_accFocus`|キーボード フォーカスを保持するオブジェクトを取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accFocus](../Topic/CWnd::get_accFocus.md) をオーバーライドします\)。|  
|`CBasePane::get_accHelp`|オブジェクトのヘルプのプロパティの文字列を取得するために、フレームワークによって呼び出されます。  \([CWnd::get\_accHelp](../Topic/CWnd::get_accHelp.md) をオーバーライドします\)。|  
|[CBasePane::get\_accHelpTopic](../Topic/CBasePane::get_accHelpTopic.md)|そのファイルの適切なトピックの指定したオブジェクトと ID に関連付けられている WinHelpfileの完全パスを取得するために、フレームワークによって呼び出されます。  \([CWnd::get\_accHelpTopic](../Topic/CWnd::get_accHelpTopic.md) をオーバーライドします\)。|  
|`CBasePane::get_accKeyboardShortcut`|指定されたオブジェクトのショートカット キーを取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accKeyboardShortcut](../Topic/CWnd::get_accKeyboardShortcut.md) をオーバーライドします\)。|  
|`CBasePane::get_accName`|指定されたオブジェクトの名前を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accName](../Topic/CWnd::get_accName.md) をオーバーライドします\)。|  
|`CBasePane::get_accParent`|オブジェクトの親の `IDispatch` インターフェイスを取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accParent](../Topic/CWnd::get_accParent.md) をオーバーライドします\)。|  
|`CBasePane::get_accRole`|指定されたオブジェクトの役割を記述する情報を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accRole](../Topic/CWnd::get_accRole.md) をオーバーライドします\)。|  
|[CBasePane::get\_accSelection](../Topic/CBasePane::get_accSelection.md)|オブジェクトの選択されている子を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accSelection](../Topic/CWnd::get_accSelection.md) をオーバーライドします\)。|  
|`CBasePane::get_accState`|指定されたオブジェクトの現在の状態を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accState](../Topic/CWnd::get_accState.md) をオーバーライドします\)。|  
|`CBasePane::get_accValue`|指定されたオブジェクトの値を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accValue](../Topic/CWnd::get_accValue.md) をオーバーライドします\)。|  
|[CBasePane::GetCaptionHeight](../Topic/CBasePane::GetCaptionHeight.md)|キャプションの高さを返します|  
|[CBasePane::GetControlBarStyle](../Topic/CBasePane::GetControlBarStyle.md)|コントロール バー スタイルを返します。|  
|[CBasePane::GetCurrentAlignment](../Topic/CBasePane::GetCurrentAlignment.md)|現在のペインの配置を返します。|  
|[CBasePane::GetDockingMode](../Topic/CBasePane::GetDockingMode.md)|ペインの現在のドッキング モードを返します。|  
|[CBasePane::GetDockSiteFrameWnd](../Topic/CBasePane::GetDockSiteFrameWnd.md)|ペインのドッキング サイトであるウィンドウへのポインターを返します。|  
|[CBasePane::GetEnabledAlignment](../Topic/CBasePane::GetEnabledAlignment.md)|ペインに適用されている CBRS\_ALIGN\_ スタイルを返します。|  
|[CBasePane::GetMFCStyle](../Topic/CBasePane::GetMFCStyle.md)|特定の MFC にウィンドウ スタイルを返します。|  
|[CBasePane::GetPaneIcon](../Topic/CBasePane::GetPaneIcon.md)|ペイン アイコンへのハンドルを返します。|  
|`CBasePane::GetPaneRect`|内部使用。|  
|[CBasePane::GetPaneRow](../Topic/CBasePane::GetPaneRow.md)|ペインがドッキングしている [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md) オブジェクトへのポインターを返します。|  
|[CBasePane::GetPaneStyle](../Topic/CBasePane::GetPaneStyle.md)|ペインのスタイルを返します。|  
|[CBasePane::GetParentDockSite](../Topic/CBasePane::GetParentDockSite.md)|親ドッキング サイトへのポインターを返します。|  
|[CBasePane::GetParentMiniFrame](../Topic/CBasePane::GetParentMiniFrame.md)|親ミニフレーム ウィンドウへのポインターを返します。|  
|[CBasePane::GetParentTabbedPane](../Topic/CBasePane::GetParentTabbedPane.md)|親タブ付きペインへのポインターを返します。|  
|[CBasePane::GetParentTabWnd](../Topic/CBasePane::GetParentTabWnd.md)|タブ内にある親ウィンドウへのポインターを返します。|  
|[CBasePane::GetRecentVisibleState](../Topic/CBasePane::GetRecentVisibleState.md)|フレームワークは、ペインをアーカイブから復元されるときにこのメソッドを呼び出します。|  
|[CBasePane::HideInPrintPreviewMode](../Topic/CBasePane::HideInPrintPreviewMode.md)|ウィンドウが印刷プレビューに非表示にするかを指定します。|  
|[CBasePane::InsertPane](../Topic/CBasePane::InsertPane.md)|指定したペインをドッキング マネージャーに登録します。|  
|[CBasePane::IsAccessibilityCompatible](../Topic/CBasePane::IsAccessibilityCompatible.md)|ウィンドウが Active Accessibility をサポートするかどうかを指定します。|  
|[CBasePane::IsAutoHideMode](../Topic/CBasePane::IsAutoHideMode.md)|ペインが自動非表示モードにあるかどうかを判定します。|  
|[CBasePane::IsDialogControl](../Topic/CBasePane::IsDialogControl.md)|ウィンドウがダイアログのコントロールであるかどうかを指定します。|  
|[CBasePane::IsDocked](../Topic/CBasePane::IsDocked.md)|ペインがドッキングされているかどうかを判断します。|  
|[CBasePane::IsFloating](../Topic/CBasePane::IsFloating.md)|ペインがフローティングしているかどうかを判定します。|  
|[CBasePane::IsHorizontal](../Topic/CBasePane::IsHorizontal.md)|ペインが水平方向にドッキングされているかどうかを判定します。|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](../Topic/CBasePane::IsInFloatingMultiPaneFrameWnd.md)|ウィンドウが複数のウィンドウ フレーム ウィンドウにあるかどうかを指定します。|  
|[CBasePane::IsMDITabbed](../Topic/CBasePane::IsMDITabbed.md)|ペインがタブ付きドキュメントとして MDI 子ウィンドウに追加されたかどうかを判定します。|  
|[CBasePane::IsPaneVisible](../Topic/CBasePane::IsPaneVisible.md)|ウィンドウ `WS_VISIBLE` のフラグがに設定されているかどうかを指定します。|  
|[CBasePane::IsPointNearDockSite](../Topic/CBasePane::IsPointNearDockSite.md)|指定された点がドッキング サイトの近くにあるかどうかを判定します。|  
|[CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md)|ペインのサイズを変更できるかどうかを判定します。|  
|[CBasePane::IsRestoredFromRegistry](../Topic/CBasePane::IsRestoredFromRegistry.md)|ペインがレジストリから復元されるかどうかを判断します。|  
|[CBasePane::IsTabbed](../Topic/CBasePane::IsTabbed.md)|ペインがタブ付きウィンドウのタブ コントロールに挿入されているかどうかを調べます。|  
|`CBasePane::IsTooltipTopmost`|内部使用。|  
|[CBasePane::IsVisible](../Topic/CBasePane::IsVisible.md)|ペインが表示されているかどうかを判断します。|  
|[CBasePane::LoadState](../Topic/CBasePane::LoadState.md)|レジストリからペインの状態を読み込みます。|  
|[CBasePane::MoveWindow](../Topic/CBasePane::MoveWindow.md)|ペインを移動します。|  
|[CBasePane::OnAfterChangeParent](../Topic/CBasePane::OnAfterChangeParent.md)|ペインの親が変更されたときに、フレームワークによって呼び出されます。|  
|[CBasePane::OnBeforeChangeParent](../Topic/CBasePane::OnBeforeChangeParent.md)|ペインが親ウィンドウを変更する直前に、フレームワークによって呼び出されます。|  
|[CBasePane::OnDrawCaption](../Topic/CBasePane::OnDrawCaption.md)|フレームワークは、キャプションを描画するときにこのメソッドを呼び出します。|  
|[CBasePane::OnMovePaneDivider](../Topic/CBasePane::OnMovePaneDivider.md)|このメソッドは、現在使用されません。|  
|[CBasePane::OnPaneContextMenu](../Topic/CBasePane::OnPaneContextMenu.md)|ペインのリストを持つメニューをビルドするときに、フレームワークによって呼び出されます。|  
|[CBasePane::OnRemoveFromMiniFrame](../Topic/CBasePane::OnRemoveFromMiniFrame.md)|ペインが親ミニフレーム ウィンドウから削除されるときに、フレームワークによって呼び出されます。|  
|[CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md)|`CBasePane` は、このメソッドを使用しません。|  
|`CBasePane::OnUpdateCmdUI`|内部使用。|  
|[CBasePane::PaneFromPoint](../Topic/CBasePane::PaneFromPoint.md)|指定した点を含むペインを返します。|  
|`CBasePane::PreTranslateMessage`|ウィンドウ メッセージが Windows 関数の [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) および [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) にディスパッチされる前に、メッセージを変換するために [CWinApp](../../mfc/reference/cwinapp-class.md) クラスによって使用されます   \([CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md) をオーバーライドします\)。|  
|[CBasePane::RecalcLayout](../Topic/CBasePane::RecalcLayout.md)|`CBasePane` は、このメソッドを使用しません。|  
|[CBasePane::RemovePaneFromDockManager](../Topic/CBasePane::RemovePaneFromDockManager.md)|ペインの登録を解除し、ドッキング マネージャーの一覧から削除します。|  
|[CBasePane::SaveState](../Topic/CBasePane::SaveState.md)|レジストリにペインの状態を保存します。|  
|[CBasePane::SelectDefaultFont](../Topic/CBasePane::SelectDefaultFont.md)|指定されたデバイス コンテキストに既定のフォントを選択します。|  
|`CBasePane::Serialize`|このオブジェクトをアーカイブから読み取ったり、アーカイブに書き込んだりします。  \([CObject::Serialize](../Topic/CObject::Serialize.md) をオーバーライドします\)。|  
|[CBasePane::SetControlBarStyle](../Topic/CBasePane::SetControlBarStyle.md)|コントロール バー スタイルを設定します。|  
|[CBasePane::SetDockingMode](../Topic/CBasePane::SetDockingMode.md)|ペインのドッキング モードを設定します。|  
|`CBasePane::SetMDITabbed`|内部使用。|  
|[CBasePane::SetPaneAlignment](../Topic/CBasePane::SetPaneAlignment.md)|ペインの配置を設定します。|  
|`CBasePane::SetPaneRect`|内部使用。|  
|[CBasePane::SetPaneStyle](../Topic/CBasePane::SetPaneStyle.md)|ペインのスタイルを設定します。|  
|`CBasePane::SetRestoredFromRegistry`|内部使用。|  
|[CBasePane::SetWindowPos](../Topic/CBasePane::SetWindowPos.md)|ペインのサイズ、位置、および z オーダーを変更します。|  
|[CBasePane::ShowPane](../Topic/CBasePane::ShowPane.md)|ペインの表示と非表示を切り替えます。|  
|[CBasePane::StretchPane](../Topic/CBasePane::StretchPane.md)|ペインを垂直方向または水平方向に引き伸ばします。|  
|[CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md)|ペインが現在ドッキングしているドッキング サイト、既定スライダー、またはミニフレーム ウィンドウからそのペインを削除します|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CBasePane::DoPaint](../Topic/CBasePane::DoPaint.md)|ペインの背景色を塗りつぶします。|  
  
## 解説  
 作成する場合は、拡張ドッキング機能をサポートするウィンドウ クラスは `CBasePane` または [CPane クラス](../../mfc/reference/cpane-class.md)から、MFC を使用して、それを派生させる必要があります。にします。  
  
## カスタマイズのヒント  
 次のカスタマイズのヒントは、[CBasePane Class](../../mfc/reference/cbasepane-class.md)とそこから継承されるすべてのクラスに関するものです。  
  
-   ペインを作成するときは、次のいくつかの新しいスタイルを適用できます。  
  
    -   `AFX_CBRS_FLOAT` は、ペインをフローティング状態にします。  
  
    -   `AFX_CBRS_AUTOHIDE` は、自動非表示モードを有効にします。  
  
    -   `AFX_CBRS_CLOSE` は、ペインを閉じる \(非表示にする\) ことができます。  
  
     これらのフラグは、ビットごとの OR 演算子と組み合わせることができます。  
  
     `CBasePane` は、仮想ブール値メソッド [CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md)、[CBasePane::CanAutoHide](../Topic/CBasePane::CanAutoHide.md)、[CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md) を実装して、これらのフラグを反映します。  派生クラスでこれらのフラグをオーバーライドして、動作をカスタマイズできます。  
  
-   [CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md) をオーバーライドすると、ドッキング動作をカスタマイズできます。  別のペインをドッキングできないようにするには、ペインがこのメソッドから `FALSE` を返すようにします。  
  
-   フローティング状態にできず、別のペインを前にドッキングできない \(OutlookDemo サンプルの Outlook バーのような\) 静的ペインを作成するには、ペインを非フローティングで作成し、[CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md) をオーバーライドして `FALSE` を返します。  `AFX_CBRS_FLOAT` スタイルを設定せずにペインが作成された場合、既定の実装は `FALSE` を返します。  
  
-   すべてのペインは、\-1 以外の ID で作成します。  
  
-   ペインの表示\/非表示を確認するには、[CBasePane::IsVisible](../Topic/CBasePane::IsVisible.md) を使用します。  タブ付きモードと自動非表示モードで表示状態が正常に処理されます。  
  
-   非フローティングのサイズ変更可能なペインを作成するには、`AFX_CBRS_FLOAT` スタイルを設定せずにペインを作成し、[CFrameWnd::DockControlBar](../Topic/CFrameWnd::DockControlBar.md) を呼び出します。  
  
-   ペインをドッキング レイアウトから除外したり、ドッキング バーからツール バーを削除するには、[CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md) を呼び出します。  自動非表示モードのペインや、タブ付きウィンドウのタブに存在するペインについては、このメソッドを呼び出さないでください。  
  
-   自動非表示モードのペインをフローティング状態にしたり、ドッキング解除するには、[CBasePane::FloatPane](../Topic/CBasePane::FloatPane.md) または [CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md) を呼び出す前に、最初の引数に `FALSE` を指定して [CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md) を呼び出す必要があります。  
  
## 使用例  
 次の例は、`CBasePane` クラスのさまざまなメソッドの使用方法を説明しています。  例では、`CFrameWndEx` クラスからペインを取得する方法およびドッキング モード、ペインの配置、およびペインのスタイルを設定する方法を説明します。  コードは [Word のスペースのサンプル](../../top/visual-cpp-samples.md)からです。  
  
 [!code-cpp[NVC_MFC_WordPad#2](../../mfc/reference/codesnippet/CPP/cbasepane-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
## 必要条件  
 **ヘッダー :** afxbasepane.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)