---
title: "CMDIFrameWndEx クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIFrameWndEx.AddDockSite
- CMDIFrameWndEx
- CMDIFrameWndEx::AddDockSite
dev_langs:
- C++
helpviewer_keywords:
- CMDIFrameWndEx class
ms.assetid: dbcafcb3-9a7a-4f11-9dfe-ba57565c81d0
caps.latest.revision: 42
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
ms.openlocfilehash: b9946f59b9ed789604ac6a02d2148188831bae56
ms.lasthandoff: 02/24/2017

---
# <a name="cmdiframewndex-class"></a>CMDIFrameWndEx クラス
機能を拡張[CMDIFrameWnd](../../mfc/reference/cframewnd-class.md)Windows のマルチ ドキュメント インターフェイス (MDI) のフレーム ウィンドウです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMDIFrameWndEx : public CMDIFrameWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMDIFrameWndEx::ActiveItemRecalcLayout](#activeitemrecalclayout)|アクティブな項目のレイアウトを再計算します。|  
|`CMDIFrameWndEx::AddDockSite`|このメソッドは使用されません。|  
|[CMDIFrameWndEx::AddPane](#addpane)|ペインをドッキング マネージャーに登録します。|  
|[CMDIFrameWndEx::AdjustClientArea](#adjustclientarea)|飾り枠に許可するようにクライアント領域が減少します。|  
|[CMDIFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)|すべてのドッキング ペインのレイアウトを再計算します。|  
|[CMDIFrameWndEx::AreMDITabs](#aremditabs)|MDI タブ機能または MDI タブ付きグループ機能が有効かどうかを決定します。|  
|[CMDIFrameWndEx::CanCovertControlBarToMDIChild](#cancovertcontrolbartomdichild)|フレーム ウィンドウがドッキング ペインをタブ付きドキュメントに変換できるかどうかを調べるためにフレームワークによって呼び出されます。|  
|[CMDIFrameWndEx::ControlBarToTabbedDocument](#controlbartotabbeddocument)|指定したドッキング ペインをタブ付きドキュメントに変換します。|  
|[CMDIFrameWndEx::CreateDocumentWindow](#createdocumentwindow)|子ドキュメント ウィンドウを作成します。|  
|[CMDIFrameWndEx::CreateNewWindow](#createnewwindow)|新しいウィンドウを作成するためにフレームワークによって呼び出されます。|  
|`CMDIFrameWndEx::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMDIFrameWndEx::DockPane](#dockpane)|フレーム ウィンドウに、指定したウィンドウをドッキングします。|  
|[CMDIFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|ウィンドウを別のウィンドウの左側にドッキングします。|  
|[CMDIFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)|により自動的に隠すモードのペインのメイン フレーム ウィンドウの指定した辺にドッキングされている場合。|  
|[CMDIFrameWndEx::EnableDocking](#enabledocking)|MDI フレーム ウィンドウに属するペインのドッキングを有効にします。|  
|[CMDIFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu)|全画面表示モードでのメイン メニューの表示と非表示を切り替えます。|  
|[CMDIFrameWndEx::EnableFullScreenMode](#enablefullscreenmode)|フレーム ウィンドウの全画面表示モードを有効にします。|  
|[CMDIFrameWndEx::EnableLoadDockState](#enableloaddockstate)|有効またはドッキング状態の読み込みを無効にします。|  
|[CMDIFrameWndEx::EnableMDITabbedGroups](#enablemditabbedgroups)|有効または MDI タブ付きグループ機能を無効にします。|  
|[CMDIFrameWndEx::EnableMDITabs](#enablemditabs)|有効または MDI タブ機能を無効にします。 有効にすると、フレーム ウィンドウには、各 MDI 子ウィンドウのタブが表示されます。|  
|[CMDIFrameWndEx::EnableMDITabsLastActiveActivation](#enablemditabslastactiveactivation)|ユーザーが現在のタブを閉じるときに、最後のアクティブなタブをアクティブ化するかどうかを指定します。|  
|[CMDIFrameWndEx::EnablePaneMenu](#enablepanemenu)|有効またはアプリケーション ウィンドウの一覧に表示されるポップアップ ウィンドウのメニューの自動作成と管理を無効にします。  をクリックします。|  
|[CMDIFrameWndEx::EnableWindowsDialog](#enablewindowsdialog)|コマンド ID を持つを呼び出すメニュー項目を挿入、 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)  ダイアログ ボックス。|  
|[CMDIFrameWndEx::GetActivePopup](#getactivepopup)|現在表示されているポップアップ メニューへのポインターを返します。|  
|[CMDIFrameWndEx::GetPane](#getpane)|指定したコントロールの ID を持つペインへのポインターを返します|  
|[CMDIFrameWndEx::GetDefaultResId](#getdefaultresid)|MDI フレーム ウィンドウの共有リソースの ID を返します。|  
|[CMDIFrameWndEx::GetMDITabGroups](#getmditabgroups)|タブ付きウィンドウの MDI の一覧を返します。|  
|[CMDIFrameWndEx::GetMDITabs](#getmditabs)|下線付きのタブ付きウィンドウへの参照を返します。|  
|[CMDIFrameWndEx::GetMDITabsContextMenuAllowedItems](#getmditabscontextmenualloweditems)|MDI タブ付きグループ機能が有効になっている場合に、どのようなコンテキスト メニュー項目が有効かを示すフラグの組み合わせを返します。|  
|[CMDIFrameWndEx::GetMenuBar](#getmenubar)|メニュー バー オブジェクトが接続されているフレーム ウィンドウへのポインターを返します。|  
|[CMDIFrameWndEx::GetRibbonBar](#getribbonbar)|フレームのリボン バー コントロールを取得します。|  
|[CMDIFrameWndEx::GetTearOffBars](#gettearoffbars)|一覧を返す[CPane](../../mfc/reference/cpane-class.md)-ティアオフ状態にあるオブジェクトを派生します。|  
|`CMDIFrameWndEx::GetThisClass`|ポインターを取得するためにフレームワークによって呼び出される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMDIFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|アプリケーション ツールバーのボタンのツールヒントを表示するときに、フレームワークによって呼び出されます。|  
|[CMDIFrameWndEx::InsertPane](#insertpane)|指定したウィンドウをドッキング マネージャーに登録します。|  
|[CMDIFrameWndEx::IsFullScreen](#isfullscreen)|フレーム ウィンドウが全画面表示モードになっているかどうかを判断します。|  
|[CMDIFrameWndEx::IsMDITabbedGroup](#ismditabbedgroup)|MDI タブ付きグループ機能が有効になっているかどうかを決定します。|  
|[CMDIFrameWndEx::IsMemberOfMDITabGroup](#ismemberofmditabgroup)|指定したタブ付きウィンドウが MDI タブ付きグループに含まれるウィンドウのリストかどうかを判断します。|  
|[CMDIFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|フレーム ウィンドウにメニュー バーがあるかどうかを決定します。|  
|[CMDIFrameWndEx::IsPointNearDockSite](#ispointneardocksite)|指定した点がドッキング サイトの近くにいるかどうかを判断します。|  
|[CMDIFrameWndEx::IsPrintPreview](#isprintpreview)|フレーム ウィンドウが印刷プレビュー モードになっているかどうかを判断します。|  
|[CMDIFrameWndEx::LoadFrame](#loadframe)|リソースの情報からフレーム ウィンドウを作成します。 (`CMDIFrameWnd::LoadFrame` をオーバーライドします)。|  
|[CMDIFrameWndEx::LoadMDIState](#loadmdistate)|MDI タブ付きグループの指定されたレイアウトと以前に開いたドキュメントの一覧を読み込みます。|  
|[CMDIFrameWndEx::MDITabMoveToNextGroup](#mditabmovetonextgroup)|アクティブなタブを現在アクティブなタブ付きウィンドウから次または前のタブ付きグループに移動します。|  
|[CMDIFrameWndEx::MDITabNewGroup](#mditabnewgroup)|1 つのウィンドウを持つ新しいタブ付きグループを作成します。|  
|[CMDIFrameWndEx::NegotiateBorderSpace](#negotiateborderspace)|フレーム ウィンドウの境界領域は、OLE、インプレース アクティブ化時にネゴシエートします。|  
|[CMDIFrameWndEx::OnCloseDockingPane](#onclosedockingpane)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**閉じる**[ドッキング可能ウィンドウ] ボタンをクリックします。|  
|[CMDIFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**閉じる**浮動ミニフレーム ウィンドウのボタンをクリックします。|  
|[CMDIFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|アクティブなポップアップ メニューを処理するときに、フレームワークによって呼び出され、`WM_DESTROY`メッセージです。|  
|[CMDIFrameWndEx::OnCmdMsg](#oncmdmsg)|コマンド メッセージをディスパッチするため、コマンドのユーザー インターフェイス オブジェクトを更新するために framework によって呼び出されます。|  
|[CMDIFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|メニュー項目に関連付けられているイメージが描画されるときに、フレームワークによって呼び出されます。|  
|[CMDIFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|フレームワークによって呼び出されるときに、 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)プロセス、`WM_PAINT`メッセージです。|  
|[CMDIFrameWndEx::OnEraseMDIClientBackground](#onerasemdiclientbackground)|MDI フレーム ウィンドウのプロセス時にフレームワークによって呼び出さ、`WM_ERASEBKGND`メッセージです。|  
|[CMDIFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|フレームワークによって呼び出されますときに、 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)プロセスのオブジェクト、`WM_NCHITTEST`メッセージです。|  
|[CMDIFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)|ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。|  
|[CMDIFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|アプリケーションのメイン フレーム ウィンドウの 印刷プレビュー モードを設定します。 (上書き[CFrameWnd::OnSetPreviewMode](../../mfc/reference/cframewnd-class.md#onsetpreviewmode))。|  
|[CMDIFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)|簡易カスタマイズ ペインがアクティブになったときに、フレームワークによって呼び出されます。|  
|[CMDIFrameWndEx::OnShowMDITabContextMenu](#onshowmditabcontextmenu)|タブのいずれかのコンテキスト メニューを表示する必要があるときに、フレームワークによって呼び出されます。 (MDI タブ付きグループのみに有効です。)|  
|[CMDIFrameWndEx::OnShowPanes](#onshowpanes)|ペインを非表示を切り替えるために、フレームワークによって呼び出されます。|  
|[CMDIFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|ポップアップ メニューがアクティブにされるときにフレームワークによって呼び出されます。|  
|[CMDIFrameWndEx::OnSizeMDIClient](#onsizemdiclient)|クライアントの MDI ウィンドウのサイズを変更するときに、フレームワークによって呼び出されます。|  
|[CMDIFrameWndEx::OnTearOffMenu](#ontearoffmenu)|ティアオフ バーのあるメニューがアクティブ化されるときにフレームワークによって呼び出されます。|  
|[CMDIFrameWndEx::OnUpdateFrameMenu](#onupdateframemenu)|フレームのメニューを更新するためにフレームワークによって呼び出されます。 (`CMDIFrameWnd::OnUpdateFrameMenu` をオーバーライドします)。|  
|[CMDIFrameWndEx::PaneFromPoint](#panefrompoint)|指定したポイントを含むドッキング ペインを返します。|  
|`CMDIFrameWndEx::PreTranslateMessage`|クラスで使用される[CWinApp](../../mfc/reference/cwinapp-class.md)にディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数です。  (`CMDIFrameWnd::PreTranslateMessage` をオーバーライドします)。|  
|[CMDIFrameWndEx::RecalcLayout](#recalclayout)|フレーム ウィンドウのレイアウトを再計算するためにフレームワークによって呼び出されます。 (上書き[表示](../../mfc/reference/cframewnd-class.md#recalclayout))。|  
|[CMDIFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|ペインの登録を解除し、ドッキング マネージャーから削除されます。|  
|[CMDIFrameWndEx::SaveMDIState](#savemdistate)|MDI タブ付きグループの現在のレイアウトと以前に開いたドキュメントの一覧を保存します。|  
|[CMDIFrameWndEx::SetPrintPreviewFrame](#setprintpreviewframe)|印刷プレビューのフレーム ウィンドウを設定します。|  
|[CMDIFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|ダミーの項目を検索して、指定されたユーザー定義の項目で置き換えることで、ツールバーのオブジェクトを変更します。|  
|[CMDIFrameWndEx::ShowFullScreen](#showfullscreen)|全画面表示モードを通常モードからメイン フレームを切り替えます。|  
|[CMDIFrameWndEx::ShowPane](#showpane)|指定したウィンドウの表示と非表示を切り替えます。|  
|[CMDIFrameWndEx::ShowWindowsDialog](#showwindowsdialog)|作成、 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)ボックスを開きます。|  
|[CMDIFrameWndEx::TabbedDocumentToControlBar](#tabbeddocumenttocontrolbar)|ドッキング ペインに、指定したタブ付きドキュメントを変換します。|  
|[CMDIFrameWndEx::UpdateCaption](#updatecaption)|ウィンドウ フレームのキャプションを更新するためにフレームワークによって呼び出されます。|  
|[CMDIFrameWndEx::UpdateMDITabbedBarsIcons](#updatemditabbedbarsicons)|各 MDI タブ付きペインのアイコンを設定します。|  
|[CMDIFrameWndEx::WinHelp](#winhelp)|WinHelp アプリケーションまたはコンテキスト ヘルプを起動するために、フレームワークによって呼び出されます。 (上書き[CWnd::WinHelp](../../mfc/reference/cwnd-class.md#winhelp))。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMDIFrameWndEx::m_bCanCovertControlBarToMDIChild](#m_bcancovertcontrolbartomdichild)|MDI 子ウィンドウのドッキング ペインを変換できるかどうかを決定します。|  
|[CMDIFrameWndEx::m_bDisableSetRedraw](#m_bdisablesetredraw)|有効または MDI 子ウィンドウの再描画を最適化を無効にします。|  
  
## <a name="remarks"></a>コメント  
 MDI アプリケーションでの拡張のカスタマイズ機能を利用するからアプリケーションの MDI フレーム ウィンドウ クラスを派生させる`CMDIFrameWndEx`の代わりに`CMDIFrameWnd`します。  
  
## <a name="example"></a>例  
 次の例からクラスを派生する`CMDIFrameWndEx`です。 このコード スニペットは、 [DrawClient サンプル: MFC Ribbon-Based OLE オブジェクトの描画アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_DrawClient&#1;](../../mfc/reference/codesnippet/cpp/cmdiframewndex-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)  
  
 [CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxMDIFrameWndEx.h  
  
##  <a name="a-nameactiveitemrecalclayouta--cmdiframewndexactiveitemrecalclayout"></a><a name="activeitemrecalclayout"></a>CMDIFrameWndEx::ActiveItemRecalcLayout  
 アクティブな項目のレイアウトを再計算します。  
  
```  
void ActiveItemRecalcLayout();
```  
  
##  <a name="a-nameaddpanea--cmdiframewndexaddpane"></a><a name="addpane"></a>CMDIFrameWndEx::AddPane  
 ペインをドッキング マネージャーに登録します。  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
 登録するペインへのポインター。  
  
 [入力] `bTail`  
 このペインをリストの末尾に追加するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが正常に登録されている場合は、0 以外の値を返します。 ウィンドウがドッキング マネージャーに既に登録されている場合は、0 を返します。  
  
### <a name="remarks"></a>コメント  
 各ウィンドウに登録する必要があります、 [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)前に、ドッキング レイアウトの一部がかかることができます。 このメソッドを使用すると、特定のペインをドッキングするドッキング マネージャーに通知します。 そのウィンドウが登録されると、配置の設定とドッキングのマネージャーによって管理されるウィンドウのリスト内の位置に基づき、ドッキング マネージャーが揃えて配置します。  
  
##  <a name="a-nameadjustclientareaa--cmdiframewndexadjustclientarea"></a><a name="adjustclientarea"></a>CMDIFrameWndEx::AdjustClientArea  
 飾り枠に許可するようにクライアント領域が減少します。  
  
```  
virtual void AdjustClientArea();
```  
  
##  <a name="a-nameadjustdockinglayouta--cmdiframewndexadjustdockinglayout"></a><a name="adjustdockinglayout"></a>CMDIFrameWndEx::AdjustDockingLayout  
 すべてのドッキング ペインのレイアウトを再計算します。  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hdwp`  
 複数ウィンドウ位置構造体を識別します。 この値を入手するにを呼び出して`BeginDeferWindowPos`します。  
  
### <a name="remarks"></a>コメント  
 フレーム ウィンドウにドッキングされているすべてのウィンドウのレイアウトを再計算するには、このメンバー関数を呼び出します。  
  
##  <a name="a-namearemditabsa--cmdiframewndexaremditabs"></a><a name="aremditabs"></a>CMDIFrameWndEx::AreMDITabs  
 MDI タブ機能または MDI タブ付きグループ機能が有効かどうかを決定します。  
  
```  
BOOL AreMDITabs(int* pnMDITabsType=NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `pnMDITabsType`  
 どの機能が有効になっていることを示す整数の変数へのポインター。  
  
-   0: すべての機能を無効にします。  
  
-   1: MDI タブが有効にします。  
  
-   2: MDI タブ付きグループを有効にします。  
  
### <a name="return-value"></a>戻り値  
 `Returns TRUE`MDI タブまたは MDI タブ付きグループは有効です。  
  
 `Returns FALSE`場合は、上記の機能は有効です。  
  
### <a name="remarks"></a>コメント  
 フレーム ウィンドウの MDI タブまたは MDI のタブ グループかどうかを判断するには、この関数が有効に使用します。 使用[CMDIFrameWndEx::EnableMDITabs](#enablemditabs)有効または MDI タブ機能を無効にします。  
  
 使用[CMDIFrameWndEx::EnableMDITabbedGroups](#enablemditabbedgroups)有効または MDI タブ付きグループ機能を無効にします。  
  
##  <a name="a-namecancovertcontrolbartomdichilda--cmdiframewndexcancovertcontrolbartomdichild"></a><a name="cancovertcontrolbartomdichild"></a>CMDIFrameWndEx::CanCovertControlBarToMDIChild  
 フレーム ウィンドウがドッキング ペインをタブ付きドキュメントに変換できるかどうかを調べるためにフレームワークによって呼び出されます  
  
```  
virtual BOOL CanCovertControlBarToMDIChild();
```  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`フレーム ウィンドウはドッキング ペインをタブ付きドキュメントに変換できる場合、それ以外の場合を返します`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 派生クラスでは、このメソッドをオーバーライドし、返す`TRUE`ドッキング ペインをタブ付きドキュメントへの変換を有効にします。 また、設定[CMDIFrameWndEx::m_bCanCovertControlBarToMDIChild](#m_bcancovertcontrolbartomdichild)に`TRUE`します。  
  
##  <a name="a-namecontrolbartotabbeddocumenta--cmdiframewndexcontrolbartotabbeddocument"></a><a name="controlbartotabbeddocument"></a>CMDIFrameWndEx::ControlBarToTabbedDocument  
 指定したドッキング ペインをタブ付きドキュメントに変換します。  
  
```  
virtual CMDIChildWndEx* ControlBarToTabbedDocument(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBar`  
 変換するドッキング ペインへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ドッキング ペインを含む新しい MDI 子ウィンドウへのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ドッキング ペインをタブ付きドキュメントに変換します。 このメソッドを呼び出すときに、フレームワークを作成、 [CMDIChildWndEx クラス](../../mfc/reference/cmdichildwndex-class.md)オブジェクト、ドッキング ペインをドッキング マネージャーから削除し、新しい MDI 子ウィンドウにドッキング ペインを追加します。 MDI 子ウィンドウがクライアント領域全体をカバーするドッキング ペインをサイズ変更します。  
  
##  <a name="a-namecreatedocumentwindowa--cmdiframewndexcreatedocumentwindow"></a><a name="createdocumentwindow"></a>CMDIFrameWndEx::CreateDocumentWindow  
 子ドキュメント ウィンドウを作成します。  
  
```  
virtual CMDIChildWndEx* CreateDocumentWindow(
    LPCTSTR lpcszDocName,  
    CObject* pObj);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpcszDocName`  
 ドキュメント識別子を表すテキスト文字列。 通常、ドキュメント ファイルの完全なパスです。  
  
 [入力] `pObj`  
 ユーザー定義のオブジェクトへのポインター。 たとえば、開発者は、ドキュメントの説明とドキュメントを起動時に初期化する方法を示す、アプリケーション固有のデータ構造を作成できます。  
  
### <a name="return-value"></a>戻り値  
 ポインター`CMDIChildWndEx`します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、レジストリに保存されているドキュメントの一覧の読み込み時に、このメソッドを呼び出します。  
  
 レジストリから読み込まれている場合は、ドキュメントを作成するために、このメソッドをオーバーライドします。  
  
### <a name="example"></a>例  
 例を次にどのように`CreateDocumentWindow`で使用される、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 この例では`g_strStartViewName`ドキュメントの名前、"仮想"(たとえば、スタート ページに") がディスク ファイルから実際にロードされていない可能性があります。 そのため、ケースを処理する特別な処理が必要です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#13;](../../mfc/codesnippet/cpp/cmdiframewndex-class_2.cpp)]  
  
##  <a name="a-namecreatenewwindowa--cmdiframewndexcreatenewwindow"></a><a name="createnewwindow"></a>CMDIFrameWndEx::CreateNewWindow  
 新しいウィンドウを作成するためにフレームワークによって呼び出されます。  
  
```  
virtual CMDIChildWndEx* CreateNewWindow(
    LPCTSTR lpcszDocName,  
    CObject* pObj);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpcszDocName`  
 ドキュメントの名前。  
  
 [入力] `pObj`  
 将来使用するために予約されています。  
  
### <a name="return-value"></a>戻り値  
 新しいウィンドウへのポインター。  
  
##  <a name="a-namedockpanea--cmdiframewndexdockpane"></a><a name="dockpane"></a>CMDIFrameWndEx::DockPane  
 フレーム ウィンドウに、指定したウィンドウをドッキングします。  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID=0,  
    LPCRECT lpRect=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 ドッキングするのには、ウィンドウへのポインター。  
  
 [入力] `nDockBarID`  
 フレーム ウィンドウにドッキングするのどの辺を指定します。  
  
 [入力] `lpRect`  
 使用しません。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、指定されたドッキング ウィンドウがフレーム ウィンドウの辺のいずれかに時に指定された[CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)と[CMDIFrameWndEx::EnableDocking](#enabledocking)と呼ばれていました。  
  
### <a name="example"></a>例  
 `DockPane` メソッドの使用例を次に示します。 このコード スニペットに由来、 [VisualStudioDemo サンプル: MFC の Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&4;](../../mfc/codesnippet/cpp/cmdiframewndex-class_3.cpp)]  
  
##  <a name="a-namedockpaneleftofa--cmdiframewndexdockpaneleftof"></a><a name="dockpaneleftof"></a>CMDIFrameWndEx::DockPaneLeftOf  
 ウィンドウを別のウィンドウの左側にドッキングします。  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 ドッキング ペインへのポインター。  
  
 [入力] `pLeftOf`  
 ドッキング サイトとして機能する、ウィンドウへのポインター。 をクリックします。  
  
### <a name="return-value"></a>戻り値  
 返します。 `TRUE` 、操作が成功した場合。 それ以外の場合は、`FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
 事前定義された順序で複数のペインのオブジェクトをドッキングするには、このメソッドを呼び出します。 このメソッドで指定されたウィンドウのドッキング`pBar`で指定されたウィンドウの左側に`pLeftOf`します。  
  
### <a name="example"></a>例  
 例を次に、どのように`DockPaneLeftOf`を使用する方法、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#5;](../../mfc/codesnippet/cpp/cmdiframewndex-class_4.cpp)]  
  
##  <a name="a-nameenableautohidepanesa--cmdiframewndexenableautohidepanes"></a><a name="enableautohidepanes"></a>CMDIFrameWndEx::EnableAutoHidePanes  
 により自動的に隠すモードのペインのメイン フレーム ウィンドウの指定した辺にドッキングされている場合。  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwDockStyle`  
 有効にするメイン フレーム ウィンドウの辺を指定します。 次のフラグの&1; つ以上を使用します。  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
### <a name="return-value"></a>戻り値  
 メイン フレーム ウィンドウの指定した辺にドッキングされている場合は、ウィンドウの自動非表示モードを有効にするには、この関数を呼び出します。  
  
### <a name="example"></a>例  
 例を次に、どのように`EnableAutoHidePanes`を使用する方法、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&6;](../../mfc/codesnippet/cpp/cmdiframewndex-class_5.cpp)]  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameenabledockinga--cmdiframewndexenabledocking"></a><a name="enabledocking"></a>CMDIFrameWndEx::EnableDocking  
 MDI フレーム ウィンドウに属するペインのドッキングを有効にします。  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwDockStyle`  
 適用するドッキング スタイルを指定します。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 属するペインのドッキングを有効にするには、この関数を呼び出して、`CMDIFrameWndEx`オブジェクトです。  
  
### <a name="example"></a>例  
 例を次に、どのように`EnableDocking`を使用する方法、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#7;](../../mfc/codesnippet/cpp/cmdiframewndex-class_6.cpp)]  
  
##  <a name="a-nameenablefullscreenmainmenua--cmdiframewndexenablefullscreenmainmenu"></a><a name="enablefullscreenmainmenu"></a>CMDIFrameWndEx::EnableFullScreenMainMenu  
 全画面表示モードでのメイン メニューの表示と非表示を切り替えます。  
  
```  
void EnableFullScreenMainMenu(BOOL bEnableMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnableMenu`  
 `TRUE`全画面表示モードで、メイン メニューを表示するか、`FALSE`非表示にします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameenablefullscreenmodea--cmdiframewndexenablefullscreenmode"></a><a name="enablefullscreenmode"></a>CMDIFrameWndEx::EnableFullScreenMode  
 フレーム ウィンドウの全画面表示モードを有効にします。  
  
```  
void EnableFullScreenMode(UINT uiFullScreenCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiFullScreenCmd`  
 または全画面表示モードを無効にするコマンドの ID。  
  
### <a name="remarks"></a>コメント  
 全画面表示モードですべてのドッキング コントロール バー、ツールバーとメニューが非表示になりに全画面表示の上にアクティブなビューのサイズを変更します。全画面表示モードを有効にすると、有効または無効にするコマンドの ID を指定する必要があります。 呼び出すことができます`EnableFullScreenMode`からメインフレームの`OnCreate`関数です。 フレーム ウィンドウを全画面表示モードに切り替わる、ときにフレームワークには、指定されたコマンド ID を持つ&1; つのボタンとフローティング ツールバーを作成します。画面にメインのメニューを保持する場合は、呼び出す[CMDIFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu)します。  
  
##  <a name="a-nameenableloaddockstatea--cmdiframewndexenableloaddockstate"></a><a name="enableloaddockstate"></a>CMDIFrameWndEx::EnableLoadDockState  
 有効またはドッキング状態の読み込みを無効にします。  
  
```  
void EnableLoadDockState(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`ドッキング状態の読み込みを有効にする`FALSE`ドッキング状態の読み込みを無効にします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameenablemditabbedgroupsa--cmdiframewndexenablemditabbedgroups"></a><a name="enablemditabbedgroups"></a>CMDIFrameWndEx::EnableMDITabbedGroups  
 有効またはフレーム ウィンドウの MDI タブ付きグループ機能を無効にします。  
  
```  
void EnableMDITabbedGroups(
    BOOL bEnable,  
    const CMDITabInfo& params);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 場合`TRUE`、MDI タブ付きグループ機能が有効な場合は`FALSE`、MDI タブ付きグループ機能を無効にします。  
  
 [入力] `params`  
 MDI クライアント領域で作成された子ウィンドウに、フレームワークを適用するパラメーターを指定します。  
  
### <a name="remarks"></a>コメント  
 有効または MDI タブ付きグループ機能を無効にするには、このメソッドを使用します。 この機能は、垂直方向に調整されているタブ付きウィンドウとして、または MDI クライアント領域内で水平方向には、子ウィンドウを表示する MDI アプリケーションを使用します。 タブ付きウィンドウのグループは、スプリッターで区切られます。 ユーザーは、スプリッターを使用して、タブ付きグループのサイズを変更できます。  
  
-   ユーザーが実行できます。  
  
-   グループ間で個々 のタブをドラッグします。  
  
-   新しいグループを作成するウィンドウの端に個々 のタブをドラッグします。  
  
-   タブを移動またはショートカット メニューを使用して、新しいグループを作成します。  
  
-   アプリケーションには、タブ付きウィンドウの現在のレイアウトおよび現在開いているドキュメントの一覧を保存できます。  
  
 このメソッドを呼び出す場合`bEnable`に設定`FALSE`、`params`は無視されます。  
  
 MDI タブ付きグループが既に有効になっている場合でも、子ウィンドウの設定を変更するには、もう一度このメソッドを呼び出すことができます。 使用してメソッドを呼び出す`bEnable`に設定`TRUE`のメンバーを変更し、`CMDITabInfo`で指定されているオブジェクト、`params`パラメーター。  
  
 タブ付きグループを MDI で使用する方法の詳細についてを参照してください[MDI タブ付きグループ](../../mfc/mdi-tabbed-groups.md)します。  
  
### <a name="example"></a>例  
 例を次にどのように`EnableMDITabbedGroups`で使用される、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#8;](../../mfc/codesnippet/cpp/cmdiframewndex-class_7.cpp)]  
  
##  <a name="a-nameenablemditabsa--cmdiframewndexenablemditabs"></a><a name="enablemditabs"></a>CMDIFrameWndEx::EnableMDITabs  
 有効または MDI フレーム ウィンドウの MDI タブ機能を無効にします。 有効にすると、フレーム ウィンドウには、各 MDI 子ウィンドウのタブが表示されます。  
  
```  
void EnableMDITabs(
    BOOL bEnable=TRUE,  
    BOOL bIcons=TRUE,  
    CMFCTabCtrl::Location tabLocation=CMFCTabCtrl::LOCATION_BOTTOM,  
    BOOL bTabCloseButton=FALSE,  
    CMFCTabCtrl::Style style=CMFCTabCtrl::STYLE_3D_SCROLLED,  
    BOOL bTabCustomTooltips=FALSE,  
    BOOL bActiveTabCloseButton=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 タブが有効になっているかどうかを指定します。  
  
 `bIcons`  
 タブにアイコンを表示する必要があるかどうかを指定します。  
  
 `tabLocation`  
 タブ ラベルの場所を指定します。  
  
 `bTabCloseButton`  
 タブを閉じるボタンを表示するかどうかを指定します。  
  
 `style`  
 タブのスタイルを指定します。 使用`STYLE_3D_SCROLLED`の通常のタブまたは`STYLE_3D_ONENOTE`Microsoft OneNote のタブにします。  
  
 `bTabCustomTooltips`  
 カスタム ツール ヒントが有効になっているかどうかを指定します。  
  
 `bActiveTabCloseButton`  
 場合`TRUE`、**閉じる**タブ領域の右上隅にアクティブなタブの代わりにボタンが表示されます。  
  
### <a name="remarks"></a>コメント  
 有効にする、または MDI フレーム ウィンドウの MDI タブの機能を無効にするには、このメソッドを呼び出します。 有効な場合、すべての子ウィンドウがタブとして表示されます。  
  
 タブ ラベルは、上またはパラメーターの設定に応じて、フレームの下部に配置することも`tabLocation`です。 どちらかを指定することがあります`CMFCTabCtrl::LOCATION_BOTTOM`(既定の設定) または`CMFCTabCtrl::LOCATION_TOP`です。  
  
 場合`bTabCustomTooltips`は`TRUE`、`AFX_WM_ON_GET_TAB_TOOLTIP`メッセージをメイン フレーム ウィンドウに送信されます。 コードでは、このメッセージを処理して、MDI タブのカスタム ツール ヒントを提供することができます。  
  
### <a name="example"></a>例  
 例を次にどのように`EnableMDITabs`で使用される、 [MDITabsDemo サンプル: MFC タブ付き MDI アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#3;](../../mfc/reference/codesnippet/cpp/cmdiframewndex-class_8.cpp)]  
  
##  <a name="a-nameenablemditabslastactiveactivationa--cmdiframewndexenablemditabslastactiveactivation"></a><a name="enablemditabslastactiveactivation"></a>CMDIFrameWndEx::EnableMDITabsLastActiveActivation  
 ユーザーが現在のタブを閉じるときに、最後のアクティブなタブを開く必要があるかどうかを指定します。  
  
```  
void EnableMDITabsLastActiveActivation(BOOL bLastActiveTab=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bLastActiveTab`  
 場合`TRUE`、最後のアクティブなタブのライセンス認証を有効にします。 場合`FALSE`、最後のアクティブなタブのアクティブ化を無効にします。  
  
### <a name="remarks"></a>コメント  
 タブを開き、アクティブなタブが閉じられたときに&2; つの方法があります。  
  
-   次のタブがアクティブにします。  
  
-   前のアクティブなタブを有効にします。  
  
 既定の実装では、最初の方法を使用します。  
  
 使用`EnableMDITabsLastActiveActivation`タブのアクティブ化の&2; 番目の方法を有効にします。 Windows が MDI 子ウィンドウを開く方法をエミュレートします。  
  
##  <a name="a-nameenablepanemenua--cmdiframewndexenablepanemenu"></a><a name="enablepanemenu"></a>CMDIFrameWndEx::EnablePaneMenu  
 有効またはアプリケーション ウィンドウの一覧に表示されるポップアップ ウィンドウのメニューの自動作成と管理を無効にします。  
  
```  
void EnablePaneMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeLabel,  
    UINT uiViewToolbarsMenuEntryID,  
    BOOL bContextMenuShowsToolbarsOnly=FALSE,  
    BOOL bViewMenuShowsToolbarsOnly=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 場合`TRUE`、ウィンドウのメニューの自動処理が有効な場合は`FALSE`、自動処理が無効になっています。  
  
 [入力] `uiCustomizeCmd`  
 コマンドの ID、**カスタマイズ**メニュー項目です。 このメニュー項目は通常、ペインの一覧の末尾に追加します。  
  
 [入力] `strCustomizeLabel`  
 表示されるテキスト、**カスタマイズ**(ローカリゼーション) のためのメニュー項目です。  
  
 [入力] `uiViewToolbarsMenuEntryID`  
 ウィンドウ メニューを開くツール バー メニュー項目の ID を指定します。 これは通常、**ツールバー**のサブメニュー、**ビュー**メニュー。  
  
 [入力] `bContextMenuShowsToolbarsOnly`  
 場合`TRUE`ウィンドウのメニューには、ツールバーの一覧のみが表示されます。 場合`FALSE`メニューには、ツールバーとドッキング バーの一覧が表示されます。  
  
 [入力] `bViewMenuShowsToolbarsOnly`  
 場合`TRUE`ウィンドウのメニューには、ツールバーの一覧のみが表示されます。 場合`FALSE`メニューには、ツールバーとドッキング バーの一覧が表示されます。  
  
### <a name="remarks"></a>コメント  
 ポップアップ ウィンドウのメニューでは、アプリケーションのウィンドウの一覧が表示され、ユーザーを表示するか、または個別のペインを非表示にすることができます。  
  
### <a name="example"></a>例  
 例を次にどのように`EnablePaneMenu`で使用される、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#9;](../../mfc/codesnippet/cpp/cmdiframewndex-class_9.cpp)]  
  
##  <a name="a-nameenablewindowsdialoga--cmdiframewndexenablewindowsdialog"></a><a name="enablewindowsdialog"></a>CMDIFrameWndEx::EnableWindowsDialog  
 コマンド ID を持つを呼び出すメニュー項目を挿入、 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)  ダイアログ ボックス。  
  
```  
void EnableWindowsDialog(
    UINT uiMenuId,  
    LPCTSTR lpszMenuText,  
    BOOL bShowAllways=FALSE,  
    BOOL bShowHelpButton=FALSE);

 
void EnableWindowsDialog(
    UINT uiMenuId,  
    UINT uiMenuTextResId,  
    BOOL bShowAllways=FALSE,  
    BOOL bShowHelpButton=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiMenuId`  
 メニューのリソース ID を指定します。  
  
 [入力] `lpszMenuText`  
 項目のテキストを指定します。  
  
 [入力] `bShowHelpButton`  
 表示するかどうかを指定、**ヘルプ**windows の管理 ダイアログ ボックスにボタンをクリックします。  
  
 [入力] `uiMenuTextResId`  
 項目のテキスト文字列を含む文字列リソースの識別子です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、そのコマンドは、MDI 子ウィンドウの管理 ダイアログ ボックスを呼び出しますメニュー項目を挿入します ( [CMFCWindowsManagerDialog クラス](../../mfc/reference/cmfcwindowsmanagerdialog-class.md))。 指定されたメニューに新しい項目を挿入`uiMenuId`します。 呼び出す`EnableWindowsDialog`を処理する際、`WM_CREATE`メッセージです。  
  
### <a name="example"></a>例  
 例を次にどのように`EnableWindowsDialog`で使用される、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#10;](../../mfc/codesnippet/cpp/cmdiframewndex-class_10.cpp)]  
  
##  <a name="a-namegetactivepopupa--cmdiframewndexgetactivepopup"></a><a name="getactivepopup"></a>CMDIFrameWndEx::GetActivePopup  
 現在表示されているポップアップ メニューへのポインターを返します。  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アクティブなポップアップ メニューへのポインター`NULL`ポップアップ メニューがアクティブでない場合。  
  
### <a name="remarks"></a>コメント  
 この関数へのポインターを使用して、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)現在表示されているオブジェクト。  
  
##  <a name="a-namegetdefaultresida--cmdiframewndexgetdefaultresid"></a><a name="getdefaultresid"></a>CMDIFrameWndEx::GetDefaultResId  
 MDI フレーム ウィンドウの共有リソースの ID を返します。  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リソースの ID 値です。 フレーム ウィンドウのメニュー バーにない場合は&0;。  
  
### <a name="remarks"></a>コメント  
 このメソッドで、MDI フレーム ウィンドウが読み込まれた時に指定されたリソース ID を返します[CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)します。  
  
##  <a name="a-namegetmditabgroupsa--cmdiframewndexgetmditabgroups"></a><a name="getmditabgroups"></a>CMDIFrameWndEx::GetMDITabGroups  
 タブ付きウィンドウの MDI の一覧を返します。  
  
```  
const CObList& GetMDITabGroups() const;  
```  
  
### <a name="return-value"></a>戻り値  
 参照、 [CObList クラス](../../mfc/reference/coblist-class.md)タブ付きウィンドウの一覧を含むオブジェクト。 格納したり、一覧を変更しないでください。  
  
### <a name="remarks"></a>コメント  
 タブ付きウィンドウの一覧にアクセスするのにには、このメソッドを使用します。 変更または個々 のタブ付きウィンドウのいくつかのパラメーターをクエリする場合は役に立ちます。  
  
##  <a name="a-namegetmditabsa--cmdiframewndexgetmditabs"></a><a name="getmditabs"></a>CMDIFrameWndEx::GetMDITabs  
 下線付きのタブ付きウィンドウへの参照を返します。  
  
```  
CMFCTabCtrl& GetMDITabs();
```  
  
### <a name="return-value"></a>戻り値  
 下線付きのタブ付きウィンドウへの参照。  
  
##  <a name="a-namegetmditabscontextmenualloweditemsa--cmdiframewndexgetmditabscontextmenualloweditems"></a><a name="getmditabscontextmenualloweditems"></a>CMDIFrameWndEx::GetMDITabsContextMenuAllowedItems  
 MDI タブ付きグループ機能が有効になっている場合に、どのような操作が有効かを示すフラグの組み合わせを返します。  
  
```  
DWORD GetMDITabsContextMenuAllowedItems();
```  
  
### <a name="return-value"></a>戻り値  
 次のフラグのビットごとの OR の組み合わせ。  
  
- `BCGP_MDI_CREATE_VERT_GROUP`-垂直タブ グループを作成できます。  
  
- `BCGP_MDI_CREATE_HORZ_GROUP`水平タブ グループを作成できます。  
  
- `BCGP_MDI_CAN_MOVE_PREV`-前のタブ グループに、タブを移動できます。  
  
- `BCGP_MDI_CAN_MOVE_NEXT`タブを次のタブ グループに移動できます。  
  
### <a name="remarks"></a>コメント  
 MDI タブ付きグループ機能が有効にすると、特定のウィンドウのタブでどのような操作は許可を知る必要があります。 このメソッドは、タブ付きウィンドウの現在のレイアウトを分析しをビルドすることができるフラグの組み合わせの使用のショートカット メニューを返します。  
  
 すべてのタブ付きウィンドウは縦方向に配置されている場合、または&1; つのタブ付きウィンドウがある場合は、新しい垂直タブ グループを作成できます。  
  
 すべてのタブ付きウィンドウが横方向に配置されている場合、または&1; つのタブ付きウィンドウがある場合は、新しい水平タブ グループを作成できます。  
  
 タブは、前のグループのタブ付きウィンドウに複数のタブがある場合にのみ移動できます。  
  
 タブは、次のグループのタブ付きウィンドウに複数のタブがある場合にのみ移動できます。  
  
##  <a name="a-namegetmenubara--cmdiframewndexgetmenubar"></a><a name="getmenubar"></a>CMDIFrameWndEx::GetMenuBar  
 メニュー バー オブジェクトが接続されているフレーム ウィンドウへのポインターを返します。  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メニュー バーのオブジェクトへのポインター。  
  
##  <a name="a-namegetpanea--cmdiframewndexgetpane"></a><a name="getpane"></a>CMDIFrameWndEx::GetPane  
 指定したコントロールの ID を持つペインへのポインターを返します  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 コントロールの id。  
  
### <a name="return-value"></a>戻り値  
 存在する場合は、指定したコントロール ID を持つウィンドウへのポインター。 それ以外の場合は `NULL`。  
  
##  <a name="a-namegetribbonbara--cmdiframewndexgetribbonbar"></a><a name="getribbonbar"></a>CMDIFrameWndEx::GetRibbonBar  
 フレームのリボン バー コントロールを取得します。  
  
```  
CMFCRibbonBar* GetRibbonBar();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)フレーム。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegettearoffbarsa--cmdiframewndexgettearoffbars"></a><a name="gettearoffbars"></a>CMDIFrameWndEx::GetTearOffBars  
 ティアオフ メニューの一覧を返します。  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>戻り値  
 参照、 [CObList クラス](../../mfc/reference/coblist-class.md)オブジェクトへのポインターのコレクションを格納する`CPane`-ティアオフ状態にあるオブジェクトを派生します。  
  
### <a name="remarks"></a>コメント  
 `CMDIFrameWndEx`ティアオフ メニューのコレクションを保持します。 このメソッドを使用すると、この一覧への参照を取得できます。  
  
##  <a name="a-namegettoolbarbuttontooltiptexta--cmdiframewndexgettoolbarbuttontooltiptext"></a><a name="gettoolbarbuttontooltiptext"></a>CMDIFrameWndEx::GetToolbarButtonToolTipText  
 アプリケーション ツールバーのボタンのツールヒントを表示するときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
 ツール バー ボタンへのポインター。  
  
 [入力] `strTTText`  
 ボタンに表示されるツールヒント テキスト。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ツールヒントが表示されています。 それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameinsertpanea--cmdiframewndexinsertpane"></a><a name="insertpane"></a>CMDIFrameWndEx::InsertPane  
 指定したウィンドウをドッキング マネージャーに登録します。  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
 挿入するのには、ウィンドウへのポインター。  
  
 [入力] `pTarget`  
 前に、または後ろに、ウィンドウを挿入する、ウィンドウへのポインター。  
  
 [入力] `bAfter`  
 場合`TRUE`、`pControlBar`後に挿入`pTarget`します。 場合`FALSE`、`pControlBar`前に挿入`pTarget`します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが、ウィンドウを正常に登録する場合`FALSE`場合は、ウィンドウはドッキング マネージャーに既に登録されています。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定されたウィンドウのドッキング マネージャーに通知を使用して`pControlBar`します。 ドッキングのマネージャーが、ウィンドウの整列およびドッキング マネージャーの内部リスト内の位置に従って、このウィンドウを整列します。  
  
##  <a name="a-nameisfullscreena--cmdiframewndexisfullscreen"></a><a name="isfullscreen"></a>CMDIFrameWndEx::IsFullScreen  
 フレーム ウィンドウが全画面表示モードになっているかどうかを判断します。  
  
```  
BOOL IsFullScreen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フレーム ウィンドウが全画面表示モードである場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 全画面表示モードを設定するには呼び出すことによって、 [CMDIFrameWndEx::EnableFullScreenMode](#enablefullscreenmode)メソッドです。  
  
##  <a name="a-nameismditabbedgroupa--cmdiframewndexismditabbedgroup"></a><a name="ismditabbedgroup"></a>CMDIFrameWndEx::IsMDITabbedGroup  
 MDI タブ付きグループ機能が有効になっているかどうかを指定します。  
  
```  
BOOL IsMDITabbedGroup() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`MDI タブ付きグループ機能が有効の場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 通常の MDI タブまたは MDI タブ付きグループ機能が有効かどうかを調べるには使用[CMDIFrameWndEx::AreMDITabs](#aremditabs)します。  
  
##  <a name="a-nameismemberofmditabgroupa--cmdiframewndexismemberofmditabgroup"></a><a name="ismemberofmditabgroup"></a>CMDIFrameWndEx::IsMemberOfMDITabGroup  
 指定したタブ付きウィンドウが MDI タブ付きグループに含まれるウィンドウのリストかどうかを判断します。  
  
```  
BOOL IsMemberOfMDITabGroup(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 タブ付きウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`指定したタブ付きウィンドウが MDI タブ付きグループを形成するタブ付きウィンドウの一覧の場合。 それ以外の場合`FALSE`します。  
  
##  <a name="a-nameismenubaravailablea--cmdiframewndexismenubaravailable"></a><a name="ismenubaravailable"></a>CMDIFrameWndEx::IsMenuBarAvailable  
 フレーム ウィンドウにメニュー バーがあるかどうかを決定します。  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メニュー バーのオブジェクトへのポインターは`NULL`。 そうしないと`FALSE`です。  
  
##  <a name="a-nameispointneardocksitea--cmdiframewndexispointneardocksite"></a><a name="ispointneardocksite"></a>CMDIFrameWndEx::IsPointNearDockSite  
 指定した点がドッキング サイトの近くにいるかどうかを判断します。  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 画面座標で指定した点です。  
  
 [入力] `dwBarAlignment`  
 どちらの端点が近いを指定します。 指定できる値は`CBRS_ALIGN_LEFT`、 `CBRS_ALIGN_RIGHT`、`CBRS_ALIGN_TOP`と`CBRS_ALIGN_BOTTOM`  
  
 [入力] `bOuterEdge`  
 `TRUE`ドッキング サイトの外側の境界線の近くのポイントがある場合`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング サイトの近くのポイントがある場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 ポイントは、ドッキング マネージャーで設定された感度内にある場合に、ドッキング サイトの近くです。 既定値と小文字の区別は、15 ピクセルです。  
  
##  <a name="a-nameisprintpreviewa--cmdiframewndexisprintpreview"></a><a name="isprintpreview"></a>CMDIFrameWndEx::IsPrintPreview  
 フレーム ウィンドウが印刷プレビュー モードになっているかどうかを判断します。  
  
```  
BOOL IsPrintPreview();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フレーム ウィンドウが印刷プレビュー モードである場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameloadframea--cmdiframewndexloadframe"></a><a name="loadframe"></a>CMDIFrameWndEx::LoadFrame  
 リソースの情報からフレーム ウィンドウを作成します。  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIDResource`  
 フレーム ウィンドウに関連付けられている共有リソースの ID です。  
  
 [入力] `dwDefaultStyle`  
 フレーム ウィンドウのスタイル。  
  
 [入力] `pParentWnd`  
 フレームの親ウィンドウへのポインター。  
  
 [入力] `pContext`  
 ポインター、 [CCreateContext 構造](../../mfc/reference/ccreatecontext-structure.md)します。 このパラメーターは、`NULL` に設定できます。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`それ以外の場合、メソッドが成功した場合`FALSE`します。  
  
##  <a name="a-nameloadmdistatea--cmdiframewndexloadmdistate"></a><a name="loadmdistate"></a>CMDIFrameWndEx::LoadMDIState  
 MDI タブ付きグループの指定されたレイアウトと以前に開いたドキュメントの一覧を読み込みます。  
  
```  
virtual BOOL LoadMDIState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 プロファイル名を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`負荷が正常な場合`FALSE`読み込みに失敗したか、読み込むデータがない場合。  
  
### <a name="remarks"></a>コメント  
 ロードする、または MDI タブとグループの状態、および開いているドキュメントの一覧を保存するには、次の操作を行います。  
  
-   呼び出す[CMDIFrameWndEx::SaveMDIState](#savemdistate)メインフレームが閉じられるとき  
  
-   呼び出す[CMDIFrameWndEx::LoadMDIState](#loadmdistate)メインフレームが作成されるときです。 この呼び出しの推奨される場所は、最初にメイン フレームが表示されるまでです。 追加`CWinAppEx::EnableLoadWindowPlacement``(FALSE);`する前に`pMainFrame->LoadFrame (IDR_MAINFRAME);.`追加`CBCGPWorkspace::ReloadWindowPlacement``(pMainFrame);`への呼び出し後`LoadMDIState`をレジストリに保存されている位置にあるメイン フレームを表示します。  
  
-   オーバーライド`GetDocumentName`で、`CMDIChildWndEx`の派生クラスの場合は、アプリケーションがファイルとして格納されていないドキュメントを表示します。 返される文字列は、ドキュメントの識別子としてレジストリに保存されます。 基本実装[CMDIChildWndEx::GetDocumentName](../../mfc/reference/cmdichildwndex-class.md#getdocumentname)から取得した値を返す[CDocument::GetPathName](../../mfc/reference/cdocument-class.md#getpathname)します。  
  
-   オーバーライド[CMDIFrameWndEx::CreateDocumentWindow](#createdocumentwindow)レジストリから読み込まれているときに、ドキュメントを正しく作成します。 最初のパラメーターは、文字列を`GetDocumentName`が返されます。  
  
### <a name="example"></a>例  
 例を次にどのように`LoadMDIState`で使用される、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#11;](../../mfc/codesnippet/cpp/cmdiframewndex-class_11.cpp)]  
  
##  <a name="a-namemditabmovetonextgroupa--cmdiframewndexmditabmovetonextgroup"></a><a name="mditabmovetonextgroup"></a>CMDIFrameWndEx::MDITabMoveToNextGroup  
 アクティブなタブを現在アクティブなタブ付きウィンドウから次または前のタブ付きグループに移動します。  
  
```  
void MDITabMoveToNextGroup(BOOL bNext=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bNext`  
 場合`TRUE`タブを次のタブ付きグループに移動します。 場合`FALSE`、前のタブ付きグループに移動します。  
  
##  <a name="a-namemditabnewgroupa--cmdiframewndexmditabnewgroup"></a><a name="mditabnewgroup"></a>CMDIFrameWndEx::MDITabNewGroup  
 1 つのウィンドウを持つ新しいタブ付きグループを作成します。  
  
```  
void MDITabNewGroup(BOOL bVert=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bVert`  
 新しいグループの配置を指定します。 場合`TRUE`、新しいグループを垂直方向に配置します。 場合`FALSE`、新しいグループが横方向に配置します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用して新しいを作成するタブ付きウィンドウ (新しいタブ付きグループ) し、最初のタブを追加します。  
  
### <a name="example"></a>例  
 例を次にどのように`MDITabNewGroup`で使用される、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#12;](../../mfc/codesnippet/cpp/cmdiframewndex-class_12.cpp)]  
  
##  <a name="a-namembcancovertcontrolbartomdichilda--cmdiframewndexmbcancovertcontrolbartomdichild"></a><a name="m_bcancovertcontrolbartomdichild"></a>CMDIFrameWndEx::m_bCanCovertControlBarToMDIChild  
 MDI 子ウィンドウのドッキング ペインを変換できるかどうかを指定します。  
  
```  
BOOL m_bCanCovertControlBarToMDIChild;  
```  
  
### <a name="remarks"></a>コメント  
 ドッキング コントロール バーを MDI 子ウィンドウに変換できるかどうかを示します。 このフラグは、する場合`TRUE`、フレームワーク、変換を自動的に処理を選択すると、**タブ付きドキュメント**コマンドです。 フラグが保護されているし、する必要があります明示的に有効にするには、このオプション設定するか`m_bCanCovertControlBarToMDIChild`のコンス トラクターで、`CMDIFrameWndEx`の派生クラス、またはオーバーライドで`CanConvertControlBarToMDIChild`します。  
  
 既定値は `FALSE` です。  
  
### <a name="example"></a>例  
 例を次にどのように`m_bCanCovertControlBarToMDIChild`で使用される、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#13;](../../mfc/codesnippet/cpp/cmdiframewndex-class_2.cpp)]  
  
##  <a name="a-namembdisablesetredrawa--cmdiframewndexmbdisablesetredraw"></a><a name="m_bdisablesetredraw"></a>CMDIFrameWndEx::m_bDisableSetRedraw  
 有効または MDI 子ウィンドウの再描画を最適化を無効にします。  
  
```  
AFX_IMPORT_DATA static BOOL m_bDisableSetRedraw;  
```  
  
### <a name="remarks"></a>コメント  
 既定値は `TRUE` です。  
  
 このフラグを設定`FALSE`MDI 子ウィンドウの再描画を最適化する場合。 ここでは、フレームワークが呼び出す`SetRedraw (FALSE)`メインフレーム アプリケーションがアクティブなタブを変更する場合のです。  
  
 このフラグには、望ましくない副作用 (バック グラウンド アプリケーションが表示される) 可能性があります。 したがって MDI タブのアクティブ化時に顕著なちらつきが発生した場合にのみ、既定値を変更することをお勧めします。  
  
##  <a name="a-namenegotiateborderspacea--cmdiframewndexnegotiateborderspace"></a><a name="negotiateborderspace"></a>CMDIFrameWndEx::NegotiateBorderSpace  
 フレーム ウィンドウの境界領域は、OLE、インプレース アクティブ化時にネゴシエートします。  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nBorderCmd`  
 列挙型から、次の値のいずれかの`CFrameWnd::BorderCmd`:  
  
- `borderGet` = 1  
  
- `borderRequest` = 2  
  
- `borderSet` = 3  
  
 [入力、出力] `lpRectBorder`  
 ポインター、 [RECT 構造体](../../mfc/reference/rect-structure1.md)または[CRect クラス](../../atl-mfc-shared/reference/crect-class.md)罫線の座標を指定するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、OLE 境界領域の調整の実装です。  
  
##  <a name="a-nameonclosedockingpanea--cmdiframewndexonclosedockingpane"></a><a name="onclosedockingpane"></a>CMDIFrameWndEx::OnCloseDockingPane  
 ユーザーがクリックしたときに、フレームワークによって呼び出されます、**閉じる**[ドッキング可能ウィンドウ] ボタンをクリックします。  
  
```  
virtual BOOL OnCloseDockingPane(CDockablePane* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 閉じるペインへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ドッキング ペインを閉じることができます。 それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 ドッキング ペインを非表示を処理するには、このメソッドをオーバーライドします。 返す`FALSE`ドッキング ウィンドウが非表示されないようにする場合。  
  
 既定の実装では nothing を返します`TRUE`します。  
  
##  <a name="a-nameoncloseminiframea--cmdiframewndexoncloseminiframe"></a><a name="oncloseminiframe"></a>CMDIFrameWndEx::OnCloseMiniFrame  
 ユーザーがクリックしたときに、フレームワークによって呼び出されます、**閉じる**浮動ミニフレーム ウィンドウのボタンをクリックします。  
  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd*);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 閉じられてミニフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、浮動小数点のミニフレーム ウィンドウを閉じることができます。 それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 フローティング ミニフレーム ウィンドウを非表示を処理するには、このメソッドをオーバーライドします。 返す`FALSE`をフローティング ミニフレーム ウィンドウが非表示にすることを防ぐために必要な場合です。  
  
 既定の実装では nothing を返します`TRUE`します。  
  
##  <a name="a-nameonclosepopupmenua--cmdiframewndexonclosepopupmenu"></a><a name="onclosepopupmenu"></a>CMDIFrameWndEx::OnClosePopupMenu  
 アクティブなポップアップ メニューを処理するときに、フレームワークによって呼び出され、`WM_DESTROY`メッセージです。  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenuPopup`  
 ポップアップ メニューへのポインター。  
  
### <a name="remarks"></a>コメント  
 通知を処理する場合は、このメソッドをオーバーライド[CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)それらのオブジェクトを処理するときに、MDI フレーム ウィンドウに属するオブジェクト`WM_DESTROY`メッセージです。  
  
##  <a name="a-nameoncmdmsga--cmdiframewndexoncmdmsg"></a><a name="oncmdmsg"></a>CMDIFrameWndEx::OnCmdMsg  
 コマンド メッセージをディスパッチするため、コマンドのユーザー インターフェイス オブジェクトを更新するために framework によって呼び出されます。  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 コマンド ID。  
  
 [入力] `nCode`  
 コマンド通知コードを識別します。 参照してください[CCmdTarget::OnCmdMsg](../../mfc/reference/ccmdtarget-class.md#oncmdmsg)の値の詳細については詳細`nCode`します。  
  
 [入力] `pExtra`  
 値に従って使用`nCode`します。 参照してください[CCmdTarget::OnCmdMsg](../../mfc/reference/ccmdtarget-class.md#oncmdmsg)の詳細については`pExtra`です。  
  
 [入力、出力] `pHandlerInfo`  
 通常、このパラメーターに指定する必要があります`NULL`します。ない場合`NULL`、`OnCmdMsg`を入力、`pTarget`と`pmf`のメンバー、`pHandlerInfo`ディスパッチ コマンドではなく構造体。  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="a-nameondrawmenuimagea--cmdiframewndexondrawmenuimage"></a><a name="ondrawmenuimage"></a>CMDIFrameWndEx::OnDrawMenuImage  
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
 イメージの外接する四角形。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、メソッドは、イメージを描画します。 既定の実装では、`FALSE` が返されます。  
  
### <a name="remarks"></a>コメント  
 所有するメニュー バーに属しているメニュー項目のイメージの描画をカスタマイズする場合は、このメソッドをオーバーライド、 `CMDIFrameWndEx`-派生オブジェクト。 既定の実装では、何も行われません。  
  
##  <a name="a-nameondrawmenulogoa--cmdiframewndexondrawmenulogo"></a><a name="ondrawmenulogo"></a>CMDIFrameWndEx::OnDrawMenuLogo  
 フレームワークによって呼び出されるときに、 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)プロセス、`WM_PAINT`メッセージです。  
  
```  
virtual void OnDrawMenuLogo(
    CDC*, 
    CMFCPopupMenu*, 
    const CRect&);
```  
  
### <a name="remarks"></a>コメント  
 所有するメニュー バーのポップアップ メニューにロゴを表示するには、この関数をオーバーライドして、 `CMDIFrameWndEx`-派生オブジェクト。 既定の実装では、何も行われません。  
  
##  <a name="a-nameonerasemdiclientbackgrounda--cmdiframewndexonerasemdiclientbackground"></a><a name="onerasemdiclientbackground"></a>CMDIFrameWndEx::OnEraseMDIClientBackground  
 MDI フレーム ウィンドウのプロセス時にフレームワークによって呼び出さ、`WM_ERASEBKGND`メッセージです。  
  
```  
virtual BOOL OnEraseMDIClientBackground(CDC*);
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`アプリケーションがメッセージを処理し、バック グラウンドが消去されます。  
  
### <a name="remarks"></a>コメント  
 処理する場合は、このメンバー関数をオーバーライド、`WM_ERASEBKGND`でメッセージを`CMDIFrameWndEx`-クラスを派生します。  
  
##  <a name="a-nameonmenubuttontoolhittesta--cmdiframewndexonmenubuttontoolhittest"></a><a name="onmenubuttontoolhittest"></a>CMDIFrameWndEx::OnMenuButtonToolHitTest  
 フレームワークによって呼び出されますときに、 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)プロセスのオブジェクト、`WM_NCHITTEST`メッセージです。  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
 ツール バー ボタン。  
  
 [出力] `pTI`  
 ポインター、 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)構造体。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`アプリケーションは入力の場合、`pTI`パラメーター。 既定の実装では、`FALSE` が返されます。  
  
### <a name="remarks"></a>コメント  
 特定のメニュー項目のツールヒントについての情報を提供する場合は、このメソッドをオーバーライドします。 既定の実装では、何も行われません。  
  
##  <a name="a-nameonmoveminiframea--cmdiframewndexonmoveminiframe"></a><a name="onmoveminiframe"></a>CMDIFrameWndEx::OnMoveMiniFrame  
 ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pFrame`  
 ミニフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`それ以外の場合、メソッドが成功した場合`FALSE`します。  
  
##  <a name="a-nameonsetpreviewmodea--cmdiframewndexonsetpreviewmode"></a><a name="onsetpreviewmode"></a>CMDIFrameWndEx::OnSetPreviewMode  
 アプリケーションのメイン フレーム ウィンドウの 印刷プレビュー モードを設定します。  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bPreview`  
 場合`TRUE`、印刷プレビュー モードを設定します。 場合`FALSE`、プレビュー モードがキャンセルされます。  
  
 [入力] `pState`  
 ポインター、`CPrintPreviewState`構造体。  
  
### <a name="remarks"></a>コメント  
 このメソッドは[CFrameWnd::OnSetPreviewMode](../../mfc/reference/cframewnd-class.md#onsetpreviewmode)します。  
  
##  <a name="a-nameonshowcustomizepanea--cmdiframewndexonshowcustomizepane"></a><a name="onshowcustomizepane"></a>CMDIFrameWndEx::OnShowCustomizePane  
 簡易カスタマイズ ペインがアクティブになったときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenuPane`  
 [カスタマイズ] ウィンドウへのポインター。  
  
 [入力] `uiToolbarID`  
 コントロールをカスタマイズするには、ツールバーの ID。  
  
### <a name="return-value"></a>戻り値  
 このメソッドは常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
 簡易カスタマイズ ペインは、ユーザーがクリックしたときに表示されるメニュー**カスタマイズ**ツールバーにあります。  
  
 すばやくカスタマイズ ウィンドウで変更して、派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="a-nameonshowmditabcontextmenua--cmdiframewndexonshowmditabcontextmenu"></a><a name="onshowmditabcontextmenu"></a>CMDIFrameWndEx::OnShowMDITabContextMenu  
 タブのいずれかのショートカット メニューを表示する前に、フレームワークによって呼び出されます。 MDI タブ付きグループのみ有効です。  
  
```  
virtual BOOL OnShowMDITabContextMenu(
    CPoint point,  
    DWORD dwAllowedItems,  
    BOOL bTabDrop);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 画面座標でメニューの場所。  
  
 [入力] `dwAllowedItems`  
 現在のタブで許可されるアクションを示すビットごとの OR フラグの組み合わせです。  
  
- `BCGP_MDI_CREATE_VERT_GROUP`-垂直タブ グループを作成できます。  
  
- `BCGP_MDI_CREATE_HORZ_GROUP`水平タブ グループを作成できます。  
  
- `BCGP_MDI_CAN_MOVE_PREV`-前のタブ グループに、タブを移動できます。  
  
- `BCGP_MDI_CAN_MOVE_NEXT`タブを次のタブ グループに移動できます。  
  
- `BCGP_MDI_CAN_BE_DOCKED`ドッキング状態 (タブ付きドキュメントのみに関連する) にはタブ付きドキュメントを切り替えます。  
  
 [入力] `bTabDrop`  
 `TRUE`別のタブ付きグループに、タブをドラッグする結果として、メニューを表示します。 `FALSE`現在アクティブなタブのショートカット メニューとメニューを表示します。  
  
### <a name="return-value"></a>戻り値  
 このメソッドをオーバーライドして、 [CBCGPMDIFrameWnd](../../mfc/reference/cmdiframewndex-class.md)-クラスを派生します。  
  
### <a name="remarks"></a>コメント  
 処理しない場合`OnShowMDITabContextMenu`、ショートカット メニューは表示されません。 この関数はによって生成された、 **MFC アプリケーション ウィザード**MDI タブ付きグループ機能を有効にするとします。  
  
### <a name="example"></a>例  
 例を次にどのように`OnShowMDITabContextMenu`で使用される、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#14;](../../mfc/codesnippet/cpp/cmdiframewndex-class_13.cpp)]  
  
##  <a name="a-nameonshowpanesa--cmdiframewndexonshowpanes"></a><a name="onshowpanes"></a>CMDIFrameWndEx::OnShowPanes  
 ペインを非表示を切り替えるために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
 `TRUE`ペインを表示する`FALSE`ウィンドウを非表示にします。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドの呼び出しの結果として、ペインの状態が変更された場合`FALSE`場合は、ペインがで指定された状態で既に`bShow`します。 たとえば、ウィンドウが表示されていない場合と`bShow`は`FALSE`、戻り値は`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、最上位のフレーム ウィンドウから、ツールバーを削除します。  
  
 場合[CDockingManager::m_bHideDockingBarsInContainerMode](../../mfc/reference/cdockingmanager-class.md#m_bhidedockingbarsincontainermode)は`TRUE`(既定)、すべてのドッキング ペインを非表示になります。  
  
##  <a name="a-nameonshowpopupmenua--cmdiframewndexonshowpopupmenu"></a><a name="onshowpopupmenu"></a>CMDIFrameWndEx::OnShowPopupMenu  
 ポップアップ メニューを開いたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu*);
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ポップアップ メニューが表示される場合。 それ以外の場合は `FALSE`。 既定の実装では、`TRUE` が返されます。  
  
### <a name="remarks"></a>コメント  
 ポップアップ メニューがアクティブ化時に特別な処理を実装する場合は、このメソッドをオーバーライドします。 たとえば、色のメニュー項目に標準のメニュー項目を変更するには場合、は、ティアオフ バーをセットアップし、具合です。  
  
 既定の実装では、何も行われません。  
  
##  <a name="a-nameonsizemdiclienta--cmdiframewndexonsizemdiclient"></a><a name="onsizemdiclient"></a>CMDIFrameWndEx::OnSizeMDIClient  
 クライアントの MDI ウィンドウのサイズを変更するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnSizeMDIClient(
    const CRect& rectOld,  
    const CRect& rectNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectOld`  
 MDI クライアント ウィンドウの現在のサイズ。  
  
 [入力] `rectNew`  
 MDI クライアント ウィンドウの新しいサイズ。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameontearoffmenua--cmdiframewndexontearoffmenu"></a><a name="ontearoffmenu"></a>CMDIFrameWndEx::OnTearOffMenu  
 ティアオフ バーのあるメニューがアクティブ化されるときにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenuPopup`  
 ポップアップ メニューへのポインター。  
  
 [入力] `pBar`  
 ティアオフ バーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ティアオフ バーがアクティブにできる、ポップアップ メニューを許可するにはそれ以外の場合`FALSE`します。 既定値は、`TRUE` です。  
  
### <a name="remarks"></a>コメント  
 ティアオフ バー用の特別な設定を実装する場合に、この関数をオーバーライドします。 既定の実装では、何も行われません。  
  
##  <a name="a-nameonupdateframemenua--cmdiframewndexonupdateframemenu"></a><a name="onupdateframemenu"></a>CMDIFrameWndEx::OnUpdateFrameMenu  
 フレームのメニューを更新するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hMenuAlt`  
 メニューへのハンドル。  
  
##  <a name="a-namepanefrompointa--cmdiframewndexpanefrompoint"></a><a name="panefrompoint"></a>CMDIFrameWndEx::PaneFromPoint  
 指定したポイントを含むドッキング ペインを返します。  
  
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
 (画面座標) をポイントします。  
  
 [入力] `nSensitivity`  
 チェックする各ペインのウィンドウの四角形は、この値によって、すべての方向に拡大されます。  
  
 [入力] `bExactBar`  
 場合`TRUE`、`nSensitivity`パラメーターは無視されます。  
  
 [入力] `pRTCBarType`  
 以外の場合`NULL`メソッドは、指定した型のウィンドウだけを反復処理します。  
  
 [出力] `dwAlignment`  
 ペインが見つかった場合、このパラメーターは、ウィンドウのどちらの側は、指定したポイントに最も近いを指定します。  
  
### <a name="return-value"></a>戻り値  
 ドッキング ペインへのポインターまたは`NULL`コントロールに指定された地点が含まれていない場合`point`します。  
  
### <a name="remarks"></a>コメント  
 呼び出しにリダイレクトされ、 [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)します。 参照してください[CDockingManager::ControlBarFromPoint](../../mfc/reference/cdockingmanager-class.md#panefrompoint)の詳細。  
  
##  <a name="a-namerecalclayouta--cmdiframewndexrecalclayout"></a><a name="recalclayout"></a>CMDIFrameWndEx::RecalcLayout  
 フレーム ウィンドウのレイアウトを再計算するためにフレームワークによって呼び出されます。  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bNotify`  
 フレーム ウィンドウのアクティブなインプレース アイテムがレイアウトの変更の通知を受け取るかどうかを決定します。 場合`TRUE`、したアイテムが通知された`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは[表示](../../mfc/reference/cframewnd-class.md#recalclayout)します。  
  
##  <a name="a-nameremovepanefromdockmanagera--cmdiframewndexremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>CMDIFrameWndEx::RemovePaneFromDockManager  
 ペインの登録を解除し、ドッキング マネージャーから削除されます。  
  
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
 削除するペインへのポインター。  
  
 [入力] `bDestroy`  
 `TRUE`削除されたウィンドウを破棄します。 `FALSE`破棄していません。  
  
 [入力] `bAdjustLayout`  
 `TRUE`すぐにドッキング レイアウトを調整します。 場合`FALSE`調整が行われますの他の理由から、再描画イベントが発生した場合にのみ (ユーザー、ウィンドウのサイズ変更、メインフレームなどをドラッグした)。  
  
 [入力] `bAutoHide`  
 `TRUE`自動的に隠す ペインの一覧から、ウィンドウを削除します。 `FALSE`標準のペインの一覧から、ウィンドウを削除します。  
  
 [入力] `pBarReplacement`  
 削除されるペインに置き換えられるペインへのポインター。  
  
### <a name="remarks"></a>コメント  
 ドッキング レイアウトを行うにドッキング マネージャーに各ウィンドウを登録する必要があります。 使用[CMDIFrameWndEx::AddPane](#addpane)または[CMDIFrameWndEx::InsertPane](#insertpane)ウィンドウを登録します。  
  
 ウィンドウがフレーム ウィンドウのドッキング レイアウトの一部では不要になったときに、このメソッドを使用します。  
  
##  <a name="a-namesavemdistatea--cmdiframewndexsavemdistate"></a><a name="savemdistate"></a>CMDIFrameWndEx::SaveMDIState  
 MDI タブ付きグループの現在のレイアウトと以前に開いたドキュメントの一覧を保存します。  
  
```  
virtual BOOL SaveMDIState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 プロファイル名を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`保存が成功した場合`FALSE`場合は、保存に失敗しました。  
  
### <a name="remarks"></a>コメント  
 ロードする、または MDI タブとグループの状態、および開いているドキュメントの一覧を保存するには、次の操作を行います。  
  
-   呼び出す`SaveMDIState`メインフレームが閉じられるとき  
  
-   呼び出す[CMDIFrameWndEx::LoadMDIState](#loadmdistate)メインフレームが作成されるときです。 この呼び出しの推奨される場所は、最初にメイン フレームが表示されるまでです。  
  
-   呼び出す`CWinAppEx::EnableLoadWindowPlacement(FALSE);`する前に`pMainFrame->LoadFrame (IDR_MAINFRAME);`  
  
-   呼び出す`CWinAppEx::ReloadWindowPlacement``(pMainFrame)`後`LoadMDIState`をレジストリに保存されている位置にあるメイン フレームを表示します。  
  
-   オーバーライド`GetDocumentName`で、`CMDIChildWndEx`の派生クラスの場合は、アプリケーションがファイルとして格納されていないドキュメントを表示します。 返される文字列は、ドキュメントの識別子としてレジストリに保存されます。 詳細については、次を参照してください。 [CMDIChildWndEx::GetDocumentName](../../mfc/reference/cmdichildwndex-class.md#getdocumentname)します。  
  
-   オーバーライド[CMDIFrameWndEx::CreateDocumentWindow](#createdocumentwindow)レジストリから読み込まれているときに、ドキュメントを正しく作成します。 パラメーターを`CreateDocumentWindow`文字列を`GetDocumentName`先ほど返されました。  
  
### <a name="example"></a>例  
 例を次にどのように`SaveMDIState`で使用される、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#15;](../../mfc/codesnippet/cpp/cmdiframewndex-class_14.cpp)]  
  
##  <a name="a-namesetprintpreviewframea--cmdiframewndexsetprintpreviewframe"></a><a name="setprintpreviewframe"></a>CMDIFrameWndEx::SetPrintPreviewFrame  
 印刷プレビューのフレーム ウィンドウを設定します。  
  
```  
void SetPrintPreviewFrame(CFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 印刷プレビューのフレーム ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetuptoolbarmenua--cmdiframewndexsetuptoolbarmenu"></a><a name="setuptoolbarmenu"></a>CMDIFrameWndEx::SetupToolbarMenu  
 ツール バー オブジェクトを変更するには、ユーザー定義の項目を含むダミーの項目を置換します。  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `menu`  
 参照、 [CMenu クラス](../../mfc/reference/cmenu-class.md)オブジェクトを変更できます。  
  
 [入力] `uiViewUserToolbarCmdFirst`  
 ユーザー定義の最初のコマンドを指定します。  
  
 [入力] `uiViewUserToolbarCmdLast`  
 ユーザー定義の最後のコマンドを指定します。  
  
##  <a name="a-nameshowfullscreena--cmdiframewndexshowfullscreen"></a><a name="showfullscreen"></a>CMDIFrameWndEx::ShowFullScreen  
 全画面表示モードを通常モードからメイン フレームを切り替えます。  
  
```  
void ShowFullScreen();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameshowpanea--cmdiframewndexshowpane"></a><a name="showpane"></a>CMDIFrameWndEx::ShowPane  
 指定したウィンドウの表示と非表示を切り替えます。  
  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 ウィンドウを表示するか非表示へのポインター。  
  
 [入力] `bShow`  
 `TRUE`ペインを表示します。 `FALSE`ウィンドウを非表示にします。  
  
 [入力] `bDelay`  
 `TRUE`遅延のドッキング レイアウトの再計算します。 `FALSE`すぐにドッキング レイアウトを再計算します。  
  
 [入力] `bActivate`  
 `TRUE`ウィンドウを表示するには、アクティブとして必要です。 `FALSE`非アクティブなウィンドウを示します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウを非表示を切り替えるには、このメソッドを呼び出します。 使用しないで`ShowWindow`ドッキング ペインです。  
  
### <a name="example"></a>例  
 例を次にどのように`ShowPane`で使用される、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#16;](../../mfc/codesnippet/cpp/cmdiframewndex-class_15.cpp)]  
  
##  <a name="a-nameshowwindowsdialoga--cmdiframewndexshowwindowsdialog"></a><a name="showwindowsdialog"></a>CMDIFrameWndEx::ShowWindowsDialog  
 作成、 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)ボックスを開きます。  
  
```  
void ShowWindowsDialog();
```  
  
### <a name="example"></a>例  
 例を次にどのように`ShowWindowsDialog`で使用される、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#18;](../../mfc/codesnippet/cpp/cmdiframewndex-class_16.cpp)]  
  
##  <a name="a-nametabbeddocumenttocontrolbara--cmdiframewndextabbeddocumenttocontrolbar"></a><a name="tabbeddocumenttocontrolbar"></a>CMDIFrameWndEx::TabbedDocumentToControlBar  
 ドッキング ペインに、指定したタブ付きドキュメントを変換します。  
  
```  
virtual BOOL TabbedDocumentToControlBar(CMDIChildWndEx* pMDIChildWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMDIChildWnd`  
 ドッキング ペインを含む MDI 子ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合`FALSE`失敗します。  
  
### <a name="remarks"></a>コメント  
 ドッキング ペインにタブ付きドキュメントを変換するのにには、このメソッドを使用します。 タブ付きドキュメントを使用して作成する必要があります[CMDIFrameWndEx::ControlBarToTabbedDocument](#controlbartotabbeddocument)します。  
  
### <a name="example"></a>例  
 例を次にどのように`TabbedDocumentToControlBar`で使用される、 [VisualStudioDemo サンプル: MFC Visual Studio アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#19;](../../mfc/codesnippet/cpp/cmdiframewndex-class_17.cpp)]  
  
##  <a name="a-nameupdatecaptiona--cmdiframewndexupdatecaption"></a><a name="updatecaption"></a>CMDIFrameWndEx::UpdateCaption  
 ウィンドウ フレームのキャプションを更新するためにフレームワークによって呼び出されます。  
  
```  
void UpdateCaption();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameupdatemditabbedbarsiconsa--cmdiframewndexupdatemditabbedbarsicons"></a><a name="updatemditabbedbarsicons"></a>CMDIFrameWndEx::UpdateMDITabbedBarsIcons  
 各 MDI タブ付きペインのアイコンを設定します。  
  
```  
void UpdateMDITabbedBarsIcons();
```  
  
##  <a name="a-namewinhelpa--cmdiframewndexwinhelp"></a><a name="winhelp"></a>CMDIFrameWndEx::WinHelp  
 WinHelp アプリケーションまたはコンテキスト ヘルプを起動するために、フレームワークによって呼び出されます。  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwData`  
 `nCmd`で指定されたヘルプの種類に必要とされるデータを指定します。  
  
 [入力] `nCmd`  
 要求されるヘルプの種類を指定します。 有効な値の一覧と `dwData` パラメーターに与える影響については、Windows SDK の「 [WinHelp 関数](http://msdn.microsoft.com/library/windows/desktop/bb762267) 」を参照してください。  
  
### <a name="remarks"></a>コメント  
 このメソッドは[CWnd::WinHelp](../../mfc/reference/cwnd-class.md#winhelp)します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWnd](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWndEx クラス](../../mfc/reference/cmdichildwndex-class.md)

