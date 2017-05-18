---
title: "CBasePane クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBasePane
- AFXBASEPANE/CBasePane
- AFXBASEPANE/CBasePane::AccNotifyObjectFocusEvent
- AFXBASEPANE/CBasePane::AddPane
- AFXBASEPANE/CBasePane::AdjustDockingLayout
- AFXBASEPANE/CBasePane::AdjustLayout
- AFXBASEPANE/CBasePane::CalcFixedLayout
- AFXBASEPANE/CBasePane::CanAcceptPane
- AFXBASEPANE/CBasePane::CanAutoHide
- AFXBASEPANE/CBasePane::CanBeAttached
- AFXBASEPANE/CBasePane::CanBeClosed
- AFXBASEPANE/CBasePane::CanBeDocked
- AFXBASEPANE/CBasePane::CanBeResized
- AFXBASEPANE/CBasePane::CanBeTabbedDocument
- AFXBASEPANE/CBasePane::CanFloat
- AFXBASEPANE/CBasePane::CanFocus
- AFXBASEPANE/CBasePane::CopyState
- AFXBASEPANE/CBasePane::CreateDefaultMiniframe
- AFXBASEPANE/CBasePane::CreateEx
- AFXBASEPANE/CBasePane::DockPane
- AFXBASEPANE/CBasePane::DockPaneUsingRTTI
- AFXBASEPANE/CBasePane::DockToFrameWindow
- AFXBASEPANE/CBasePane::DoesAllowDynInsertBefore
- AFXBASEPANE/CBasePane::EnableDocking
- AFXBASEPANE/CBasePane::EnableGripper
- AFXBASEPANE/CBasePane::FloatPane
- AFXBASEPANE/CBasePane::get_accHelpTopic
- AFXBASEPANE/CBasePane::get_accSelection
- AFXBASEPANE/CBasePane::GetCaptionHeight
- AFXBASEPANE/CBasePane::GetControlBarStyle
- AFXBASEPANE/CBasePane::GetCurrentAlignment
- AFXBASEPANE/CBasePane::GetDockingMode
- AFXBASEPANE/CBasePane::GetDockSiteFrameWnd
- AFXBASEPANE/CBasePane::GetEnabledAlignment
- AFXBASEPANE/CBasePane::GetMFCStyle
- AFXBASEPANE/CBasePane::GetPaneIcon
- AFXBASEPANE/CBasePane::GetPaneRow
- AFXBASEPANE/CBasePane::GetPaneStyle
- AFXBASEPANE/CBasePane::GetParentDockSite
- AFXBASEPANE/CBasePane::GetParentMiniFrame
- AFXBASEPANE/CBasePane::GetParentTabbedPane
- AFXBASEPANE/CBasePane::GetParentTabWnd
- AFXBASEPANE/CBasePane::GetRecentVisibleState
- AFXBASEPANE/CBasePane::HideInPrintPreviewMode
- AFXBASEPANE/CBasePane::InsertPane
- AFXBASEPANE/CBasePane::IsAccessibilityCompatible
- AFXBASEPANE/CBasePane::IsAutoHideMode
- AFXBASEPANE/CBasePane::IsDialogControl
- AFXBASEPANE/CBasePane::IsDocked
- AFXBASEPANE/CBasePane::IsFloating
- AFXBASEPANE/CBasePane::IsHorizontal
- AFXBASEPANE/CBasePane::IsInFloatingMultiPaneFrameWnd
- AFXBASEPANE/CBasePane::IsMDITabbed
- AFXBASEPANE/CBasePane::IsPaneVisible
- AFXBASEPANE/CBasePane::IsPointNearDockSite
- AFXBASEPANE/CBasePane::IsResizable
- AFXBASEPANE/CBasePane::IsRestoredFromRegistry
- AFXBASEPANE/CBasePane::IsTabbed
- AFXBASEPANE/CBasePane::IsVisible
- AFXBASEPANE/CBasePane::LoadState
- AFXBASEPANE/CBasePane::MoveWindow
- AFXBASEPANE/CBasePane::OnAfterChangeParent
- AFXBASEPANE/CBasePane::OnBeforeChangeParent
- AFXBASEPANE/CBasePane::OnDrawCaption
- AFXBASEPANE/CBasePane::OnMovePaneDivider
- AFXBASEPANE/CBasePane::OnPaneContextMenu
- AFXBASEPANE/CBasePane::OnRemoveFromMiniFrame
- AFXBASEPANE/CBasePane::OnSetAccData
- AFXBASEPANE/CBasePane::PaneFromPoint
- AFXBASEPANE/CBasePane::RecalcLayout
- AFXBASEPANE/CBasePane::RemovePaneFromDockManager
- AFXBASEPANE/CBasePane::SaveState
- AFXBASEPANE/CBasePane::SelectDefaultFont
- AFXBASEPANE/CBasePane::SetControlBarStyle
- AFXBASEPANE/CBasePane::SetDockingMode
- AFXBASEPANE/CBasePane::SetPaneAlignment
- AFXBASEPANE/CBasePane::SetPaneStyle
- AFXBASEPANE/CBasePane::SetWindowPos
- AFXBASEPANE/CBasePane::ShowPane
- AFXBASEPANE/CBasePane::StretchPane
- AFXBASEPANE/CBasePane::UndockPane
- AFXBASEPANE/CBasePane::DoPaint
dev_langs:
- C++
helpviewer_keywords:
- get_accState method
- get_accHelp method
- CBasePane class
- accLocation method
- accHitTest method
- get_accDescription method
- get_accDefaultAction method
- get_accName method
- get_accFocus method
- get_accRole method
- get_accValue method
- get_accChild method
- accSelect method
- get_accKeyboardShortcut method
- get_accChildCount method
- Serialize method
- PreTranslateMessage method
- get_accParent method
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
caps.latest.revision: 43
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0444c0647d83a1e9b431dd0c5bdb369da213b91b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cbasepane-class"></a>CBasePane クラス
MFC でのすべてのペインの基本クラス。  
  
## <a name="syntax"></a>構文  
  
```  
class CBasePane : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CBasePane::CBasePane`|既定のコンストラクター|  
|`CBasePane::~CBasePane`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CBasePane::accHitTest`|画面上の指定された位置にある子要素または子オブジェクトを取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::accHitTest](../../mfc/reference/cwnd-class.md#acchittest))。|  
|`CBasePane::accLocation`|指定したオブジェクトの現在の画面位置を取得するためにフレームワークによって呼び出されます。 (上書き[CWnd::accLocation](../../mfc/reference/cwnd-class.md#acclocation))。|  
|[CBasePane::AccNotifyObjectFocusEvent](#accnotifyobjectfocusevent)|`CBasePane`このメソッドは使用されません。|  
|`CBasePane::accSelect`|選択を変更するため、または指定されたオブジェクトのキーボード フォーカスを移動するために、フレームワークによって呼び出されます。 (上書き[CWnd::accSelect](../../mfc/reference/cwnd-class.md#accselect))。|  
|[CBasePane::AddPane](#addpane)|ペインをドッキング マネージャーに追加します。|  
|[CBasePane::AdjustDockingLayout](#adjustdockinglayout)|ドッキング レイアウトを調整するには、ドッキング マネージャーに呼び出しをリダイレクトします。|  
|[CBasePane::AdjustLayout](#adjustlayout)|ウィンドウは、その内部のレイアウトを調整する必要があるときに、フレームワークによって呼び出されます。|  
|[CBasePane::CalcFixedLayout](#calcfixedlayout)|コントロール バーの水平方向のサイズを計算します。|  
|[CBasePane::CanAcceptPane](#canacceptpane)|別のウィンドウをウィンドウにドッキングできるかどうかを決定します。|  
|[CBasePane::CanAutoHide](#canautohide)|ペインが自動非表示モードをサポートするかどうかを決定します。|  
|[CBasePane::CanBeAttached](#canbeattached)|別のペインに、ウィンドウをドッキングできるかどうかを決定します。|  
|[CBasePane::CanBeClosed](#canbeclosed)|ウィンドウを閉じることがあるかどうかを決定します。|  
|[CBasePane::CanBeDocked](#canbedocked)|別のペインに、ウィンドウをドッキングできるかどうかを決定します。|  
|[CBasePane::CanBeResized](#canberesized)|ウィンドウのサイズを変更できるかどうかを決定します。|  
|[CBasePane::CanBeTabbedDocument](#canbetabbeddocument)|MDI タブ付きドキュメントに、ウィンドウを変換できるかどうかを指定します。|  
|[CBasePane::CanFloat](#canfloat)|ペインをフローティングできるかどうかを決定します。|  
|[CBasePane::CanFocus](#canfocus)|ウィンドウがフォーカスを取得できるかどうかを指定します。|  
|[CBasePane::CopyState](#copystate)|指定されたウィンドウの状態をコピーします。|  
|[CBasePane::CreateDefaultMiniframe](#createdefaultminiframe)|ペインをフローティングできる場合は、ミニフレーム ウィンドウを作成します。|  
|[CBasePane::CreateEx](#createex)|ウィンドウ コントロールを作成します。|  
|[CBasePane::DockPane](#dockpane)|別のウィンドウまたはフレームのウィンドウ ペインをドッキングします。|  
|[CBasePane::DockPaneUsingRTTI](#dockpaneusingrtti)|実行時型情報を使用して、ウィンドウをドッキングします。|  
|[CBasePane::DockToFrameWindow](#docktoframewindow)|フレームにドッキング可能ペインをドッキングします。|  
|[CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|このペインと親フレームの間の別のウィンドウを動的に挿入するかどうかを決定します。|  
|[CBasePane::EnableDocking](#enabledocking)|メイン フレーム ウィンドウのドッキングを有効にします。|  
|[CBasePane::EnableGripper](#enablegripper)|有効またはグリッパーを無効にします。 グリッパーが有効になっている場合、ユーザーは、ウィンドウの位置を変更することをドラッグできます。|  
|`CBasePane::FillWindowRect`|内部的に使用します。|  
|[CBasePane::FloatPane](#floatpane)|ペインをフローティング状態です。|  
|`CBasePane::get_accChild`|指定された子の `IDispatch` インターフェイスのアドレスを取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accChild](../../mfc/reference/cwnd-class.md#get_accchild))。|  
|`CBasePane::get_accChildCount`|このオブジェクトに属する子の数を取得するためにフレームワークによって呼び出されます。 (上書き[CWnd::get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount))。|  
|`CBasePane::get_accDefaultAction`|オブジェクトの既定のアクションを説明する文字列を取得するためにフレームワークによって呼び出されます。 (上書き[CWnd::get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction))。|  
|`CBasePane::get_accDescription`|指定されたオブジェクトの外観を記述する文字列を取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription))。|  
|`CBasePane::get_accFocus`|キーボード フォーカスを保持するオブジェクトを取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus))。|  
|`CBasePane::get_accHelp`|オブジェクトのヘルプ プロパティ文字列を取得するためにフレームワークによって呼び出されます。 (上書き[CWnd::get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp))。|  
|[CBasePane::get_accHelpTopic](#get_acchelptopic)|指定したオブジェクトに関連付けられている WinHelp ファイルの完全なパスとファイルの適切なトピックの識別子を取得するためにフレームワークによって呼び出されます。 (上書き[CWnd::get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic))。|  
|`CBasePane::get_accKeyboardShortcut`|オブジェクトの指定されたショートカット キーを取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut))。|  
|`CBasePane::get_accName`|指定されたオブジェクトの名前を取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accName](../../mfc/reference/cwnd-class.md#get_accname))。|  
|`CBasePane::get_accParent`|取得するためにフレームワークによって呼び出される、`IDispatch`オブジェクトの親のインターフェイスです。 (上書き[CWnd::get_accParent](../../mfc/reference/cwnd-class.md#get_accparent))。|  
|`CBasePane::get_accRole`|指定されたオブジェクトの役割を記述する情報を取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accRole](../../mfc/reference/cwnd-class.md#get_accrole))。|  
|[CBasePane::get_accSelection](#get_accselection)|このオブジェクトの選択されている子を取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection))。|  
|`CBasePane::get_accState`|指定されたオブジェクトの現在の状態を取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accState](../../mfc/reference/cwnd-class.md#get_accstate))。|  
|`CBasePane::get_accValue`|指定されたオブジェクトの値を取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue))。|  
|[CBasePane::GetCaptionHeight](#getcaptionheight)|キャプションの高さを返します。|  
|[CBasePane::GetControlBarStyle](#getcontrolbarstyle)|コントロール バーのスタイルを返します。|  
|[CBasePane::GetCurrentAlignment](#getcurrentalignment)|現在のウィンドウの配置を返します。|  
|[CBasePane::GetDockingMode](#getdockingmode)|現在のドッキング ペインのモードを返します。|  
|[CBasePane::GetDockSiteFrameWnd](#getdocksiteframewnd)|ペインのドッキング サイトは、ウィンドウへのポインターを返します。|  
|[CBasePane::GetEnabledAlignment](#getenabledalignment)|ウィンドウに適用される cbrs_align _ スタイルを返します。|  
|[CBasePane::GetMFCStyle](#getmfcstyle)|MFC 特定のペインのスタイルを返します。|  
|[CBasePane::GetPaneIcon](#getpaneicon)|ペインのアイコンのハンドルを返します。|  
|`CBasePane::GetPaneRect`|内部的に使用します。|  
|[CBasePane::GetPaneRow](#getpanerow)|ポインターを返す、 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)ウィンドウがドッキングされているオブジェクト。|  
|[CBasePane::GetPaneStyle](#getpanestyle)|ウィンドウ スタイルを返します。|  
|[CBasePane::GetParentDockSite](#getparentdocksite)|親ドッキング サイトへのポインターを返します。|  
|[CBasePane::GetParentMiniFrame](#getparentminiframe)|親ミニフレーム ウィンドウへのポインターを返します。|  
|[CBasePane::GetParentTabbedPane](#getparenttabbedpane)|親のタブ付きペインへのポインターを返します。|  
|[CBasePane::GetParentTabWnd](#getparenttabwnd)|タブ内にある親ウィンドウへのポインターを返します。|  
|[CBasePane::GetRecentVisibleState](#getrecentvisiblestate)|フレームワークは、ペインがアーカイブから復元された場合、このメソッドを呼び出します。|  
|[CBasePane::HideInPrintPreviewMode](#hideinprintpreviewmode)|印刷プレビューで、ウィンドウが非表示かどうかを指定します。|  
|[CBasePane::InsertPane](#insertpane)|指定したウィンドウをドッキング マネージャーに登録します。|  
|[CBasePane::IsAccessibilityCompatible](#isaccessibilitycompatible)|ペインがアクティブなユーザー補助をサポートするかどうかを指定します。|  
|[CBasePane::IsAutoHideMode](#isautohidemode)|ペインが自動非表示モードになっているかどうかを判断します。|  
|[CBasePane::IsDialogControl](#isdialogcontrol)|ウィンドウが、ダイアログ コントロールであるかどうかを指定します。|  
|[CBasePane::IsDocked](#isdocked)|ウィンドウがドッキングされているかどうかを決定します。|  
|[CBasePane::IsFloating](#isfloating)|ペインをフローティングするかどうかを決定します。|  
|[CBasePane::IsHorizontal](#ishorizontal)|ウィンドウが水平方向にドッキングされているかどうかを決定します。|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|ウィンドウが複数のウィンドウ フレーム ウィンドウかどうかを指定します。|  
|[CBasePane::IsMDITabbed](#ismditabbed)|タブ付きドキュメントとしての MDI 子ウィンドウに、ウィンドウが追加されているかどうかを決定します。|  
|[CBasePane::IsPaneVisible](#ispanevisible)|指定するかどうか、`WS_VISIBLE`のウィンドウでフラグを設定します。|  
|[CBasePane::IsPointNearDockSite](#ispointneardocksite)|指定した点がドッキング サイトの近くにいるかどうかを判断します。|  
|[CBasePane::IsResizable](#isresizable)|ウィンドウのサイズを変更できるかどうかを決定します。|  
|[CBasePane::IsRestoredFromRegistry](#isrestoredfromregistry)|ペインがレジストリから復元されるかどうかを決定します。|  
|[CBasePane::IsTabbed](#istabbed)|タブ付きウィンドウのタブ コントロールに、ウィンドウが挿入されたかどうかを決定します。|  
|`CBasePane::IsTooltipTopmost`|内部的に使用します。|  
|[CBasePane::IsVisible](#isvisible)|ウィンドウが表示されているかどうかを決定します。|  
|[CBasePane::LoadState](#loadstate)|レジストリからペインの状態を読み込みます。|  
|[CBasePane::MoveWindow](#movewindow)|ウィンドウに移動します。|  
|[CBasePane::OnAfterChangeParent](#onafterchangeparent)|ウィンドウの親が変更されたときに、フレームワークによって呼び出されます。|  
|[CBasePane::OnBeforeChangeParent](#onbeforechangeparent)|ウィンドウは、親ウィンドウを変更する前に、フレームワークによって呼び出されます。|  
|[CBasePane::OnDrawCaption](#ondrawcaption)|フレームワークは、キャプションが描画されるときに、このメソッドを呼び出します。|  
|[CBasePane::OnMovePaneDivider](#onmovepanedivider)|このメソッドは現在使用されていません。|  
|[CBasePane::OnPaneContextMenu](#onpanecontextmenu)|ウィンドウのリストを持つメニューを作成するときに、フレームワークによって呼び出されます。|  
|[CBasePane::OnRemoveFromMiniFrame](#onremovefromminiframe)|親ミニフレーム ウィンドウから、ウィンドウが削除されたときに、フレームワークによって呼び出されます。|  
|[CBasePane::OnSetAccData](#onsetaccdata)|`CBasePane`このメソッドは使用されません。|  
|`CBasePane::OnUpdateCmdUI`|内部的に使用します。|  
|[CBasePane::PaneFromPoint](#panefrompoint)|指定したポイントを含むペインを返します。|  
|`CBasePane::PreTranslateMessage`|クラスで使用される[CWinApp](../../mfc/reference/cwinapp-class.md)にディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数です。 (上書き[CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage))。|  
|[CBasePane::RecalcLayout](#recalclayout)|`CBasePane`このメソッドは使用されません。|  
|[CBasePane::RemovePaneFromDockManager](#removepanefromdockmanager)|ペインの登録を解除し、ドッキング マネージャーの一覧から削除されます。|  
|[CBasePane::SaveState](#savestate)|レジストリにペインの状態を保存します。|  
|[CBasePane::SelectDefaultFont](#selectdefaultfont)|指定したデバイス コンテキストの既定のフォントを選択します。|  
|`CBasePane::Serialize`|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。 (上書き[指定](../../mfc/reference/cobject-class.md#serialize))。|  
|[CBasePane::SetControlBarStyle](#setcontrolbarstyle)|コントロール バーのスタイルを設定します。|  
|[CBasePane::SetDockingMode](#setdockingmode)|ペインのドッキング モードを設定します。|  
|`CBasePane::SetMDITabbed`|内部的に使用します。|  
|[CBasePane::SetPaneAlignment](#setpanealignment)|ペインの配置を設定します。|  
|`CBasePane::SetPaneRect`|内部的に使用します。|  
|[CBasePane::SetPaneStyle](#setpanestyle)|ウィンドウのスタイルを設定します。|  
|`CBasePane::SetRestoredFromRegistry`|内部的に使用します。|  
|[CBasePane::SetWindowPos](#setwindowpos)|サイズ、位置、およびウィンドウの Z オーダーを変更します。|  
|[CBasePane::ShowPane](#showpane)|ウィンドウの表示と非表示を切り替えます。|  
|[CBasePane::StretchPane](#stretchpane)|垂直または水平方向にウィンドウを拡大します。|  
|[CBasePane::UndockPane](#undockpane)|ドッキング サイト、既定のスライダーまたはミニフレーム ウィンドウの現在のドッキング位置から、ウィンドウを削除します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBasePane::DoPaint](#dopaint)|ペインの背景を設定します。|  
  
## <a name="remarks"></a>コメント  
 MFC で使用できる拡張のドッキング機能をサポートするウィンドウ クラスを作成する場合をから派生する必要があります`CBasePane`またはから[CPane クラス](../../mfc/reference/cpane-class.md)します。  
  
## <a name="customization-tips"></a>カスタマイズのヒント  
 次のカスタマイズのヒントに関する、`CBasePane Class`とそれを継承したクラス。  
  
-   ウィンドウを作成するときは、いくつかの新しいスタイルを適用できます。  
  
    - `AFX_CBRS_FLOAT`ペインをフローティングを使用できます。  
  
    - `AFX_CBRS_AUTOHIDE`により自動的に隠すモード。  
  
    - `AFX_CBRS_CLOSE`(非表示)、終了するウィンドウを使用できます。  
  
     これらは、フラグ ビットごとの OR 操作を組み合わせることができます。  
  
 `CBasePane`これらのフラグを反映するために次の仮想ブール メソッドを実装する: [CBasePane::CanBeClosed](#canbeclosed)、 [CBasePane::CanAutoHide](#canautohide)、 [CBasePane::CanFloat](#canfloat)します。 動作をカスタマイズする派生クラスでオーバーライドできます。  
  
-   ドッキングの動作をカスタマイズするには、オーバーライドすることで[CBasePane::CanAcceptPane](#canacceptpane)します。 ウィンドウを返す、`FALSE`別のウィンドウをドッキングされないようにするのには、このメソッドからです。  
  
-   静的のウィンドウを使用しているフロートすることはできず、、他のウィンドウは前に、ドッキングできなくなります (OutlookDemo 例では、Outlook バーに似ています) を作成する場合は、フローティングとして作成し、オーバーライド[CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)を返す`FALSE`します。 既定の実装`FALSE`なしのウィンドウで作成された場合、`AFX_CBRS_FLOAT`スタイル。  
  
-   -1 以外の Id を持つすべてのペインを作成します。  
  
-   ウィンドウの可視性を調べるには使用[CBasePane::IsVisible](#isvisible)します。 表示状態が正常に処理タブ付きモードと自動非表示モード。  
  
-   フローティングのサイズ変更可能なウィンドウを作成する場合は、作成しないまま、`AFX_CBRS_FLOAT`スタイルおよび呼び出し[CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar)します。  
  
-   ペインをドッキング レイアウトから除外する、またはそのドッキング バーからツールバーを削除するには、呼び出す[CBasePane::UndockPane](#undockpane)します。 自動非表示モードのペインまたはウィンドウのタブ付きウィンドウのタブ内に存在するには、このメソッドを呼び出さないでください。  
  
-   浮動小数点数を自動的に隠すモードになっているペインをドッキング解除するか、呼び出す必要があります[CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode)と`FALSE`を呼び出す前に、最初の引数として[CBasePane::FloatPane](#floatpane)または[CBasePane::UndockPane](#undockpane)します。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CBasePane`クラスです。 ウィンドウを取得する方法の例、`CFrameWndEx`クラスとドッキング モード、ペインの配置、およびウィンドウのスタイルを設定する方法です。 コードから、 [Word パッド サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_WordPad&#2;](../../mfc/reference/codesnippet/cpp/cbasepane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxbasepane.h  
  
##  <a name="accnotifyobjectfocusevent"></a>CBasePane::AccNotifyObjectFocusEvent  
 `CBasePane`このメソッドは使用されません。  
  
```  
virtual void AccNotifyObjectFocusEvent(int);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `int`  
 使用しません。  
  
##  <a name="addpane"></a>CBasePane::AddPane  
 ペインをドッキング マネージャーに追加します。  
  
```  
void AddPane(CBasePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 追加するペインへのポインター。  
  
### <a name="remarks"></a>コメント  
 これは、ペインをドッキング マネージャーに追加するための便利なメソッドです。 このメソッドを使用すると、親フレームの型を分析するコードを記述する必要はありません。  
  
 詳細については、次を参照してください。 [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)と[CMDIFrameWndEx::AddPane](../../mfc/reference/cmdiframewndex-class.md#addpane)します。  
  
##  <a name="adjustdockinglayout"></a>CBasePane::AdjustDockingLayout  
 ドッキング レイアウトを調整するには、ドッキング マネージャーに呼び出しをリダイレクトします。  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `hdwp`  
 複数のウィンドウの位置を含む構造体へのハンドル。  
  
### <a name="remarks"></a>コメント  
 これは、ドッキング レイアウトを調整するための便利なメソッドです。 このメソッドを使用すると、親フレームの型を分析するコードを記述する必要はありません。  
  
 詳細については、次を参照してください[CDockingManager::AdjustDockingLayout。](../../mfc/reference/cdockingmanager-class.md#adjustdockinglayout)  
  
##  <a name="adjustlayout"></a>CBasePane::AdjustLayout  
 ウィンドウの内部のレイアウトを調整するためにフレームワークによって呼び出されます。  
  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ウィンドウの内部のレイアウトを調整しなければならない場合に、このメソッドを呼び出します。 基本の実装では、何も行いません。  
  
##  <a name="calcfixedlayout"></a>CBasePane::CalcFixedLayout  
 コントロール バーの水平方向のサイズを計算します。  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bStretch`  
 フレームのサイズをバーを拡大するかどうかを示します。 `bStretch`パラメーターは 0 以外のバー ドッキング バー (ドッキングは使用できません) ではないありが 0 ドッキングまたはフローティングにあるとき (ドッキングの使用可能)。  
  
 [入力] `bHorz`  
 バーが水平方向または垂直方向であることを示します。 `bHorz`場合は、バーが水平方向および垂直方向である場合は 0、パラメーターが 0 以外の値。  
  
### <a name="return-value"></a>戻り値  
 コントロール バーのサイズをピクセル単位での`CSize`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 「解説」セクションを参照してください[CControlBar::CalcFixedLayout](../../mfc/reference/ccontrolbar-class.md#calcfixedlayout)  
  
##  <a name="canacceptpane"></a>CBasePane::CanAcceptPane  
 別のウィンドウをウィンドウにドッキングできるかどうかを決定します。  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 ドッキングするのには、ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`別のウィンドウが許可される場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 指定されたウィンドウをドッキングする前に、フレームワークはこのメソッドを呼び出して`pBar`現在のウィンドウにします。  
  
 このメソッドを使用して、 [CBasePane::CanBeDocked](#canbedocked)ペインと、アプリケーションの他のペインのドッキングを制御します。  
  
 既定の実装では、`FALSE` が返されます。  
  
##  <a name="canautohide"></a>CBasePane::CanAutoHide  
 ペインが自動非表示モードをサポートするかどうかを決定します。  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このウィンドウは、自動非表示モードをサポートしている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ウィンドウが自動非表示モードをサポートするかどうかを確認するには、この関数を呼び出します。  
  
 構築時に、この機能を設定を渡すことによって、`AFX_CBRS_AUTOHIDE`フラグを[CBasePane::CreateEx](#createex)します。  
  
 既定の実装、`AFX_CBRS_AUTOHIDE`フラグ。 この動作をカスタマイズする派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="canbeattached"></a>CBasePane::CanBeAttached  
 別のウィンドウまたはフレーム ウィンドウのウィンドウをドッキングできるかどうかを決定します。  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`別のウィンドウまたはフレーム ウィンドウに、ウィンドウをドッキングできる場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、`FALSE` が返されます。 このメソッドを有効または呼び出さずにドッキングする機能を無効にする派生クラスでオーバーライド[CBasePane::EnableDocking](#enabledocking)します。  
  
##  <a name="canbeclosed"></a>CBasePane::CanBeClosed  
 ウィンドウを閉じることがあるかどうかを決定します。  
  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ウィンドウを閉じることができます。それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ウィンドウを閉じることがあるかどうかを判断するには、このメソッドを呼び出します。 メソッドが返す場合`TRUE`、**閉じる**ペインのタイトル バーにボタンが追加またはミニフレーム ウィンドウのタイトル バーに、ウィンドウがフローティングします。  
  
 構築時に、この機能を設定を渡すことによって、`AFX_CBRS_CLOSE`フラグを[CBasePane::CreateEx](#createex)します。  
  
 既定の実装、`AFX_CBRS_CLOSE`フラグ。  
  
##  <a name="canbedocked"></a>CBasePane::CanBeDocked  
 別のペインに、ウィンドウをドッキングできるかどうかを決定します。  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockBar`  
 別のウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このペインは、別のペインをドッキングできる場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 指定されたウィンドウをドッキングする前に、フレームワークはこのメソッドを呼び出して`pDockBar`現在のウィンドウにします。  
  
 このメソッドを使用して、 [CBasePane::CanAcceptPane](#canacceptpane)ペインと、アプリケーションの他のペインのドッキングを制御します。  
  
 既定の実装では、`FALSE` が返されます。  
  
##  <a name="canberesized"></a>CBasePane::CanBeResized  
 ウィンドウのサイズを変更できるかどうかを決定します。  
  
```  
virtual BOOL CanBeResized() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウのサイズを変更する場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドはのチェック、`AFX_CBRS_RESIZE`フラグは、既定で指定された`CBasePane::OnCreate`します。 このフラグが指定されていない場合は、内部的にドッキングするの代わりに、特定のウィンドウがフラグ ドッキング マネージャーです。  
  
##  <a name="canbetabbeddocument"></a>CBasePane::CanBeTabbedDocument  
 MDI タブ付きドキュメントに、ウィンドウを変換できるかどうかを指定します。  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウはタブ付きドキュメントに変換できる場合それ以外の場合、`FALSE`です。 `CBasePane::CanBeTabbedDocument` は常に `FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
 特定のオブジェクトのみ`CBasePane`-などの種類の派生、 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)、タブ付きドキュメントに変換できます。  
  
##  <a name="canfloat"></a>CBasePane::CanFloat  
 ペインをフローティングできるかどうかを決定します。  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインをフローティングできる場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、ペインをフローティングできるかどうかを判断するには、このメソッドを呼び出します。  
  
 構築時に、この機能を設定を渡すことによって、`AFX_CBRS_FLOAT`フラグを[CBasePane::CreateEx](#createex)します。  
  
> [!NOTE]
>  フレームワークは、フローティング ウィンドウが静的であると、ドッキング状態を変更できないことを想定します。 そのため、フレームワークでは、非フローティング ペインのドッキング状態は保存されません。  
  
 既定の実装、`AFX_CBRS_FLOAT`スタイル。  
  
##  <a name="canfocus"></a>CBasePane::CanFocus  
 ウィンドウがフォーカスを取得できるかどうかを指定します。  
  
```  
virtual BOOL CanFocus() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ウィンドウがフォーカスを受け取ることができます。それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 フォーカスを制御する派生クラスでこのメソッドをオーバーライドします。 たとえば、ツールバーがフォーカスを受け取ることはできませんのでこのメソッドが返されます。`FALSE`ツール バー オブジェクトで呼び出されます。  
  
 フレームワークは、ペインのドッキングまたはフローティング状態のときに入力フォーカスを設定しようとします。  
  
##  <a name="copystate"></a>CBasePane::CopyState  
 指定されたウィンドウの状態をコピーします。  
  
```  
virtual void CopyState(CBasePane* pOrgBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pOrgBar`  
 別のウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドからの状態をコピーする`pOrgBar`このペインにします。  
  
##  <a name="createdefaultminiframe"></a>CBasePane::CreateDefaultMiniframe  
 ペインをフローティングできる場合、このメソッドは、そのミニフレーム ウィンドウを作成します。  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectInitial`  
 ミニフレーム ウィンドウの最初の座標を指定します。  
  
### <a name="return-value"></a>戻り値  
 新しいミニフレーム ウィンドウへのポインターまたは`NULL`場合は、作成に失敗しました。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ペインがフローティング状態に切り替わるときに、このメソッドを呼び出します。 メソッドは、ミニフレーム ウィンドウを作成し、このウィンドウに、ウィンドウを結び付けます。  
  
 既定の実装では、`NULL` が返されます。  
  
##  <a name="createex"></a>CBasePane::CreateEx  
 ウィンドウ コントロールを作成します。  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle=0,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwStyleEx`  
 拡張スタイル (を参照してください[とき](../../mfc/reference/cwnd-class.md#createex)の詳細)。  
  
 [入力] `lpszClassName`  
 ウィンドウ クラスの名前。  
  
 [入力] `lpszWindowName`  
 ウィンドウの名前。  
  
 [入力] `dwStyle`  
 ウィンドウ スタイル (を参照してください[とき](../../mfc/reference/cwnd-class.md#createex))。  
  
 [入力] `rect`  
 初期の四角形。  
  
 [入力] `pParentWnd`  
 親ウィンドウへのポインター。  
  
 [入力] `nID`  
 ウィンドウの ID を指定します 一意である必要があります。  
  
 [入力] `dwControlBarStyle`  
 ウィンドウのスタイルのフラグ。  
  
 [入力] `pContext`  
 ポインター`CcreateContext`  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインが正常に作成された場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 クラスのウィンドウを作成`lpszClassName`します。 指定した場合`WS_CAPTION`、このメソッドは、クリア、`WS_CAPTION`スタイル ビットとセット`CBasePane::m_bHasCaption`に`TRUE`ライブラリでは、キャプションのあるウィンドウをサポートしていないため、します。  
  
 子ウィンドウのスタイルと MFC コントロール バー (cbrs _) スタイルの任意の組み合わせを使用することができます。  
  
 ライブラリは、ウィンドウの場合、いくつかの新しいスタイルを追加します。 次の表では、新しいスタイルについて説明します。  
  
|スタイル|説明|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|ペインをフローティングできます。|  
|`AFX_CBRS_AUTOHIDE`|ウィンドウは、自動非表示モードをサポートしています。|  
|`AFX_CBRS_RESIZE`|ウィンドウのサイズを変更できます。 **重要:**このスタイルが実装されていません。|  
|`AFX_CBRS_CLOSE`|ペインを閉じることができます。|  
|`AFX_CBRS_AUTO_ROLLUP`|フローティング状態の場合は、ペインのロールアップを作成することができます。|  
|`AFX_CBRS_REGULAR_TABS`|1 つのペインは、このスタイルを持つ別のウィンドウにドッキング、通常のタブ付きウィンドウが作成されます。 (詳細については、次を参照してください[派生クラス](../../mfc/reference/ctabbedpane-class.md)。)。|  
|`AFX_CBRS_OUTLOOK_TABS`|1 つのペインは、このスタイルを持つ別のウィンドウにドッキング、Outlook のようなタブ付きウィンドウが作成されます。 (詳細については、次を参照してください[があります](../../mfc/reference/cmfcoutlookbar-class.md)。)。|  
  
 新しいスタイルを使用するには、指定することで`dwControlBarStyle`します。  
  
##  <a name="dockpane"></a>CBasePane::DockPane  
 別のウィンドウまたはフレームのウィンドウ ペインをドッキングします。  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockBar`  
 別のウィンドウへのポインター。  
  
 [入力] `lpRect`  
 コピー先の四角形を指定します。  
  
 [入力] `dockMethod`  
 ドッキング方法を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`コントロール バーが正常にドッキングされている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 別のペインをドッキング バー ペインをドッキングするには、この関数を呼び出します ( [CDockSite クラス](../../mfc/reference/cdocksite-class.md)) で指定されている`pDockBar`、メイン フレームに切り替えたりする場合は`pDockBar`は`NULL`です。  
  
 `dockMethod`ウィンドウをドッキングする方法を指定します。 参照してください[CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane)使用可能な値の一覧にします。  
  
##  <a name="dockpaneusingrtti"></a>CBasePane::DockPaneUsingRTTI  
 実行時型情報を使用して、ウィンドウをドッキングします。  
  
```  
void DockPaneUsingRTTI(BOOL bUseDockSite);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bUseDockSite`  
 場合`TRUE`、ドッキング サイトにドッキングします。 場合`FALSE`親のフレームにドッキングします。  
  
##  <a name="docktoframewindow"></a>CBasePane::DockToFrameWindow  
 フレームにドッキング可能ペインをドッキングします。  
  
```  
virtual BOOL DockToFrameWindow(
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL,  
    DWORD dwDockFlags = DT_DOCK_LAST,  
    CBasePane* pRelativeBar = NULL,  
    int nRelativeIndex = -1,  
    BOOL bOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 ウィンドウをドッキングする親フレームの側です。  
  
 [入力] `lpRect`  
 目的のサイズ。  
  
 [入力] `dwDockFlags`  
 無視されます。  
  
 [入力] `pRelativeBar`  
 無視されます。  
  
 [入力] `nRelativeIndex`  
 無視されます。  
  
 [入力] `bOuterEdge`  
 場合`TRUE`で指定された横にあるその他のドッキング可能ペインが`dwAlignment`、他のウィンドウの外側のウィンドウがドッキングされている親フレームの端に近い場所にします。 場合`FALSE`ウィンドウがクライアント領域の中央に近いドッキングされています。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは失敗ペイン分割バー ( [CPaneDivider クラス](../../mfc/reference/cpanedivider-class.md)) を作成できません。 それ以外の場合、常に返します`TRUE`します。  
  
##  <a name="doesallowdyninsertbefore"></a>CBasePane::DoesAllowDynInsertBefore  
 このペインと親フレームの間の別のウィンドウを動的に挿入するかどうかを決定します。  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ユーザーが別のペインを挿入できる場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、ユーザーがこのペインの前にウィンドウを動的に挿入できるかどうかを判断するには、このメソッドを呼び出します。  
  
 たとえば、アプリケーションが (Outlook バー) など、フレームの左側にドッキングされているウィンドウを作成します。 ユーザーが、最初のウィンドウの左側に別のペインをドッキングをするを防ぐためにこのメソッドをオーバーライドし、返す`FALSE`します。  
  
 このメソッドをオーバーライドし、返すことをお勧め`FALSE`から派生した非フローティング ペインの[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)します。  
  
 既定の実装では、`TRUE` が返されます。  
  
##  <a name="dopaint"></a>CBasePane::DoPaint  
 ペインの背景を設定します。  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、背景の塗りつぶしに現在のビジュアル マネージャーを呼び出します ( [CMFCVisualManager::OnFillBarBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillbarbackground))。  
  
##  <a name="enabledocking"></a>CBasePane::EnableDocking  
 メイン フレーム ウィンドウのドッキングを有効にします。  
  
```  
virtual void EnableDocking(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 有効にするドッキングの配置を指定します。  
  
### <a name="remarks"></a>コメント  
 メイン フレームにドッキングの配置を有効にするには、このメソッドを呼び出します。 組み合わせを渡すことができます`CBRS_ALIGN_`フラグ (詳細については、次を参照してください。 [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking))。  
  
 `EnableDocking`内部フラグを設定`CBasePane::m_dwEnabledAlignment`し、フレームワークは、ウィンドウがドッキングされているときにこのフラグを確認します。  
  
 呼び出す[CBasePane::GetEnabledAlignment](#getenabledalignment)ペインのドッキング位置を決定します。  
  
##  <a name="enablegripper"></a>CBasePane::EnableGripper  
 有効またはグリッパーを無効にします。 グリッパーが有効になっている場合、ユーザーは、ウィンドウの位置を変更することをドラッグできます。  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`グリッパー; を有効にするには`FALSE`を無効にします。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、このメソッドを使用して、使用する代わりに、変更グリップを有効にする、`WS_CAPTION`スタイル。  
  
##  <a name="floatpane"></a>CBasePane::FloatPane  
 ペインをフローティング状態です。  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod=DM_UNKNOWN,  
    bool bShow=true);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectFloat`  
 浮動ペインが表示される画面座標を指定します。  
  
 [入力] `dockMethod`  
 使用してペインをフローティングするドッキング方法を指定します。  
  
 [入力] `bShow`  
 浮動ペインが表示されているかどうかを指定します ( `TRUE`) または非表示 ( `FALSE`)。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウが正常にフローティング状態の場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 指定した画面位置にあるペインをフローティングするには、このメソッドを呼び出す`rectFloat`します。  
  
##  <a name="get_acchelptopic"></a>CBasePane::get_accHelpTopic  
 フレームワークの完全なパスを取得するには、このメソッドを呼び出して、`WinHelp`指定したオブジェクトとそのファイルに適切なトピックの識別子に関連付けられているファイル。  
  
```  
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,  
    VARIANT varChild,  
    long* pidTopic);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pszHelpFile`  
 アドレス、`BSTR`の完全なパスを受け取る、`WinHelp`存在する場合に指定したオブジェクトに関連付けられているファイル。  
  
 [入力] `varChild`  
 ヘルプ トピックを取得するが、オブジェクトまたはオブジェクトの子要素の&1; つのかどうかを指定します。 このパラメーターには、いずれかを指定できます`CHILDID_SELF`(オブジェクトのヘルプ トピックを取得) するか、子の ID (する場合、オブジェクトの要素の子のいずれかのヘルプ トピックを取得)。  
  
 [入力] `pidTopic`  
 識別、`Help`指定したオブジェクトに関連付けられているファイルのトピックです。  
  
### <a name="return-value"></a>戻り値  
 `CBasePane`このメソッドは実装しません。 したがって、`CBasePane::get_accHelpTopic`は常に返します`S_FALSE`します。  
  
### <a name="remarks"></a>コメント  
 この関数は、MFC での Active Accessibility のサポートの一部です。 オブジェクトに関するヘルプ情報を提供する派生クラスでオーバーライドします。  
  
##  <a name="get_accselection"></a>CBasePane::get_accSelection  
 フレームワークでは、このオブジェクトの選択された子を取得するには、このメソッドを呼び出します。  
  
```  
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pvarChildren`  
 選択された子を識別する情報を受け取ります。  
  
### <a name="return-value"></a>戻り値  
 `CBasePane`このメソッドは実装しません。 `pvarChildren` が `NULL` の場合、このメソッドは `E_INVALIDARG` を返します。 それ以外の場合、このメソッドが戻る`DISP_E_MEMBERNOTFOUND`します。  
  
### <a name="remarks"></a>コメント  
 この関数は、MFC での Active Accessibility のサポートの一部です。 ウィンドウなしの ActiveX コントロール以外のウィンドウを持つユーザー インターフェイス要素がある場合は、派生クラスでは、この関数をオーバーライドします。  
  
##  <a name="getcaptionheight"></a>CBasePane::GetCaptionHeight  
 キャプションの高さを返します。  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 キャプションの高さ。  
  
##  <a name="getcontrolbarstyle"></a>CBasePane::GetControlBarStyle  
 コントロール バーのスタイルを返します。  
  
```  
virtual DWORD GetControlBarStyle() const 
```  
  
### <a name="return-value"></a>戻り値  
 Afx_cbrs _ フラグのビットごとの OR の組み合わせ。  
  
### <a name="remarks"></a>コメント  
 戻り値では、次の値の組み合わせです。  
  
|スタイル|説明|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|コントロール バーの float 型を使用できます。|  
|`AFX_CBRS_AUTOHIDE`|により自動的に隠すモード。|  
|`AFX_CBRS_RESIZE`|コントロール バーのサイズを変更できるようにします。 このフラグが設定されている場合は、ドッキング可能なウィンドウで、コントロール バーを配置できます。|  
|`AFX_CBRS_CLOSE`|コントロール バーの非表示を有効にします。|  
  
##  <a name="getcurrentalignment"></a>CBasePane::GetCurrentAlignment  
 現在のウィンドウの配置を返します。  
  
```  
virtual DWORD GetCurrentAlignment() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロール バーの現在の配置。 次の表は、使用可能な値を示します。  
  
|値|アラインメント|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|左揃え。|  
|`CBRS_ALIGN_RIGHT`|右揃え。|  
|`CBRS_ALIGN_TOP`|上揃え。|  
|`CBRS_ALIGN_BOTTOM`|下揃え。|  
  
##  <a name="getdockingmode"></a>CBasePane::GetDockingMode  
 現在のドッキング ペインのモードを返します。  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 DT_STANDARD、ウィンドウをドラッグする場合は、画面にドラッグ四角形によって示されます。 DT_IMMEDIATE ペインの内容をドラッグした場合。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、ウィンドウの現在のドッキング モードを確認するには、このメソッドを呼び出します。  
  
 場合`CBasePane::m_dockMode`が未定義のドッキング モードは、グローバル ドッキング モードから取得 (DT_UNDEFINED) ( `AFX_GLOBAL_DATA::m_dockModeGlobal`)。  
  
 設定して`m_dockMode`したり上書きしたりする`GetDockingMode`各ウィンドウのドッキング モードを制御することができます。  
  
##  <a name="getdocksiteframewnd"></a>CBasePane::GetDockSiteFrameWnd  
 ポインターを返す、 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)ウィンドウがドッキングされているオブジェクト。  
  
```  
virtual CWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウのドッキング サイトへのポインター。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのドッキング サイトへのポインターを取得するには、このメソッドを呼び出します。 ドッキング サイトには、ウィンドウがフローティング状態の場合、ウィンドウがメイン フレームにドッキングされている場合は、メイン フレーム ウィンドウまたはミニフレーム ウィンドウのいずれかをすることができます。  
  
##  <a name="getenabledalignment"></a>CBasePane::GetEnabledAlignment  
 ウィンドウに適用される cbrs_align _ スタイルを返します。  
  
```  
virtual DWORD GetEnabledAlignment() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Cbrs_align _ スタイルの組み合わせ。 次の表は、有効なスタイルを示しています。  
  
|フラグ|有効な配置|  
|----------|-----------------------|  
|`CBRS_ALIGN_LEFT`|左。|  
|`CBRS_ALIGN_RIGHT`|そうです。|  
|`CBRS_ALIGN_TOP`|ページのトップへ。|  
|`CBRS_ALIGN_BOTTOM`|下部にあります。|  
|`CBRS_ALIGN_ANY`|すべてのフラグの組み合わせ。|  
  
### <a name="remarks"></a>コメント  
 ウィンドウの有効な配置を決定するには、このメソッドを呼び出します。 有効な配置では、ペインをドッキングするメイン フレーム ウィンドウの辺を意味します。  
  
 使用して、ドッキング配置を有効にする[CBasePane::EnableDocking](#enabledocking)します。  
  
##  <a name="getmfcstyle"></a>CBasePane::GetMFCStyle  
 MFC に固有のペインのスタイルを返します。  
  
```  
virtual DWORD GetMFCStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 特定のライブラリ (afx_cbrs _) ペインのスタイルの組み合わせ。  
  
##  <a name="getpaneicon"></a>CBasePane::GetPaneIcon  
 ペインのアイコンのハンドルを返します。  
  
```  
virtual HICON GetPaneIcon(BOOL bBigIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bBigIcon`  
 場合に、32 ピクセルのアイコンで 32 のピクセルを指定`TRUE`; 場合は、16 ピクセルのアイコンで 16 ピクセルを指定`FALSE`します。  
  
### <a name="return-value"></a>戻り値  
 ペインのアイコンへのハンドル。 失敗した場合、返します`NULL`します。  
  
### <a name="remarks"></a>コメント  
 既定の実装[CWnd::GetIcon](../../mfc/reference/cwnd-class.md#geticon)します。  
  
##  <a name="getpanerow"></a>CBasePane::GetPaneRow  
 ポインターを返す、 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)ウィンドウがドッキングされているオブジェクト。  
  
```  
CDockingPanesRow* GetPaneRow();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター `CDockingPanesRow` 、ウィンドウがドッキングされている場合、または`NULL`がフローティング状態の場合。  
  
### <a name="remarks"></a>コメント  
 ウィンドウがドッキングされている行にアクセスするには、このメソッドを呼び出します。 たとえば、特定の行でウィンドウを配置するを呼び出す`GetPaneRow`し、呼び出す[CDockingPanesRow::ArrangePanes](../../mfc/reference/cdockingpanesrow-class.md#arrangepanes)します。  
  
##  <a name="getpanestyle"></a>CBasePane::GetPaneStyle  
 ウィンドウ スタイルを返します。  
  
```  
virtual DWORD GetPaneStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロール バーのスタイル (cbrs _ スタイルを含む) で設定されたの組み合わせ、 [CBasePane::SetPaneStyle](#setpanestyle)メソッドの作成時にします。  
  
##  <a name="getparentdocksite"></a>CBasePane::GetParentDockSite  
 親ドッキング サイトへのポインターを返します。  
  
```  
virtual CDockSite* GetParentDockSite() const;  
```  
  
### <a name="return-value"></a>戻り値  
 親ドッキング サイトです。  
  
##  <a name="getparentminiframe"></a>CBasePane::GetParentMiniFrame  
 親ミニフレーム ウィンドウへのポインターを返します。  
  
```  
virtual CPaneFrameWnd* GetParentMiniFrame(BOOL bNoAssert=FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bNoAssert`  
 場合`TRUE`、このメソッドは無効なポインターをチェックしません。 アプリケーションの終了時にこのメソッドを呼び出す場合は、このパラメーターを設定`TRUE`です。  
  
### <a name="return-value"></a>戻り値  
 親ミニフレーム ウィンドウのウィンドウが固定されていない場合に有効なポインターそれ以外の場合`NULL`します。  
  
### <a name="remarks"></a>コメント  
 この関数では、親ミニフレーム ウィンドウへのポインターを取得します。 このメソッドは、すべての親を反復処理しから派生したオブジェクトのチェックを[CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)します。  
  
 使用`GetParentMiniFrame`ペインがフローティング状態かどうかを決定します。  
  
##  <a name="getparenttabbedpane"></a>CBasePane::GetParentTabbedPane  
 親のタブ付きペインへのポインターを返します。  
  
```  
CBaseTabbedPane* GetParentTabbedPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 存在する場合は、親のタブ付きペインへのポインターそれ以外の場合`NULL`します。  
  
##  <a name="getparenttabwnd"></a>CBasePane::GetParentTabWnd  
 タブ内にある親ウィンドウへのポインターを返します。  
  
```  
CMFCBaseTabCtrl* GetParentTabWnd(HWND& hWndTab) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `hWndTab`  
 戻り値がない場合`NULL`、このパラメーターには、親のタブ付きウィンドウへのハンドルが含まれています。  
  
### <a name="return-value"></a>戻り値  
 タブ付きウィンドウの親への有効なポインターまたは`NULL`です。  
  
### <a name="remarks"></a>コメント  
 この関数を使用すると、親のタブ付きウィンドウへのポインターを取得できます。 不十分ですを呼び出す`GetParent`ウィンドウがドッキング ラッパー内であるため、( [CDockablePaneAdapter クラス](../../mfc/reference/cdockablepaneadapter-class.md)) またはペイン アダプターの内部 ( [CDockablePaneAdapter クラス](../../mfc/reference/cdockablepaneadapter-class.md))。 使用して`GetParentTabWnd`(親はタブ付きウィンドウであると仮定して) このような場合、有効なポインターを取得することができます。  
  
##  <a name="getrecentvisiblestate"></a>CBasePane::GetRecentVisibleState  
 フレームワークは、ペインがアーカイブから復元された場合、このメソッドを呼び出します。  
  
```  
virtual BOOL GetRecentVisibleState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`BOOL`最近使用した表示状態を指定します。 場合`TRUE`ペインが表示される場合に、シリアル化され、復元するときに表示する必要があります。 場合`FALSE`、シリアル化し、復元するときに非表示にすると、ウィンドウが非表示にします。  
  
##  <a name="hideinprintpreviewmode"></a>CBasePane::HideInPrintPreviewMode  
 印刷プレビューで、ウィンドウが非表示かどうかを指定します。  
  
```  
virtual BOOL HideInPrintPreviewMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`印刷プレビューでは、ウィンドウが表示されない場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 印刷プレビューでは、基本のペインは表示されません。 そのため、このメソッドは常`TRUE`します。  
  
##  <a name="insertpane"></a>CBasePane::InsertPane  
 指定したウィンドウをドッキング マネージャーに登録します。  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
 挿入するペインへのポインター。  
  
 [入力] `pTarget`  
 隣接するペインへのポインター。  
  
 [入力] `bAfter`  
 場合`TRUE`、`pControlBar`後に挿入`pTarget`します。 場合`FALSE`、`pControlBar`前に挿入`pTarget`します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功すると、`FALSE`それ以外の場合。  
  
##  <a name="isaccessibilitycompatible"></a>CBasePane::IsAccessibilityCompatible  
 ペインがアクティブなユーザー補助をサポートするかどうかを指定します。  
  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウは、Active Accessibility; をサポートしている場合それ以外の場合、`FALSE`です。  
  
##  <a name="isautohidemode"></a>CBasePane::IsAutoHideMode  
 ペインが自動非表示モードになっているかどうかを判断します。  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウが自動非表示モードである場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 基本ペインできない自動的に隠す。 このメソッドは常に `FALSE` を返します。  
  
##  <a name="isdialogcontrol"></a>CBasePane::IsDialogControl  
 ウィンドウがダイアログ ボックス コントロールであるかどうかを指定します。  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウがダイアログ ボックス コントロールである場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、このメソッドを使用して、すべてのペインのレイアウトの一貫性を保証します。  
  
##  <a name="isdocked"></a>CBasePane::IsDocked  
 ウィンドウがドッキングされているかどうかを決定します。  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウの親がミニ フレームではない場合、またはミニフレームで別のペインで、ウィンドウがフローティング状態の場合それ以外の場合、`FALSE`です。  
  
##  <a name="isfloating"></a>CBasePane::IsFloating  
 ペインをフローティングするかどうかを決定します。  
  
```  
virtual BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインが固定されていない場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドの逆の値を返します[CBasePane::IsDocked](#isdocked)します。  
  
##  <a name="ishorizontal"></a>CBasePane::IsHorizontal  
 ウィンドウが水平方向にドッキングされているかどうかを決定します。  
  
```  
virtual BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウが水平方向にドッキングされている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 既定の実装で、チェックの現在のドッキング配置`CBRS_ORIENT_HORZ`します。  
  
##  <a name="isinfloatingmultipaneframewnd"></a>CBasePane::IsInFloatingMultiPaneFrameWnd  
 ウィンドウが複数ペインのフレーム ウィンドウかどうかを指定 ( [CMultiPaneFrameWnd クラス](../../mfc/reference/cmultipaneframewnd-class.md))。  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`複数ペインのフレーム ウィンドウには、ペインは場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 複数ペインのフレーム ウィンドウのドッキング可能なウィンドウだけができます。 したがって、`CBasePane::IsInFloatingMultiPaneFrameWnd`は常に返します`FALSE`します。  
  
##  <a name="ismditabbed"></a>CBasePane::IsMDITabbed  
 タブ付きドキュメントとしての MDI 子ウィンドウに、ウィンドウが追加されているかどうかを決定します。  
  
```  
virtual BOOL IsMDITabbed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`タブ付きドキュメントとして、ウィンドウが MDI 子ウィンドウに追加した場合それ以外の場合、`FALSE`です。  
  
##  <a name="ispanevisible"></a>CBasePane::IsPaneVisible  
 指定するかどうか、`WS_VISIBLE`のウィンドウでフラグを設定します。  
  
```  
BOOL IsPaneVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合`WS_VISIBLE`が設定されているそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 使用[CBasePane::IsVisible](#isvisible)をウィンドウの可視性を判断します。  
  
##  <a name="ispointneardocksite"></a>CBasePane::IsPointNearDockSite  
 指定した点がドッキング サイトの近くにいるかどうかを判断します。  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 指定した点です。  
  
 [出力] `dwBarAlignment`  
 どちらの端点が近いを指定します。 指定できる値は`CBRS_ALIGN_LEFT`、 `CBRS_ALIGN_RIGHT`、`CBRS_ALIGN_TOP`と`CBRS_ALIGN_BOTTOM`  
  
 [出力] `bOuterEdge`  
 `TRUE`ドッキング サイトの外側の境界線の近くのポイントがある場合`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング サイトの近くのポイントがある場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 ポイントは、ドッキング マネージャーで設定された感度内にある場合に、ドッキング サイトの近くです。 既定値と小文字の区別は、15 ピクセルです。  
  
##  <a name="isresizable"></a>CBasePane::IsResizable  
 ウィンドウのサイズを変更できるかどうかを決定します。  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ユーザーが、ウィンドウのサイズを変更できる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ウィンドウの[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)サイズを変更できます。  
  
 ステータス バー ( [CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)) とドッキング バー ( [CDockSite クラス](../../mfc/reference/cdocksite-class.md)) サイズを変更できません。  
  
##  <a name="isrestoredfromregistry"></a>CBasePane::IsRestoredFromRegistry  
 ペインがレジストリから復元されるかどうかを決定します。  
  
```  
virtual BOOL IsRestoredFromRegistry() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインがレジストリから復元される場合それ以外の場合、`FALSE`です。  
  
##  <a name="istabbed"></a>CBasePane::IsTabbed  
 タブ付きウィンドウのタブ コントロールに、ウィンドウが挿入されたかどうかを決定します。  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`タブ付きウィンドウのタブで、コントロール バーが挿入される場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、直接の親へのポインターを取得し、かどうかを親のランタイム クラス[CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)します。  
  
##  <a name="isvisible"></a>CBasePane::IsVisible  
 ウィンドウが表示されているかどうかを決定します。  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウが表示されている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 ペインの表示を指定するのにには、このメソッドを使用します。 `::IsWindowVisible` は使用しないでください。  
  
 ウィンドウがタブ付きいない場合 (を参照してください[CBasePane::IsTabbed](#istabbed))、このメソッドはのチェック、`WS_VISIBLE`スタイル。 場合は、ウィンドウのタブは、このメソッドは、親のタブ付きウィンドウの可視性をチェックします。 親ウィンドウが表示されている場合、関数はウィンドウ タブを使用して、可視性をチェック[CMFCBaseTabCtrl::IsTabVisible](../../mfc/reference/cmfcbasetabctrl-class.md#istabvisible)します。  
  
##  <a name="loadstate"></a>CBasePane::LoadState  
 レジストリからペインの状態を読み込みます。  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 プロファイルの名前。  
  
 [入力] `nIndex`  
 プロファイルのインデックス。  
  
 [入力] `uiID`  
 ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインの状態が正常に読み込まれている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、レジストリからペインの状態を読み込むには、このメソッドを呼び出します。 保存して他の情報をロードする派生クラスでオーバーライド[CBasePane::SaveState](#savestate)します。  
  
##  <a name="movewindow"></a>CBasePane::MoveWindow  
 ウィンドウに移動します。  
  
```  
virtual HDWP MoveWindow(
    CRect& rect,  
    BOOL bRepaint = TRUE,  
    HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 新しい場所と、ウィンドウのサイズを指定する四角形。  
  
 [入力] `bRepaint`  
 場合`TRUE`ペインが再描画します。 場合`FALSE`ペインが再描画されません。  
  
 [入力] `hdwp`  
 遅延のウィンドウの位置の構造体へのハンドルします。  
  
### <a name="return-value"></a>戻り値  
 遅延のウィンドウの位置の構造体へのハンドルまたは`NULL`です。  
  
### <a name="remarks"></a>コメント  
 渡した場合`NULL`として、`hdwp`パラメーター、このメソッドは通常ウィンドウを移動します。 ハンドルを渡す場合、このメソッドは遅延するウィンドウの移動を実行します。 呼び出すために、ハンドルを取得できます[BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672)またはこのメソッドを前回呼び出したときの戻り値を格納することで。  
  
##  <a name="onafterchangeparent"></a>CBasePane::OnAfterChangeParent  
 ウィンドウの親の変更された後、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndOldParent`  
 以前の親へのポインター。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ペインの親が変わった場合、通常、ドッキングまたはフローティング操作後に、このメソッドを呼び出します。  
  
 既定の実装では、何も行われません。  
  
##  <a name="onbeforechangeparent"></a>CBasePane::OnBeforeChangeParent  
 ウィンドウは、親ウィンドウを変更する前に、フレームワークによって呼び出されます。  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndNewParent`  
 新しい親ウィンドウへのポインター。  
  
 [入力] `bDelay`  
 レイアウトの調整を遅延する必要があるかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 通常、ドッキング、フローティング、または自動非表示の操作のため、フレームワークは、ウィンドウの親の変更の直前にこのメソッドを呼び出します。  
  
 既定の実装では、何も行われません。  
  
##  <a name="ondrawcaption"></a>CBasePane::OnDrawCaption  
 フレームワークは、キャプションが描画されるときに、このメソッドを呼び出します。  
  
```  
virtual void OnDrawCaption();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドの機能を持たない、`CBasePane`クラスです。  
  
##  <a name="onmovepanedivider"></a>CBasePane::OnMovePaneDivider  
 このメソッドは現在使用されていません。  
  
```  
virtual void OnMovePaneDivider(CPaneDivider*);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `CPaneDivider*`  
 使用しません。  
  
##  <a name="onpanecontextmenu"></a>CBasePane::OnPaneContextMenu  
 ウィンドウのリストを持つメニューを作成するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnPaneContextMenu(
    CWnd* pParentFrame,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentFrame`  
 親のフレームへのポインター。  
  
 [入力] `point`  
 ショートカット メニューの場所を指定します。  
  
### <a name="remarks"></a>コメント  
 `OnPaneContextMenu`ドッキングのマネージャーは、現在のフレーム ウィンドウに属するペインのリストを保持を呼び出します。 このメソッドは、ショートカット メニューにペインの名前を追加し、それを表示します。 メニューのコマンドは、表示または個別のペインを非表示にします。  
  
 この動作をカスタマイズするには、このメソッドをオーバーライドします。  
  
##  <a name="onremovefromminiframe"></a>CBasePane::OnRemoveFromMiniFrame  
 親ミニフレーム ウィンドウから、ウィンドウが削除されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnRemoveFromMiniFrame(CPaneFrameWnd* pMiniFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMiniFrame`  
 ウィンドウを削除するミニフレーム ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、親ミニフレーム ウィンドウ (結果としてドッキングなど) から、ウィンドウが削除されたときに、このメソッドを呼び出します。  
  
 既定の実装では、何も行われません。  
  
##  <a name="onsetaccdata"></a>CBasePane::OnSetAccData  
 `CBasePane`このメソッドは使用されません。  
  
```  
virtual BOOL OnSetAccData(long lVal);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lVal`  
 使用しません。  
  
### <a name="return-value"></a>戻り値  
 このメソッドは常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="panefrompoint"></a>CBasePane::PaneFromPoint  
 指定したポイントを含むペインを返します。  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 確認の画面座標で、ポイントを指定します。  
  
 [入力] `nSensitivity`  
 この金額には、検索領域を拡大します。 指定したポイントが拡大された領域で該当する場合、ペインは、検索条件を満たします。  
  
 [入力] `bExactBar`  
 `TRUE`無視する、`nSensitivity`パラメーター。 そうしないと、`FALSE`です。  
  
 [入力] `pRTCBarType`  
 ない場合`NULL`、指定した型のペインだけを検索します。  
  
### <a name="return-value"></a>戻り値  
 `CBasePane`-指定したポイントを格納しているオブジェクトを派生または`NULL`ウィンドウが検出されなかった場合。  
  
##  <a name="recalclayout"></a>CBasePane::RecalcLayout  
 `CBasePane`このメソッドは使用されません。  
  
```  
virtual void RecalcLayout();
```  
  
##  <a name="removepanefromdockmanager"></a>CBasePane::RemovePaneFromDockManager  
 ペインの登録を解除し、ドッキング マネージャーの一覧から削除されます。  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pBar,  
    BOOL bDestroy = TRUE,  
    BOOL bAdjustLayout = FALSE,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 削除するペインへのポインター。  
  
 [入力] `bDestroy`  
 場合`TRUE`、削除されたウィンドウを破棄します。  
  
 [入力] `bAdjustLayout`  
 場合`TRUE`、すぐにドッキング レイアウトを調整します。  
  
 [入力] `bAutoHide`  
 場合`TRUE`、ドッキング レイアウトが自動的に隠す バーのリストに関連しています。 場合`FALSE`、ドッキング レイアウトが標準のペインのリストに関連します。  
  
 [入力] `pBarReplacement`  
 削除されるペインに置き換えられるペインへのポインター。  
  
##  <a name="savestate"></a>CBasePane::SaveState  
 レジストリにペインの状態を保存します。  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 プロファイルの名前。  
  
 [入力] `nIndex`  
 プロファイルのインデックス。  
  
 [入力] `uiID`  
 ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`状態が正常に保存されている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ペインの状態をレジストリに保存するときに、このメソッドを呼び出します。 オーバーライド`SaveState`追加情報を格納する派生クラスでします。  
  
##  <a name="selectdefaultfont"></a>CBasePane::SelectDefaultFont  
 指定したデバイス コンテキストの既定のフォントを選択します。  
  
```  
CFont* SelectDefaultFont(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキスト。  
  
### <a name="return-value"></a>戻り値  
 既定値へのポインター [CFont クラス](../../mfc/reference/cfont-class.md)オブジェクトです。  
  
##  <a name="setcontrolbarstyle"></a>CBasePane::SetControlBarStyle  
 コントロール バーのスタイルを設定します。  
  
```  
virtual void SetControlBarStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwNewStyle`  
 次の値のビットごとの OR の組み合わせ。  
  
|スタイル|説明|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|コントロール バーの float 型を使用できます。|  
|`AFX_CBRS_AUTOHIDE`|により自動的に隠すモード。|  
|`AFX_CBRS_RESIZE`|コントロール バーのサイズを変更できるようにします。 このフラグが設定されている場合は、ドッキング可能なウィンドウで、コントロール バーを配置できます。|  
|`AFX_CBRS_CLOSE`|コントロール バーの非表示を有効にします。|  
  
##  <a name="setdockingmode"></a>CBasePane::SetDockingMode  
 ペインのドッキング モードを設定します。  
  
```  
void SetDockingMode(AFX_DOCK_TYPE dockModeNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dockModeNew`  
 ペインの新しいドッキング モードを指定します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、2 つのドッキング モードをサポートしています。 標準と即時します。  
  
 標準ドッキング モードでは、ドラッグ四角形を使用するウィンドウおよびミニフレーム ウィンドウが移動します。 即時ドッキング モードでのコントロール バーおよびミニフレーム ウィンドウと共に移動するすぐに、コンテキスト。  
  
 最初に、ドッキング モードが定義されている世界[CDockingManager::m_dockModeGlobal](../../mfc/reference/cdockingmanager-class.md#m_dockmodeglobal)します。 使って個別に各ウィンドウのドッキング モードを設定することができます、`SetDockingMode`メソッドです。  
  
##  <a name="setpanealignment"></a>CBasePane::SetPaneAlignment  
 ペインの配置を設定します。  
  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 新しい配置を指定します。  
  
### <a name="remarks"></a>コメント  
 通常、フレームワークは、別のメインフレームの一方の側から、ウィンドウがドッキングされているとき、このメソッドを呼び出します。  
  
 次の表に、可能な値`dwAlignment`:  
  
|値|アラインメント|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|左揃え。|  
|`CBRS_ALIGN_RIGHT`|右揃え。|  
|`CBRS_ALIGN_TOP`|上揃え。|  
|`CBRS_ALIGN_BOTTOM`|下揃え。|  
  
##  <a name="setpanestyle"></a>CBasePane::SetPaneStyle  
 ウィンドウのスタイルを設定します。  
  
```  
virtual void SetPaneStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwNewStyle`  
 設定する新しいスタイルを指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、afxres.h 内で定義されている cbrs _ スタイルのいずれかの設定を使用できます。 ウィンドウのスタイルとペインの配置は一緒に保存されるので、次のように、現在の配置と組み合わせることにより、新しいスタイルを設定します。  
  
 `pPane->SetPaneStyle (pPane->GetCurrentAlignment() | CBRS_TOOLTIPS);`  
  
##  <a name="setwindowpos"></a>CBasePane::SetWindowPos  
 サイズ、位置、およびウィンドウの Z オーダーを変更します。  
  
```  
virtual HDWP SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags,  
    HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndInsertAfter`  
 識別、`CWnd`これよりも前にオブジェクト`CWnd`Z オーダー内のオブジェクト。 詳細については、次を参照してください。 [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)します。  
  
 [入力] `x`  
 ウィンドウの左側の位置を指定します。  
  
 [入力] `y`  
 ウィンドウの上端の位置を指定します。  
  
 [入力] `cx`  
 ウィンドウの幅を指定します。  
  
 [入力] `cy`  
 ウィンドウの高さを指定します。  
  
 [入力] `nFlags`  
 サイズと位置のオプションを指定します。 詳細については、次を参照してください。 [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)します。  
  
 [入力] `hdwp`  
 1 つまたは複数のウィンドウのサイズと位置情報を格納する構造体へのハンドルします。  
  
### <a name="return-value"></a>戻り値  
 更新された遅延ウィンドウ位置構造体へのハンドルまたは`NULL`です。  
  
### <a name="remarks"></a>コメント  
 場合`pWndInsertAfter`は`NULL`、このメソッドを呼び出す[CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)します。 場合`pWndInsertAfter`以外は、 `NULL`、このメソッドを呼び出す`DeferWindowPos`します。  
  
##  <a name="showpane"></a>CBasePane::ShowPane  
 ウィンドウの表示と非表示を切り替えます。  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
 表示するかどうかを指定します ( `TRUE`) の表示と非 ( `FALSE`) ペインです。  
  
 [入力] `bDelay`  
 場合`TRUE`、ドッキング レイアウトを再計算が遅延します。  
  
 [入力] `bActivate`  
 場合`TRUE`、ウィンドウが表示されているときにアクティブです。  
  
### <a name="remarks"></a>コメント  
 このメソッド ペインの表示と非表示を切り替えます。 代わりにこのメソッドを使用して`ShowWindow`のため、このメソッドに関連するドッキング マネージャー ウィンドウの表示/非表示の変更について通知します。  
  
 使用[CBasePane::IsVisible](#isvisible)をウィンドウの現在の可視性を判断します。  
  
##  <a name="stretchpane"></a>CBasePane::StretchPane  
 垂直または水平方向にウィンドウを拡大します。  
  
```  
virtual CSize StretchPane(
    int nLength,  
    BOOL bVert);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nLength`  
 ペインを引き伸ばす長さです。  
  
 [入力] `bVert`  
 場合`TRUE`、垂直方向にウィンドウを拡大します。 場合`FALSE`ウィンドウを水平方向に拡大します。  
  
### <a name="return-value"></a>戻り値  
 拡大されたウィンドウのサイズ。  
  
##  <a name="undockpane"></a>CBasePane::UndockPane  
 ドッキング サイト、既定のスライダーまたはミニフレーム ウィンドウの現在のドッキング位置から、ウィンドウを削除します。  
  
```  
virtual void UndockPane(BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bDelay`  
 TRUE の場合、ドッキング レイアウトはすぐに再計算されません。  
  
### <a name="remarks"></a>コメント  
 ウィンドウの状態を操作またはドッキング レイアウトから、ウィンドウを除外するには、このメソッドを呼び出します。  
  
 引き続きこのペインを使用する場合は、いずれかを呼び出す[CBasePane::DockPane](#dockpane)または[CBasePane::FloatPane](#floatpane)このメソッドを呼び出す前にします。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)

