---
title: "CMDIChildWndEx クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx::ActivateTopLevelFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AdjustDockingLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnMDITabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnTaskBarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnWindowsList
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPaneLeftOf
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableAutoHidePanes
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableDocking
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDockingManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDocumentName
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameIcon
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameText
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabProxyWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarPreviewWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetToolbarButtonToolTipText
- AFXMDICHILDWNDEX/CMDIChildWndEx::InsertPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::InvalidateIconicBitmaps
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsPointNearDockSite
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsReadOnly
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsRegisteredWithTaskbarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarTabsSupportEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicLivePreviewBitmap
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicThumbnail
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnMoveMiniFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnSetPreviewMode
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailStretch
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnUpdateFrameTitle
- AFXMDICHILDWNDEX/CMDIChildWndEx::PaneFromPoint
- AFXMDICHILDWNDEX/CMDIChildWndEx::RecalcLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::RegisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::RemovePaneFromDockManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabActive
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabOrder
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabProperties
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::ShowPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::UnregisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::UpdateTaskbarTabIcon
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWndEx class
- ActivateFrame method
- PreTranslateMessage method
- GetThisClass method
- CreateObject method
ms.assetid: d39fec06-0bd6-4271-917d-35aae3b24d8e
caps.latest.revision: 35
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 016de8fdade75376f9f081539c0f160a6502bc37
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmdichildwndex-class"></a>CMDIChildWndEx クラス
`CMDIChildWndEx`マルチ ドキュメント インターフェイス (MDI) 子ウィンドウに、Windows の機能を提供するクラス。 機能を拡張[CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)します。 ある特定の MFC クラスを MDI アプリケーションで使用するときは、フレームワークにこのクラスが必要です。  
  
## <a name="syntax"></a>構文  
  
```  
class CMDIChildWndEx : public CMDIChildWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMDIChildWndEx::ActivateTopLevelFrame](#activatetoplevelframe)|タスク バー タブから、アプリケーションをアクティブ化するときに、トップ レベルのフレームをアクティブ化するために、フレームワークによって内部的に呼び出されます。|  
|`CMDIChildWndEx::AddDockSite`|このメソッドを実装または使用されていないします。|  
|[CMDIChildWndEx::AddPane](#addpane)|ペインを追加します。|  
|[CMDIChildWndEx::AddTabbedPane](#addtabbedpane)|タブ付きペインを追加します。|  
|[CMDIChildWndEx::AdjustDockingLayout](#adjustdockinglayout)|ドッキング レイアウトを調整します。|  
|[CMDIChildWndEx::CanShowOnMDITabs](#canshowonmditabs)||  
|[CMDIChildWndEx::CanShowOnTaskBarTabs](#canshowontaskbartabs)|Windows 7 タスク バーのタブにこの MDI 子フォームを表示するかどうかをフレームワークに指示します。|  
|[CMDIChildWndEx::CanShowOnWindowsList](#canshowonwindowslist)|返します。`TRUE`に MDI 子ウィンドウの名前を表示できる場合は、 [CMFCWindowsManagerDialog クラス](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) ダイアログ ボックス。 それ以外の場合は、`FALSE` を返します。|  
|`CMDIChildWndEx::CreateObject`|このクラス型の動的インスタンスを作成するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::DockPane](#dockpane)|ペインをドッキングします。|  
|[CMDIChildWndEx::DockPaneLeftOf](#dockpaneleftof)|ウィンドウを別のウィンドウの左側にドッキングします。|  
|[CMDIChildWndEx::EnableAutoHidePanes](#enableautohidepanes)|により自動的に隠すモードのペインのウィンドウの指定した辺にドッキングされている場合。|  
|[CMDIChildWndEx::EnableDocking](#enabledocking)|メインフレームへの子ウィンドウのドッキングを有効にします。|  
|[CMDIChildWndEx::EnableTaskbarThumbnailClipRect](#enabletaskbarthumbnailcliprect)|有効またはウィンドウのクライアント領域の一部の自動選択を無効にします。|  
|[CMDIChildWndEx::GetDockingManager](#getdockingmanager)||  
|[CMDIChildWndEx::GetDocumentName](#getdocumentname)|MDI 子ウィンドウに表示されているドキュメントの名前を返します。|  
|[CMDIChildWndEx::GetFrameIcon](#getframeicon)|MDI 子ウィンドウ アイコンを取得するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::GetFrameText](#getframetext)|MDI 子ウィンドウのテキストを取得するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::GetPane](#getpane)|指定したコントロール ID によってウィンドウを検索します。|  
|[CMDIChildWndEx::GetRelatedTabGroup](#getrelatedtabgroup)||  
|[CMDIChildWndEx::GetTabbedPane](#gettabbedpane)|タブ付きドキュメントに変換された埋め込みドッキング ペインへのポインターを返します。|  
|[CMDIChildWndEx::GetTabProxyWnd](#gettabproxywnd)|返します。 は、Windows 7 タスク バーのタブに実際に登録されているプロキシ ウィンドウ タブします。|  
|[CMDIChildWndEx::GetTaskbarPreviewWnd](#gettaskbarpreviewwnd)|Windows 7 タスク バー タブのサムネイルに表示する子ウィンドウ (通常はビューまたは分割ウィンドウ) を取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::GetTaskbarThumbnailClipRect](#gettaskbarthumbnailcliprect)|ウィンドウのクライアント領域の一部を選択する必要があるときに、フレームワークによって呼び出されます。|  
|`CMDIChildWndEx::GetThisClass`|ポインターを取得するためにフレームワークによって呼び出される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMDIChildWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|ツール バー ボタンのツールヒントを取得するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::InsertPane](#insertpane)|指定したウィンドウをドッキング マネージャーに登録します。|  
|[CMDIChildWndEx::InvalidateIconicBitmaps](#invalidateiconicbitmaps)|MDI 子フォームのアイコン ビットマップ表示を無効にします。|  
|[CMDIChildWndEx::IsPointNearDockSite](#ispointneardocksite)|指定した点がドッキング サイトの近くにいるかどうかを判断します。|  
|[CMDIChildWndEx::IsReadOnly](#isreadonly)|返します。`TRUE`場合は、子ウィンドウに表示されるドキュメントは読み取り専用です。 それ以外の場合は、`FALSE` を返します。|  
|[CMDIChildWndEx::IsRegisteredWithTaskbarTabs](#isregisteredwithtaskbartabs)|Windows 7 タスク バー タブ付き MDI 子ウィンドウが正しく登録された場合は、TRUE を返します。|  
|[CMDIChildWndEx::IsTabbedPane](#istabbedpane)|返します。 `TRUE` MDI 子ウィンドウには、ドッキング ペインが含まれている場合。 それ以外の場合は、`FALSE` を返します。|  
|[CMDIChildWndEx::IsTaskbarTabsSupportEnabled](#istaskbartabssupportenabled)|MDI 子ウィンドウが、Windows 7 タスク バーのタブに表示できるかどうかを指示します。|  
|[CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled](#istaskbarthumbnailcliprectenabled)|ウィンドウのクライアント領域の一部の自動選択が有効か無効かどうかを示します。|  
|[CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags](#m_dwdefaulttaskbartabpropertyflags)|フレームワークによって SetTaskbarTabProperties メソッドはとタブ (MDI 子フォーム、に渡されるフラグの組み合わせは、Windows 7 タスク バーのタブに登録しています。 既定値の組み合わせが STPF_USEAPPTHUMBNAILWHENACTIVE |STPF_USEAPPPEEKWHENACTIVE します。|  
|[CMDIChildWndEx::OnGetIconicLivePreviewBitmap](#ongeticoniclivepreviewbitmap)|MDI 子ウィンドウのライブ プレビューのビットマップを取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnGetIconicThumbnail](#ongeticonicthumbnail)|MDI 子フォームのアイコンのサムネイルのビットマップを取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnMoveMiniFrame](#onmoveminiframe)|ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton](#onpresstaskbarthmbnailclosebutton)|ユーザーがタスク バー タブの縮小表示を閉じる ボタンを押したときに、フレームワークによって呼び出されます.|  
|[CMDIChildWndEx::OnSetPreviewMode](#onsetpreviewmode)|入力するか、印刷プレビュー モードを終了するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailActivate](#ontaskbartabthumbnailactivate)|タスク バー タブのサムネイルが WM_ACTIVATE メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate](#ontaskbartabthumbnailmouseactivate)|タスク バー タブのサムネイルが WM_MOUSEACTIVATE メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailStretch](#ontaskbartabthumbnailstretch)|MDI 子ウィンドウの Windows 7 タスク バー タブの縮小表示プレビューのビットマップを拡大する必要があるときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnUpdateFrameTitle](#onupdateframetitle)|フレームのタイトルを更新するためにフレームワークによって呼び出されます。 (`CMDIChildWnd::OnUpdateFrameTitle` をオーバーライドします)。|  
|[CMDIChildWndEx::PaneFromPoint](#panefrompoint)|指定したポイントを含むペインを返します。|  
|`CMDIChildWndEx::PreTranslateMessage`|クラスで使用される[CWinApp](../../mfc/reference/cwinapp-class.md)にディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数です。 (上書き[CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage))。|  
|[CMDIChildWndEx::RecalcLayout](#recalclayout)|ウィンドウのレイアウトを再計算します。|  
|[CMDIChildWndEx::RegisterTaskbarTab](#registertaskbartab)|Windows 7 タスク バー タブ付き MDI 子フォームを登録します。|  
|[CMDIChildWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|ペインをドッキング マネージャーから削除します。|  
|[CMDIChildWndEx::SetRelatedTabGroup](#setrelatedtabgroup)||  
|[CMDIChildWndEx::SetTaskbarTabActive](#settaskbartabactive)|対応する Windows 7 タスク バー タブをアクティブにします。|  
|[CMDIChildWndEx::SetTaskbarTabOrder](#settaskbartaborder)|Windows 7 タスク バーのタブで指定した期間の前に、MDI 子を挿入します。|  
|[CMDIChildWndEx::SetTaskbarTabProperties](#settaskbartabproperties)|Windows 7 のタスクバー タブのプロパティを設定します。|  
|[CMDIChildWndEx::SetTaskbarThumbnailClipRect](#settaskbarthumbnailcliprect)|ウィンドウのクライアント領域の一部を選択するクリッピング四角形を設定するためにフレームワークによって内部的に呼び出されます。|  
|[CMDIChildWndEx::ShowPane](#showpane)||  
|[CMDIChildWndEx::UnregisterTaskbarTab](#unregistertaskbartab)|Windows 7 タスク バーのタブから、MDI 子フォームを削除します。|  
|[CMDIChildWndEx::UpdateTaskbarTabIcon](#updatetaskbartabicon)|Windows 7 タスク バー タブのアイコンを更新します。|  
  
## <a name="remarks"></a>コメント  
 MDI アプリケーションでドッキングの拡張機能を利用するから、アプリケーションの MDI 子ウィンドウ クラスを派生させる`CMDIChildWndEx`の代わりに[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)します。  
  
## <a name="example"></a>例  
 次の例からクラスを派生する`CMDIChildWndEx`です。 このコード スニペットに由来、 [VisualStudioDemo サンプル: MFC の Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#3;](../../mfc/codesnippet/cpp/cmdichildwndex-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)  
  
 [CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxMDIChildWndEx.h  
  
##  <a name="addpane"></a>CMDIChildWndEx::AddPane  
 ペインを追加します。  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
 ペインへのポインター。  
  
 [入力] `bTail`  
 `TRUE`ドッキング マネージャーのペインの一覧の最後に、ウィンドウを追加するにはそれ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ウィンドウはドッキング マネージャーに正常に登録されましたそれ以外の場合、`FALSE`です。  
  
##  <a name="addtabbedpane"></a>CMDIChildWndEx::AddTabbedPane  
 タブ付きペインを追加します。  
  
```  
void AddTabbedPane(CDockablePane* pControlBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
 ペインへのポインター。  
  
##  <a name="adjustdockinglayout"></a>CMDIChildWndEx::AdjustDockingLayout  
 ドッキング レイアウトを調整します。  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hdwp`  
 遅延のウィンドウの位置の構造体へのハンドルします。  
  
##  <a name="canshowonmditabs"></a>CMDIChildWndEx::CanShowOnMDITabs  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanShowOnMDITabs();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="canshowonwindowslist"></a>CMDIChildWndEx::CanShowOnWindowsList  
 MDI 子ウィンドウの名前を表示できるかどうかを指定、 [CMFCWindowsManagerDialog クラス](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) ダイアログ ボックス。  
  
```  
virtual BOOL CanShowOnWindowsList();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウを表示できる場合、 **Windows**  ダイアログ ボックス。 そうしないと、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 派生クラスでは、このメソッドをオーバーライドし、返す`FALSE`でウィンドウを表示しない場合、 **Windows**  ダイアログ ボックス。 この関数から`CMFCWindowsManagerDialog`します。  
  
##  <a name="dockpane"></a>CMDIChildWndEx::DockPane  
 ペインをドッキングします。  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 ペインへのポインター。  
  
 [入力] `nDockBarID`  
 ペインの ID。  
  
 [入力] `lpRect`  
 四角形へのポインター。  
  
### <a name="remarks"></a>コメント  
 `lpRect`パラメーターは使用されません。  
  
##  <a name="dockpaneleftof"></a>CMDIChildWndEx::DockPaneLeftOf  
 ウィンドウを別のウィンドウの左側にドッキングします。  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBar`  
 ドッキングするウィンドウへのポインター。  
  
 `pLeftOf`  
 参照のポイントとして機能する、ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`成功した場合、`FALSE`を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定されたウィンドウには`pBar`で指定されたウィンドウの左側にドッキングして`pLeftOf`します。  
  
 事前定義された順序でいくつかのペインをドッキングするときに、このメソッドを呼び出します。  
  
##  <a name="enableautohidepanes"></a>CMDIChildWndEx::EnableAutoHidePanes  
 により自動的に隠すモードのペインのウィンドウの指定した辺にドッキングされている場合。  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwDockStyle`  
 有効になっているメイン フレーム ウィンドウの辺を指定します。 次のフラグの&1; つ以上を使用します。  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
##  <a name="enabledocking"></a>CMDIChildWndEx::EnableDocking  
 メインフレームへの子ウィンドウのドッキングを有効にします。  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwDockStyle`  
 有効にするドッキングの配置を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 メイン フレームにドッキングの配置を有効にするには、このメソッドを呼び出します。 Cbrs_align _ フラグの組み合わせを渡すことができます (詳細については、次を参照してください。 [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking))。  
  
##  <a name="getdockingmanager"></a>CMDIChildWndEx::GetDockingManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdocumentname"></a>CMDIChildWndEx::GetDocumentName  
 MDI 子ウィンドウに表示されているドキュメントの名前を返します。  
  
```  
virtual LPCTSTR GetDocumentName(CObject** pObj);
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントの名前を含む文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 ドキュメントは、MDI 子ウィンドウが表示されます。 一般に、ウィンドウから読み込まれた、またはファイルに保存されるデータが表示されます。 そのため、ドキュメントの名前は、ファイルの名前です。 既定の実装`GetDocumentName`から取得した文字列を返す`CDocument::GetPathName`します。  
  
 ウィンドウには、ファイルから読み込まれていないドキュメントが表示されている場合は、派生クラスでは、このメソッドをオーバーライドし、ドキュメントの一意の識別子を返します。  
  
 `GetDocumentName`すべての開いているドキュメントの状態を保存するときに、フレームワークによって呼び出されます。 返される文字列は、レジストリに書き込まれます。  
  
 ドキュメントの名前が、レジストリから読み取るしに渡されるフレームワークでは、後で状態を復元は、 [CMDIFrameWndEx::CreateDocumentWindow](../../mfc/reference/cmdiframewndex-class.md#createdocumentwindow)します。 このメソッドをオーバーライドして、 [CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)-クラスを派生し、作成またはこの名前を持つドキュメントを開き、この名前を持つファイルで読み取らします。 ドキュメントがファイルに基づいていない、ドキュメント識別子自体に基づくドキュメントを作成します。 保存し、ドキュメントを復元する場合にのみ、上記のアクションを行う必要があります。  
  
### <a name="example"></a>例  
 `GetDocumentName` メソッドの使用例を次に示します。 このコード スニペットに由来、 [VisualStudioDemo サンプル: MFC の Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&17;](../../mfc/codesnippet/cpp/cmdichildwndex-class_2.cpp)]  
  
##  <a name="getframeicon"></a>CMDIChildWndEx::GetFrameIcon  
 MDI 子ウィンドウのアイコンを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual HICON GetFrameIcon() const;  
```  
  
### <a name="return-value"></a>戻り値  
 [ウィンドウ] アイコンのハンドル。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、MDI 子フレーム ウィンドウを含む MDI タブに表示するには、どのようなアイコンを決定するためにフレームワークによって呼び出されます。  
  
 既定では、このメソッドは、[ウィンドウ] アイコンを返します。 オーバーライド`GetFrameIcon`で、 `CMDIChildWndEx`-この動作をカスタマイズするクラスを派生します。  
  
##  <a name="getframetext"></a>CMDIChildWndEx::GetFrameText  
 MDI 子ウィンドウのテキストを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual CString GetFrameText() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フレーム ウィンドウのテキストを含む文字列です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、MDI 子フレーム ウィンドウを含む MDI タブに表示するには、どのようなテキストを調べるためにフレームワークによって呼び出されます。  
  
 既定では、このメソッドは、ウィンドウのテキストを返します。 オーバーライド`GetFrameText`で、 `CMDIChildWndEx`-この動作をカスタマイズするクラスを派生します。  
  
##  <a name="getpane"></a>CMDIChildWndEx::GetPane  
 指定したコントロール ID によってウィンドウを検索します。  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 検索するウィンドウのコントロール ID。  
  
### <a name="return-value"></a>戻り値  
 ペインへのポインター場合見つかると、それ以外の場合`NULL`します。  
  
##  <a name="getrelatedtabgroup"></a>CMDIChildWndEx::GetRelatedTabGroup  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCTabCtrl* GetRelatedTabGroup();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettabbedpane"></a>CMDIChildWndEx::GetTabbedPane  
 タブ付きドキュメントの MDI のグループの一部であるドッキング ペインへのポインターを返します。  
  
```  
CDockablePane* GetTabbedPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タブ付きドキュメントの MDI のグループの一部であるドッキング ペインへのポインター。  
  
##  <a name="gettoolbarbuttontooltiptext"></a>CMDIChildWndEx::GetToolbarButtonToolTipText  
 ツール バー ボタンのツールヒントを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton*, 
    CString&);
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ツールヒントが表示されています。 既定の実装では、`FALSE` が返されます。  
  
### <a name="remarks"></a>コメント  
 ツール バー ボタンのカスタム ツール ヒントを表示する場合は、このメソッドをオーバーライドします。  
  
##  <a name="insertpane"></a>CMDIChildWndEx::InsertPane  
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
  
##  <a name="ispointneardocksite"></a>CMDIChildWndEx::IsPointNearDockSite  
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
  
 [入力] `dwBarAlignment`  
 どちらの端点が近いを指定します。 指定できる値は`CBRS_ALIGN_LEFT`、 `CBRS_ALIGN_RIGHT`、`CBRS_ALIGN_TOP`と`CBRS_ALIGN_BOTTOM`  
  
 [入力] `bOuterEdge`  
 `TRUE`ドッキング サイトの外側の境界線の近くのポイントがある場合`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング サイトの近くのポイントがある場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 ポイントは、ドッキング マネージャーで設定された感度内にある場合に、ドッキング サイトの近くです。 既定値と小文字の区別は、15 ピクセルです。  
  
##  <a name="isreadonly"></a>CMDIChildWndEx::IsReadOnly  
 子ウィンドウに表示されるドキュメントは読み取り専用であるかどうかを指定します。  
  
```  
virtual BOOL IsReadOnly();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドキュメントが読み取り専用の場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 この関数を防ぐために使用される読み取り専用の文書を保存します。  
  
### <a name="example"></a>例  
 次の例では、オーバーライドを示しています、`IsReadOnly`メソッドです。 このコード スニペットに由来、 [VisualStudioDemo サンプル: MFC の Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#2;](../../mfc/codesnippet/cpp/cmdichildwndex-class_3.cpp)]  
  
##  <a name="istabbedpane"></a>CMDIChildWndEx::IsTabbedPane  
 MDI 子ウィンドウがドッキング ペインを含むかどうかを指定します。  
  
```  
BOOL IsTabbedPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`MDI 子ウィンドウには、タブ付きドキュメントに変換されたドッキング ペインが含まれている場合それ以外の場合`FALSE`します。  
  
##  <a name="onmoveminiframe"></a>CMDIChildWndEx::OnMoveMiniFrame  
 ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pFrame`  
 ミニフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`それ以外の場合、メソッドが成功した場合`FALSE`します。  
  
##  <a name="onsetpreviewmode"></a>CMDIChildWndEx::OnSetPreviewMode  
 入力するか、印刷プレビュー モードを終了するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bPreview`  
 場合`TRUE`、印刷プレビュー モードを開始します。 場合`FALSE`、印刷プレビュー モードを終了します。  
  
 [入力] `pState`  
 印刷プレビューの状態の構造体へのポインター。  
  
##  <a name="onupdateframetitle"></a>CMDIChildWndEx::OnUpdateFrameTitle  
 フレームのタイトルを更新するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bAddToTitle`  
 場合`TRUE`タイトルにドキュメントの名前を追加します。  
  
##  <a name="panefrompoint"></a>CMDIChildWndEx::PaneFromPoint  
 指定したポイントを含むペインを返します。  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar,  
    CRuntimeClass* pRTCBarType) const;  
  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 確認の画面座標で、ポイントを指定します。  
  
 [入力] `nSensitivity`  
 この金額には、検索領域を拡大します。 ペインは、指定したポイントが拡大された領域で該当する場合に、検索条件を満たします。  
  
 [入力] `bExactBar`  
 `TRUE`無視する、`nSensitivity`パラメーター。 そうしないと、`FALSE`です。  
  
 [入力] `pRTCBarType`  
 ない場合`NULL`、指定した型のペインだけを検索します。  
  
 [入力] `dwAlignment`  
 指定したポイントに、ウィンドウが見つかった場合、このパラメーターが指定したポイントに最も近いペインの横にはが含まれています。 詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 `CBasePane`-指定したポイントを格納しているオブジェクトを派生または`NULL`ウィンドウが検出されなかった場合。  
  
### <a name="remarks"></a>コメント  
 ランタイム クラスと可視性などの指定した条件に従って、指定した点がウィンドウに含まれるかどうかを確認するには、このメソッドを呼び出します。  
  
 この関数に戻り、ペインが見つかった`dwAlignment`指定した点の配置が含まれています。 たとえば、次の点が、ウィンドウの上部に最も近い`dwAlignment`に設定されている`CBRS_ALIGN_TOP`します。  
  
##  <a name="recalclayout"></a>CMDIChildWndEx::RecalcLayout  
 ウィンドウのレイアウトを再計算します。  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bNotify`  
 場合`TRUE`ウィンドウのアクティブなインプレース アイテムがレイアウトの変更の通知を受信します。  
  
##  <a name="removepanefromdockmanager"></a>CMDIChildWndEx::RemovePaneFromDockManager  
 ペインをドッキング マネージャーから削除します。  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pControlBar,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide,  
    CBasePane* pBarReplacement);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
 削除するのには、ウィンドウへのポインター。  
  
 [入力] `bDestroy`  
 場合`TRUE`、削除されたウィンドウを破棄します。  
  
 [入力] `bAdjustLayout`  
 場合`TRUE`、すぐにドッキング レイアウトを調整します。  
  
 [入力] `bAutoHide`  
 場合`TRUE`、ドッキング レイアウトが自動的に隠す バーのリストに関連しています。 場合`FALSE`、ドッキング レイアウトが標準のペインのリストに関連します。  
  
 [入力] `pBarReplacement`  
 削除されるペインに置き換えられるペインへのポインター。  
  
##  <a name="setrelatedtabgroup"></a>CMDIChildWndEx::SetRelatedTabGroup  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetRelatedTabGroup(CMFCTabCtrl* p);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `p`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="showpane"></a>CMDIChildWndEx::ShowPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `bShow`  
 [入力] `bDelay`  
 [入力] `bActivate`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="updatetaskbartabicon"></a>CMDIChildWndEx::UpdateTaskbarTabIcon  
 Windows 7 タスク バー タブのアイコンを更新します。  
  
```  
virtual void UpdateTaskbarTabIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 `hIcon`  
 Windows 7 タスク バー タブに表示するアイコンへのハンドル。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="unregistertaskbartab"></a>CMDIChildWndEx::UnregisterTaskbarTab  
 Windows 7 タスク バーのタブから、MDI 子を削除します。  
  
```  
void UnregisterTaskbarTab(BOOL bCheckRegisteredMDIChildCount = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bCheckRegisteredMDIChildCount`  
 この関数が MDI 子フォーム MDI タブに登録されている数を確認する必要があるかどうかを指定します。 この数値が 0 の場合、この関数は、アプリケーションのタスク バーの縮小表示からクリッピング四角形を削除し、します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="settaskbarthumbnailcliprect"></a>CMDIChildWndEx::SetTaskbarThumbnailClipRect  
 ウィンドウのクライアント領域の一部を選択するクリッピング四角形を設定するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL SetTaskbarThumbnailClipRect(CRect rect);
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 新しいクリッピング四角形を指定します。 四角形が空または null の場合は、クリッピングが削除されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="settaskbartabproperties"></a>CMDIChildWndEx::SetTaskbarTabProperties  
 Windows 7 のタスクバー タブのプロパティを設定します。  
  
```  
void SetTaskbarTabProperties(DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 STPFLAG の値の組み合わせ。 詳細については、次を参照してください。 [itaskbarlist&4;::settabproperties](http://msdn.microsoft.com/library/dd562049\(vs.85\).aspx)します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="settaskbartaborder"></a>CMDIChildWndEx::SetTaskbarTabOrder  
 Windows 7 タスク バーのタブで指定した期間の前に、MDI 子を挿入します。  
  
```  
void SetTaskbarTabOrder(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndBefore`  
 サムネイルの左側に挿入する MDI 子ウィンドウへのポインター。 このウィンドウを登録する必要が既に`RegisterTaskbarTab`します。 この値が場合`NULL`、新しい縮小表示がリストの末尾に追加します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="settaskbartabactive"></a>CMDIChildWndEx::SetTaskbarTabActive  
 対応する Windows 7 タスク バー タブをアクティブにします。  
  
```  
void SetTaskbarTabActive();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="registertaskbartab"></a>CMDIChildWndEx::RegisterTaskbarTab  
 Windows 7 タスク バー タブ付き MDI 子ウィンドウを登録します。  
  
```  
virtual void RegisterTaskbarTab(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndBefore`  
 サムネイルの左側に挿入する MDI 子ウィンドウへのポインター。 このウィンドウを登録する必要が既に`RegisterTaskbarTab`します。 この値が場合`NULL`、新しい縮小表示がリストの末尾に追加します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ontaskbartabthumbnailstretch"></a>CMDIChildWndEx::OnTaskbarTabThumbnailStretch  
 MDI 子ウィンドウの Windows 7 タスク バー タブ縮小表示プレビューのビットマップを拡大する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnTaskbarTabThumbnailStretch(
    HBITMAP hBmpDst,  
    const CRect& rectDst,  
    HBITMAP hBmpSrc,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `hBmpDst`  
 コピー先のビットマップへのハンドル。  
  
 `rectDst`  
 コピー先の四角形を指定します。  
  
 `hBmpSrc`  
 元のビットマップへのハンドル。  
  
 `rectSrc`  
 元の四角形を指定します。  
  
### <a name="remarks"></a>コメント  
 Requirementher または彼彼彼彼彼彼彼**:** afxmdichildwndex.h  
  
##  <a name="ontaskbartabthumbnailmouseactivate"></a>CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate  
 タスク バー タブのサムネイルが WM_MOUSEACTIVATE メッセージを処理するときに、フレームワークによって呼び出されます。  
  
```  
virtual int OnTaskbarTabThumbnailMouseActivate(
    CWnd* pDesktopWnd,  
    UINT nHitTest,  
    UINT message);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDesktopWnd`  
 アクティブ化されているウィンドウの最上位の親ウィンドウへのポインターを指定します。 ポインターは、一時的な場合があり、保存されません。  
  
 `nHitTest`  
 ヒット テスト領域のコードを指定します。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 `message`  
 マウス メッセージの番号を指定します。  
  
### <a name="remarks"></a>コメント  
 既定の実装には、関連する MDI 子フレームがアクティブになります。  
  
##  <a name="ontaskbartabthumbnailactivate"></a>CMDIChildWndEx::OnTaskbarTabThumbnailActivate  
 タスク バー タブのサムネイルが WM_ACTIVATE メッセージを処理するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnTaskbarTabThumbnailActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>パラメーター  
 `nState`  
 指定するかどうか、`CWnd`がアクティブ化または非アクティブ化します。  
  
 `pWndOther`  
 ポインター、`CWnd`アクティブまたは非アクティブになります。 マウス ポインターを指定できます`NULL`、一時的な場合があります。  
  
 `bMinimized`  
 最小化された状態を示す、`CWnd`アクティブまたは非アクティブになります。 値`TRUE`ウィンドウが最小化されていることを示します。  
  
### <a name="remarks"></a>コメント  
 既定の実装には、関連する MDI 子フレームがアクティブになります。  
  
##  <a name="onpresstaskbarthmbnailclosebutton"></a>CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton  
 ユーザーがタスク バー タブのサムネイルに閉じるボタンを押したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnPressTaskbarThmbnailCloseButton();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ongeticonicthumbnail"></a>CMDIChildWndEx::OnGetIconicThumbnail  
 MDI 子ウィンドウのアイコンのサムネイルのビットマップを取得する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual HBITMAP OnGetIconicThumbnail(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `nWidth`  
 必要なビットマップの幅を指定します。  
  
 `nHeight`  
 必要なビットマップの高さを指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ongeticoniclivepreviewbitmap"></a>CMDIChildWndEx::OnGetIconicLivePreviewBitmap  
 MDI 子ウィンドウのライブ プレビューのビットマップを取得する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual HBITMAP OnGetIconicLivePreviewBitmap(
    BOOL bIsMDIChildActive,  
    CPoint& ptLocation);
```  
  
### <a name="parameters"></a>パラメーター  
 `bIsMDIChildActive`  
 このパラメーターは`TRUE`場合は、MDI 子のビットマップが要求されると、これが現在アクティブなメイン ウィンドウが最小化されていません。 既定の処理をここでは、メイン ウィンドウのスナップショットを取得します。  
  
 `ptLocation`  
 Main (最上位) で、ビットマップの場所を指定するウィンドウのクライアント座標。 このポイントは、呼び出し先によって提供される必要があります。  
  
### <a name="return-value"></a>戻り値  
 処理された場合、ハンドルを返します有効な 32 bpp のビットマップでは、それ以外の場合`NULL`します。  
  
### <a name="remarks"></a>コメント  
 派生クラスでは、このメソッドをオーバーライドし、MDI 子ウィンドウのライブ プレビューの有効な 32 bpp のビットマップを返します。 MDI 子ウィンドウは、Windows 7 タスク バーのタブに表示される場合にのみ、このメソッドが呼び出されます。 返された場合`NULL`、MFC の既定のハンドラーが呼び出されてとビットマップが使用して取得`PrintClient`または`PrintWindow`です。  
  
##  <a name="m_dwdefaulttaskbartabpropertyflags"></a>CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags  
 フレームワークによって渡されるフラグの組み合わせ、`SetTaskbarTabProperties`メソッドは、Windows 7 タスク バー タブを持つタブ (MDI 子) が登録されているとします。  
  
```  
AFX_IMPORT_DATA static DWORD m_dwDefaultTaskbarTabPropertyFlags;  
```  
  
### <a name="remarks"></a>コメント  
 既定値の組み合わせが STPF_USEAPPTHUMBNAILWHENACTIVE |STPF_USEAPPPEEKWHENACTIVE します。  
  
##  <a name="istaskbarthumbnailcliprectenabled"></a>CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled  
 ウィンドウのクライアント領域の一部の自動選択が有効か無効かどうかを示します。  
  
```  
BOOL IsTaskbarThumbnailClipRectEnabled() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`を表示するウィンドウのクライアント領域の一部の自動選択が有効であるそれ以外の場合は場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="istaskbartabssupportenabled"></a>CMDIChildWndEx::IsTaskbarTabsSupportEnabled  
 MDI 子ウィンドウが、Windows 7 タスク バーのタブに表示できるかどうかを指示します。  
  
```  
BOOL IsTaskbarTabsSupportEnabled();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`MDI 子ウィンドウは、Windows 7 タスク バー タブに表示できる場合`FALSE`場合は、MDI 子が Windows 7 タスク バーのタブに表示されないことができます。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isregisteredwithtaskbartabs"></a>CMDIChildWndEx::IsRegisteredWithTaskbarTabs  
 返します。`TRUE`場合は、MDI 子は、Windows 7 タスク バー タブに正常に登録されました。  
  
```  
BOOL IsRegisteredWithTaskbarTabs();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`MDI 子ウィンドウが Windows 7 タスク バー タブ; に登録されている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="invalidateiconicbitmaps"></a>CMDIChildWndEx::InvalidateIconicBitmaps  
 MDI 子ウィンドウのアイコン ビットマップ表示を無効にします。  
  
```  
BOOL InvalidateIconicBitmaps();
```  
  
### <a name="return-value"></a>戻り値  
 返します`FALSE`Windows 7 タスク バーのサポートが無効になっているか、MDI 子ウィンドウは、Windows 7 タスク バー タブ; に登録されていない場合、それ以外の場合を返します`TRUE`します。  
  
### <a name="remarks"></a>コメント  
 ライブ コンテンツまたは MDI 子ウィンドウのサイズが変更されたときに呼び出す必要があります。  
  
##  <a name="gettaskbarthumbnailcliprect"></a>CMDIChildWndEx::GetTaskbarThumbnailClipRect  
 ウィンドウのクライアント領域の一部を選択する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual CRect GetTaskbarThumbnailClipRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Windows の座標で四角形。 この四角形は、最上位フレームのクライアント領域にマップされます。 四角形は、クリッピング四角形をオフにするには、空にする必要があります。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettaskbarpreviewwnd"></a>CMDIChildWndEx::GetTaskbarPreviewWnd  
 Windows 7 タスク バー タブのサムネイルに表示する子ウィンドウ (通常はビューまたは分割ウィンドウ) を取得する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual CWnd* GetTaskbarPreviewWnd();
```  
  
### <a name="return-value"></a>戻り値  
 有効なポインターを返す必要があります、`CWnd`この MDI 子に関連するオブジェクト、Windows 7 タスク バー タブ上のプレビューを表示する必要があります。 既定の実装が AFX_IDW_PANE_FIRST コントロール ID の場合は、この MDI 子の子ウィンドウを返します (これは、通常、`CView`の派生クラス)。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettabproxywnd"></a>CMDIChildWndEx::GetTabProxyWnd  
 Windows 7 タスク バーのタブに登録されているタブ プロキシ ウィンドウを返します。  
  
```  
CMDITabProxyWnd* GetTabProxyWnd();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CMDITabProxyWnd`オブジェクトで、Windows 7 タスク バーのタブに登録されています。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enabletaskbarthumbnailcliprect"></a>CMDIChildWndEx::EnableTaskbarThumbnailClipRect  
 有効またはウィンドウのクライアント領域の一部の自動選択を無効にします。  
  
```  
void EnableTaskbarThumbnailClipRect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 有効にするかどうかを指定します ( `TRUE`)、または無効にする ( `FALSE`) を表示するウィンドウのクライアント領域の部分が自動的に選択します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="canshowontaskbartabs"></a>CMDIChildWndEx::CanShowOnTaskBarTabs  
 Windows 7 タスク バーのタブにこの MDI 子フォームを表示するかどうかをフレームワークに指示します。  
  
```  
virtual BOOL CanShowOnTaskBarTabs();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`MDI 子ウィンドウのコンテンツは、Windows 7 タスク バーの縮小表示に表示されることができる場合。  
  
### <a name="remarks"></a>コメント  
 派生クラスでは、このメソッドをオーバーライドし、返す`FALSE`この MDI 子フォームの Windows 7 タスク バー タブの外観を無効にします。  
  
##  <a name="activatetoplevelframe"></a>CMDIChildWndEx::ActivateTopLevelFrame  
 タスク バー タブから、アプリケーションがアクティブになったときに、最上位フレームをアクティブ化するために、フレームワークによって呼び出されます。  
  
```  
virtual void ActivateTopLevelFrame();
```  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)   
 [CMFCWindowsManagerDialog クラス](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)   
 [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)

