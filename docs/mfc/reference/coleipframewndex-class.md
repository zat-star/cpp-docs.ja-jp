---
title: "COleIPFrameWndEx クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleIPFrameWndEx
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AddDockSite
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AddPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AdjustDockingLayout
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::DockPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::DockPaneLeftOf
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnableAutoHidePanes
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnableDocking
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnablePaneMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetActivePopup
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetContainerFrameWindow
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDefaultResId
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDockFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDockingManager
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetMainFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetMenuBar
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetTearOffBars
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetToolbarButtonToolTipText
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::InsertPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::IsMenuBarAvailable
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::IsPointNearDockSite
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::LoadFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCloseDockingPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCloseMiniFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnClosePopupMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCmdMsg
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnDrawMenuImage
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnDrawMenuLogo
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnMenuButtonToolHitTest
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnMoveMiniFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnSetPreviewMode
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowCustomizePane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowPanes
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowPopupMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnTearOffMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::PaneFromPoint
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::PreTranslateMessage
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::RecalcLayout
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::RemovePaneFromDockManager
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::SetDockState
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::SetupToolbarMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::ShowPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::WinHelpA
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::InitUserToobars
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWndEx class
ms.assetid: ebff1560-a1eb-4854-af00-95d4a192bd55
caps.latest.revision: 34
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5eec8e3a9cc4ad71a1ee3de9f6d5f25cffef1242
ms.lasthandoff: 02/24/2017

---
# <a name="coleipframewndex-class"></a>COleIPFrameWndEx クラス
`COleIPFrameWndEx` クラスは、MFC をサポートする OLE コンテナーを実装します。 自分のアプリケーションで埋め込み先フレーム ウィンドウ クラスを派生させる必要があります、`COleIPFrameWndEx`クラスから派生することではなく、 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class COleIPFrameWndEx : public COleIPFrameWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleIPFrameWndEx::AddDockSite](#adddocksite)||  
|[COleIPFrameWndEx::AddPane](#addpane)||  
|[COleIPFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)||  
|[COleIPFrameWndEx::DockPane](#dockpane)||  
|[COleIPFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|ウィンドウを別のウィンドウの左側にドッキングします。|  
|[COleIPFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)||  
|[COleIPFrameWndEx::EnableDocking](#enabledocking)||  
|[COleIPFrameWndEx::EnablePaneMenu](#enablepanemenu)||  
|[COleIPFrameWndEx::GetActivePopup](#getactivepopup)|現在表示されているポップアップ メニューへのポインターを返します。|  
|[COleIPFrameWndEx::GetContainerFrameWindow](#getcontainerframewindow)||  
|[COleIPFrameWndEx::GetDefaultResId](#getdefaultresid)|ウィンドウが読み込まれるときに指定した、フレーム ウィンドウのリソース ID を返します。|  
|[COleIPFrameWndEx::GetDockFrame](#getdockframe)||  
|[COleIPFrameWndEx::GetDockingManager](#getdockingmanager)||  
|[COleIPFrameWndEx::GetMainFrame](#getmainframe)||  
|[COleIPFrameWndEx::GetMenuBar](#getmenubar)|フレーム ウィンドウにアタッチされているメニュー バーのオブジェクトへのポインターを返します。|  
|[COleIPFrameWndEx::GetPane](#getpane)||  
|[COleIPFrameWndEx::GetTearOffBars](#gettearoffbars)|ティアオフ状態にあるウィンドウ オブジェクトの一覧を返します。|  
|[COleIPFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|ボタンのツールヒントが表示される前に、フレームワークによって呼び出されます。|  
|[COleIPFrameWndEx::InsertPane](#insertpane)||  
|[COleIPFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|メニュー バーのオブジェクトへのポインターが `NULL`ではないかどうかを判断します。|  
|[COleIPFrameWndEx::IsPointNearDockSite](#ispointneardocksite)||  
|[COleIPFrameWndEx::LoadFrame](#loadframe)|( `COleIPFrameWnd::LoadFrame`をオーバーライドします)。|  
|[COleIPFrameWndEx::OnCloseDockingPane](#onclosedockingpane)||  
|[COleIPFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)||  
|[COleIPFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|アクティブなポップアップ メニューが WM_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[COleIPFrameWndEx::OnCmdMsg](#oncmdmsg)|( `CFrameWnd::OnCmdMsg`をオーバーライドします)。|  
|[COleIPFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|メニュー項目に関連付けられているイメージが描画されるときに、フレームワークによって呼び出されます。|  
|[COleIPFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|フレームワークによって呼び出されるときに、 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)WM_PAINT メッセージを処理するオブジェクト。|  
|[COleIPFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|フレームワークによって呼び出されるときに、 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクト WM_NCHITTEST メッセージを処理します。|  
|[COleIPFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)||  
|[COleIPFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|印刷プレビュー モードの内外にアプリケーションのメイン フレーム ウィンドウを設定するには、このメンバー関数を呼び出します。 (上書き[CFrameWnd::OnSetPreviewMode](../../mfc/reference/cframewnd-class.md#onsetpreviewmode))。|  
|[COleIPFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)||  
|[COleIPFrameWndEx::OnShowPanes](#onshowpanes)||  
|[COleIPFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|ポップアップ メニューがアクティブにされるときにフレームワークによって呼び出されます。|  
|[COleIPFrameWndEx::OnTearOffMenu](#ontearoffmenu)|ティアオフ バーのあるメニューがアクティブ化されるときにフレームワークによって呼び出されます。|  
|[COleIPFrameWndEx::PaneFromPoint](#panefrompoint)||  
|[COleIPFrameWndEx::PreTranslateMessage](#pretranslatemessage)|( `COleIPFrameWnd::PreTranslateMessage`をオーバーライドします)。|  
|[COleIPFrameWndEx::RecalcLayout](#recalclayout)|( `COleIPFrameWnd::RecalcLayout`をオーバーライドします)。|  
|[COleIPFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)||  
|[COleIPFrameWndEx::SetDockState](#setdockstate)|フレーム ウィンドウに属しているウィンドウに、指定のドッキング状態を適用します。|  
|[COleIPFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|ダミーの項目を検索して、指定されたユーザー定義の項目で置き換えることで、ツールバーのオブジェクトを変更します。|  
|[COleIPFrameWndEx::ShowPane](#showpane)||  
|[COleIPFrameWndEx::WinHelpA](#winhelpa)|WinHelp アプリケーションまたはコンテキスト ヘルプを起動するために、フレームワークによって呼び出されます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleIPFrameWndEx::InitUserToobars](#initusertoobars)|ユーザー定義のツールバーに割り当てられているコントロールの ID の範囲を初期化するようフレームワークに指示します。|  
  
## <a name="example"></a>例  
 次の例は、 `COleIPFrameWndEx` クラスのインスタンスをサブクラス化して、メソッドをオーバーライドする方法を示しています。 `OnDestory` メソッド、 `RepositionFrame` メソッド、 `RecalcLayout` メソッド、および `CalcWindowRect` メソッドをオーバーライドする方法を例に示します。 このコード スニペットの一部である、 [Word パッド サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_WordPad&#1;](../../mfc/reference/codesnippet/cpp/coleipframewndex-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)  
  
 [COleIPFrameWndEx](../../mfc/reference/coleipframewndex-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxoleipframewndex.h  
  
##  <a name="adddocksite"></a>COleIPFrameWndEx::AddDockSite  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AddDockSite();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addpane"></a>COleIPFrameWndEx::AddPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
 [入力] `bTail`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="adjustdockinglayout"></a>COleIPFrameWndEx::AdjustDockingLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hdwp`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="dockpane"></a>COleIPFrameWndEx::DockPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `nDockBarID`  
 [入力] `lpRect`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="dockpaneleftof"></a>COleIPFrameWndEx::DockPaneLeftOf  
 ウィンドウを別のウィンドウの左側にドッキングします。  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 ドッキングするのには、ウィンドウへのポインター。  
  
 [入力] `pLeftOf`  
 配信元として機能するペインへのポインター。  
  
### <a name="return-value"></a>戻り値  
 返します。 `TRUE` 、操作が成功した場合。 それ以外の場合は、`FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
 事前定義された順序で複数のペインのオブジェクトをドッキングするには、このメソッドを呼び出します。 このメソッドで指定されたウィンドウのドッキング`pBar`で指定されたウィンドウの左側に`pLeftOf`します。  
  
##  <a name="enableautohidepanes"></a>COleIPFrameWndEx::EnableAutoHidePanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwDockStyle`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enabledocking"></a>COleIPFrameWndEx::EnableDocking  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwDockStyle`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enablepanemenu"></a>COleIPFrameWndEx::EnablePaneMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnablePaneMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeLabel,  
    UINT uiViewToolbarsMenuEntryID,  
    BOOL bContextMenuShowsToolbarsOnly = FALSE,  
    BOOL bViewMenuShowsToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 [入力] `uiCustomizeCmd`  
 [入力] `strCustomizeLabel`  
 [入力] `uiViewToolbarsMenuEntryID`  
 [入力] `bContextMenuShowsToolbarsOnly`  
 [入力] `bViewMenuShowsToolbarsOnly`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getactivepopup"></a>COleIPFrameWndEx::GetActivePopup  
 現在表示されているポップアップ メニューへのポインターを返します。  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アクティブなポップアップ メニュー; へのポインターそれ以外の場合`NULL`します。  
  
### <a name="remarks"></a>コメント  
 ポインターを取得するには、このメソッドを使用して、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)現在表示されているオブジェクト。  
  
##  <a name="getcontainerframewindow"></a>COleIPFrameWndEx::GetContainerFrameWindow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
COleCntrFrameWndEx* GetContainerFrameWindow();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdefaultresid"></a>COleIPFrameWndEx::GetDefaultResId  
 メニュー リソース ID を指定のフレーム ウィンドウで、メニューがどのように読み込まれるときに返します。  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フレーム ウィンドウのメニュー バーにない場合は、リソース ID、メニューまたは 0 を返します。  
  
### <a name="remarks"></a>コメント  
 リソース ID を取得するには、この関数は、フレーム ウィンドウによって呼び出すことによって、メニュー リソースが読み込まれるときに指定されている呼び出し`COleIPFrameWndEx::LoadFrame`します。  
  
##  <a name="getdockframe"></a>COleIPFrameWndEx::GetDockFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CFrameWnd* GetDockFrame();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdockingmanager"></a>COleIPFrameWndEx::GetDockingManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getmainframe"></a>COleIPFrameWndEx::GetMainFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CFrameWnd* GetMainFrame();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getmenubar"></a>COleIPFrameWndEx::GetMenuBar  
 フレーム ウィンドウにアタッチされているメニュー バーのオブジェクトへのポインターを返します。  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メニュー バーのオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 メニュー バー オブジェクトに属するへのポインターを取得するこの関数を使用して、`COleIPFrameWndEx`オブジェクトです。  
  
##  <a name="getpane"></a>COleIPFrameWndEx::GetPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettearoffbars"></a>COleIPFrameWndEx::GetTearOffBars  
 ティアオフ状態にあるウィンドウ オブジェクトの一覧を返します。  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>戻り値  
 参照、`CObList`へのポインターのコレクションを格納するオブジェクト、 [CBasePane クラス](../../mfc/reference/cbasepane-class.md)の派生クラスのオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `COleIPFrameWndEx`オブジェクトの一覧としてティアオフ メニューのコレクションを保持する[CBasePane クラス](../../mfc/reference/cbasepane-class.md)の派生クラスのオブジェクト。 このメソッドを使用すると、この一覧への参照を取得できます。  
  
##  <a name="gettoolbarbuttontooltiptext"></a>COleIPFrameWndEx::GetToolbarButtonToolTipText  
 ボタンのツールヒントが表示される前に、フレームワークによって呼び出されます。  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
 ボタンへのポインター。  
  
 [入力] `strTTText`  
 ツールヒントのテキストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、0 を返します。  
  
### <a name="remarks"></a>コメント  
 ツール バー ボタンのツールヒントの表示をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="initusertoobars"></a>COleIPFrameWndEx::InitUserToobars  
 コントロール、フレームワークは、ユーザー定義のツールバーに代入する Id の範囲を指定します。  
  
```  
void InitUserToolbars(
    LPCTSTR lpszRegEntry,   
    UINT uiUserToolbarFirst,   
    UINT uiUserToolbarLast)  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszRegEntry`  
 レジストリ エントリは、ライブラリがユーザー ツールバーの設定を格納する場所です。  
  
 [入力] `uiUserToolbarFirst`  
 ユーザー定義の最初のツールバーに割り当てられているコントロールの ID。  
  
 [入力] `uiUserToolbarLast`  
 最後のユーザー定義のツールバーに割り当てられているコントロールの ID。  
  
### <a name="remarks"></a>コメント  
 ユーザーが動的に定義したツールバーへの割り当てのコントロール Id の範囲を初期化するのにには、この関数を使用します。 パラメーター`uiUserToolbarFirst`と`uiUserToolbarLast`許可されているツール バー コントロールの Id の範囲を定義します。 ユーザー定義のツールバーの作成を無効にする設定`uiUserToolbarFirst`または`uiUserToolbarLast`を-1 にします。  
  
##  <a name="insertpane"></a>COleIPFrameWndEx::InsertPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
 [入力] `pTarget`  
 [入力] `bAfter`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ismenubaravailable"></a>COleIPFrameWndEx::IsMenuBarAvailable  
 メニュー バーのオブジェクトへのポインターがないかどうかを確認します。`NULL`  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外を返します。 値のフレーム ウィンドウにメニュー バーです。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 以外のフレーム ウィンドウを保持かどうかを判断するには、このメソッドを呼び出す`NULL`メニュー バー オブジェクトへのポインター。  
  
##  <a name="ispointneardocksite"></a>COleIPFrameWndEx::IsPointNearDockSite  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 [入力] `dwBarAlignment`  
 [入力] `bOuterEdge`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="loadframe"></a>COleIPFrameWndEx::LoadFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIDResource`  
 [入力] `dwDefaultStyle`  
 [入力] `pParentWnd`  
 [入力] `pContext`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onclosedockingpane"></a>COleIPFrameWndEx::OnCloseDockingPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCloseDockingPane(CDockablePane*);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `CDockablePane*`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="oncloseminiframe"></a>COleIPFrameWndEx::OnCloseMiniFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd*);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `CPaneFrameWnd*`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onclosepopupmenu"></a>COleIPFrameWndEx::OnClosePopupMenu  
 アクティブなポップアップ メニューを処理するときに、フレームワークによって呼び出され、`WM_DESTROY`メッセージです。  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenuPopup`  
 ポップアップ メニュー オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 通知を受信するには、このメソッドをオーバーライド`CMFCPopupMenu`オブジェクトを処理するときに`WM_DESTROY`メッセージです。  
  
##  <a name="oncmdmsg"></a>COleIPFrameWndEx::OnCmdMsg  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 [入力] `nCode`  
 [入力] `pExtra`  
 [入力] `pHandlerInfo`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondrawmenuimage"></a>COleIPFrameWndEx::OnDrawMenuImage  
 メニュー項目に関連付けられているイメージが描画されるときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnDrawMenuImage(
    CDC* pDC,  
    const CMFCToolBarMenuButton* pMenuButton,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `pMenuButton`  
 メニュー ボタンへのポインター。  
  
 [入力] `rectImage`  
 メニュー項目に関連付けられたイメージ。  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、何も実行し、0 を返します。  
  
### <a name="remarks"></a>コメント  
 所有するメニュー バーに属しているメニュー項目のイメージの描画をカスタマイズする場合は、このメソッドをオーバーライド、 `COleIPFrameWndEx`-派生オブジェクト。  
  
##  <a name="ondrawmenulogo"></a>COleIPFrameWndEx::OnDrawMenuLogo  
 フレームワークによって呼び出されますときに、 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)プロセスのオブジェクト、`WM_PAINT`メッセージです。  
  
```  
virtual void OnDrawMenuLogo(
    CDC* pDC,  
    CMFCPopupMenu* pMenu,  
    const CRect& rectLogo);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `pMenu`  
 ポップアップ メニュー オブジェクトへのポインター。  
  
 [入力] `rectLogo`  
 表示するロゴへのポインター。  
  
### <a name="remarks"></a>コメント  
 所有するメニュー バーに関連付けられている、ポップアップ メニューにロゴを表示するには、このメソッドをオーバーライドして、 `COleIPFrameWndEx`-派生オブジェクト。 既定の実装では、何も行われません。  
  
##  <a name="onmenubuttontoolhittest"></a>COleIPFrameWndEx::OnMenuButtonToolHitTest  
 フレームワークによって呼び出されますときに、 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)プロセスのオブジェクト、`WM_NCHITTEST`メッセージです。  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>パラメーター  
 [in] pButton  
 メニュー ボタンへのポインター。  
  
 [out] pTI  
 `TOOLINFO` 構造体へのポインター。  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、何も実行し、0 を返します。 塗りつぶす場合に、実装が&0; 以外の値を返す必要があります、`pTI`パラメーター。  
  
### <a name="remarks"></a>コメント  
 特定のメニュー項目のツールヒント情報を提供するには、このメソッドをオーバーライドします。  
  
##  <a name="onmoveminiframe"></a>COleIPFrameWndEx::OnMoveMiniFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pFrame`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onsetpreviewmode"></a>COleIPFrameWndEx::OnSetPreviewMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bPreview`  
 [入力] `pState`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshowcustomizepane"></a>COleIPFrameWndEx::OnShowCustomizePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenuPane`  
 [入力] `uiToolbarID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshowpanes"></a>COleIPFrameWndEx::OnShowPanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshowpopupmenu"></a>COleIPFrameWndEx::OnShowPopupMenu  
 ポップアップ メニューが表示されたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] pMenuPopup`  
 表示されるポップアップ メニューへのポインター。  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、何も実行し、0 以外の値を返します。 実装を返す必要があります`FALSE`ポップアップ メニューを表示できない場合。  
  
### <a name="remarks"></a>コメント  
 ポップアップ メニューの表示をカスタマイズするには、このメソッドをオーバーライドします。 たとえば、色のメニュー項目をメニュー ボタンを変更したり、ティアオフ バーを初期化できます。  
  
##  <a name="ontearoffmenu"></a>COleIPFrameWndEx::OnTearOffMenu  
 ティアオフ バーを持つメニューを選択すると、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenuPopup`  
 ユーザーが選択したポップアップ メニューへのポインター。  
  
 [入力] `pBar`  
 メニューをホストするウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ポップアップ メニューをアクティブにする場合それ以外の場合`FALSE`します。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
 ティアオフ バーの設定をカスタマイズする場合は、この関数をオーバーライドします。  
  
##  <a name="panefrompoint"></a>COleIPFrameWndEx::PaneFromPoint  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 [入力] `nSensitivity`  
 [入力] `bExactBar`  
 [入力] `pRTCBarType`  
 [入力] `dwAlignment`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="pretranslatemessage"></a>COleIPFrameWndEx::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMsg`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="recalclayout"></a>COleIPFrameWndEx::RecalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bNotify`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removepanefromdockmanager"></a>COleIPFrameWndEx::RemovePaneFromDockManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 [入力] `bDestroy`  
 [入力] `bAdjustLayout`  
 [入力] `bAutoHide`  
 [入力] `pBarReplacement`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setdockstate"></a>COleIPFrameWndEx::SetDockState  
 フレーム ウィンドウに属するペインには、指定したドッキング状態を適用します。  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `state`  
 ドッキング状態を指定します。  
  
### <a name="remarks"></a>コメント  
 この関数に属しているペインの新しいドッキング状態の指定を使用して、`COleIPFrameWndEx`オブジェクトです。  
  
##  <a name="setuptoolbarmenu"></a>COleIPFrameWndEx::SetupToolbarMenu  
 ダミーの項目を検索して、指定されたユーザー定義の項目で置き換えることで、ツールバーのオブジェクトを変更します。  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `menu`  
 参照、 [CMenu](../../mfc/reference/cmenu-class.md)オブジェクトを変更できます。  
  
 [入力] `uiViewUserToolbarCmdFirst`  
 ユーザー定義の最初のコマンドを指定します。  
  
 [入力] `uiViewUserToolbarCmdLast`  
 ユーザー定義の最後のコマンドを指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="showpane"></a>COleIPFrameWndEx::ShowPane  
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
  
##  <a name="winhelpa"></a>COleIPFrameWndEx::WinHelpA  
 WinHelp アプリケーションまたはコンテキスト ヘルプを起動するために、フレームワークによって呼び出されます。  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] dwData  
 `nCmd`で指定されたヘルプの種類に必要とされるデータを指定します。  
  
 [入力] `nCmd`  
 要求されるヘルプの種類を指定します。 有効な値の一覧と `dwData` パラメーターに与える影響については、Windows SDK の「 [WinHelp 関数](http://msdn.microsoft.com/library/windows/desktop/bb762267) 」を参照してください。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)   
 [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)

