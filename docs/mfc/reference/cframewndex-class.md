---
title: "CFrameWndEx クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFrameWndEx
dev_langs:
- C++
helpviewer_keywords:
- CFrameWndEx class
ms.assetid: 5830aca8-4a21-4f31-91f1-dd5477ffcc8d
caps.latest.revision: 39
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b2106c3067a0164395eddab0e8b156728697d5bb
ms.lasthandoff: 02/24/2017

---
# <a name="cframewndex-class"></a>CFrameWndEx クラス
Windows のシングル ドキュメント インターフェイス (SDI: Single Document Interface) のオーバーラップ フレーム ウィンドウまたはポップアップ フレーム ウィンドウの機能を実装し、ウィンドウを管理するメンバーを提供します。 拡張して、 [CFrameWnd](../../mfc/reference/cframewnd-class.md)クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CFrameWndEx : public CFrameWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFrameWndEx::ActiveItemRecalcLayout](#activeitemrecalclayout)|OLE クライアント アイテムとフレームのクライアント領域のレイアウトを調整します。|  
|`CFrameWndEx::AddDockSite`|このメソッドは使用されません。|  
|[CFrameWndEx::AddPane](#addpane)|コントロール バーをドッキング マネージャーに登録します。|  
|[CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)|フレーム ウィンドウにドッキングされているすべてのペインのレイアウトを再計算します。|  
|[CFrameWndEx::DelayUpdateFrameMenu](#delayupdateframemenu)|フレームのメニューを設定し、コマンドの処理がアイドル状態のときに更新します。|  
|[CFrameWndEx::DockPane](#dockpane)|フレーム ウィンドウに、指定したウィンドウをドッキングします。|  
|[CFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|ウィンドウを別のウィンドウの左側にドッキングします。|  
|[CFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)|メイン フレーム ウィンドウの指定した辺にドッキングされている場合は、ウィンドウの自動非表示モードを有効にします。|  
|[CFrameWndEx::EnableDocking](#enabledocking)|フレーム ウィンドウに属するペインのドッキングを有効にします。|  
|[CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu)|全画面表示モードのメイン メニューの表示と非表示を切り替えます。|  
|[CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode)|フレーム ウィンドウの全画面表示モードを有効にします。|  
|[CFrameWndEx::EnableLoadDockState](#enableloaddockstate)|有効またはドッキング状態の読み込みを無効にします。|  
|[CFrameWndEx::EnablePaneMenu](#enablepanemenu)|有効または、ウィンドウのメニューの自動処理を無効にします。|  
|[CFrameWndEx::GetActivePopup](#getactivepopup)|現在表示されているポップアップ メニューへのポインターを返します。|  
|[CFrameWndEx::GetDefaultResId](#getdefaultresid)|フレームワークには、フレーム ウィンドウが読み込まれたときに指定したリソース ID を返します。|  
|[CFrameWndEx::GetDockingManager](#getdockingmanager)|取得、 [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)フレーム ウィンドウのオブジェクト。|  
|[CFrameWndEx::GetMenuBar](#getmenubar)|フレーム ウィンドウにアタッチされているメニュー バーのオブジェクトへのポインターを返します。|  
|[CFrameWndEx::GetPane](#getpane)|指定した ID を持つペインへのポインターを返します|  
|[CFrameWndEx::GetRibbonBar](#getribbonbar)|フレームのリボン バー コントロールを取得します。|  
|[CFrameWndEx::GetTearOffBars](#gettearoffbars)|ティアオフ状態にあるウィンドウ オブジェクトの一覧を返します。|  
|[CFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|アプリケーション ツールバーのボタンのツールヒントを表示するときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::InsertPane](#insertpane)|ペインをドッキング マネージャーに登録します。|  
|[CFrameWndEx::IsFullScreen](#isfullscreen)|フレーム ウィンドウが全画面表示モードになっているかどうかを判断します。|  
|[CFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|メニュー バーのオブジェクトへのポインターが有効かどうかを判断します。|  
|[CFrameWndEx::IsPointNearDockSite](#ispointneardocksite)|配置ゾーンに、ポイントがあるかどうかを示します。|  
|[CFrameWndEx::IsPrintPreview](#isprintpreview)|フレーム ウィンドウが印刷プレビュー モードかどうかを示します。|  
|[CFrameWndEx::LoadFrame](#loadframe)|このメソッドは、構造のフレーム ウィンドウを作成し、そのリソースの読み込み後に呼び出されます。|  
|[CFrameWndEx::NegotiateBorderSpace](#negotiateborderspace)|実装して OLE クライアント罫線調整します。|  
|[CFrameWndEx::OnActivate](#onactivate)|フレームワークは、ユーザー入力が切り替えられたにまたはフレームを離れたときに、このメソッドを呼び出します。|  
|[CFrameWndEx::OnActivateApp](#onactivateapp)|アプリケーションが選択または選択解除されたときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnChangeVisualManager](#onchangevisualmanager)|フレームへの変更がビジュアル マネージャーへの変更が必要な場合に、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnClose](#onclose)|フレームワークでは、フレームを終了するには、このメソッドを呼び出します。|  
|[CFrameWndEx::OnCloseDockingPane](#onclosedockingpane)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**閉じる**ドッキング ペインでボタンをクリックします。|  
|[CFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**閉じる**浮動ミニフレーム ウィンドウのボタンをクリックします。|  
|[CFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|アクティブなポップアップ メニューが WM_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnCmdMsg](#oncmdmsg)|コマンド メッセージをディスパッチします。|  
|[CFrameWndEx::OnContextHelp](#oncontexthelp)|フレームワークによって呼び出されるコンテキストを表示する関連するヘルプ。|  
|[CFrameWndEx::OnCreate](#oncreate)|フレームを作成した後に、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnDestroy](#ondestroy)|フレームが破棄されるときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|アプリケーションは、メニュー項目に関連付けられているイメージを描画するときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|フレームワークによって呼び出されますときに、`CMFCPopupMenu`プロセスのオブジェクト、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)メッセージです。|  
|[CFrameWndEx::OnDWMCompositionChanged](#ondwmcompositionchanged)|デスクトップ ウィンドウ マネージャー (DWM) の構成を有効になっているか、無効になっているときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnExitSizeMove](#onexitsizemove)|移動またはサイズ変更、フレームが停止したときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnGetMinMaxInfo](#ongetminmaxinfo)|ウィンドウのサイズ制限を設定する、フレームのサイズが変更されるときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnIdleUpdateCmdUI](#onidleupdatecmdui)|コマンドの処理がアイドル状態のときに、フレームの表示を更新するためにフレームワークによって呼び出されます。|  
|[CFrameWndEx::OnLButtonDown](#onlbuttondown)|フレームワークは、ユーザーがマウスの左ボタンを押したときに、このメソッドを呼び出します。|  
|[CFrameWndEx::OnLButtonUp](#onlbuttonup)|フレームワークは、マウスの左ボタンを離したときに、このメソッドを呼び出します。|  
|[CFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|フレームワークによって呼び出されますときに、`CMFCToolBarButton`プロセスのオブジェクト、`WM_NCHITTEST`メッセージです。|  
|[CFrameWndEx::OnMenuChar](#onmenuchar)|メニューが表示され、ユーザーがコマンドに対応しないキーを押したときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnMouseMove](#onmousemove)|フレームワークは、ポインターを移動すると、このメソッドを呼び出します。|  
|[CFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)|ウィンドウ枠に移動したときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnNcActivate](#onncactivate)|アクティブな状態の変化を示すために、フレームの非クライアント領域が再描画されるときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnNcCalcSize](#onnccalcsize)|クライアント領域の位置とサイズを計算する必要があるときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnNcHitTest](#onnchittest)|ポインターを移動する、またはマウス ボタンが押されたまたは離されたときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnNcMouseMove](#onncmousemove)|マウス ポインターが非クライアント領域内に移動するときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnNcPaint](#onncpaint)|非クライアント領域を描画する必要があるときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnPaneCheck](#onpanecheck)|ペインの表示を制御するためにフレームワークによって呼び出されます。|  
|[CFrameWndEx::OnPostPreviewFrame](#onpostpreviewframe)|ユーザーが印刷プレビュー モードに変更されたときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnPowerBroadcast](#onpowerbroadcast)|電源管理イベントが発生したときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnSetMenu](#onsetmenu)|フレーム ウィンドウ メニューを置き換えるため、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|フレームの印刷プレビュー モードを設定するためにフレームワークによって呼び出されます。|  
|[CFrameWndEx::OnSetText](#onsettext)|ウィンドウのテキストを設定するためにフレームワークによって呼び出されます。|  
|[CFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)|簡単なカスタマイズ時にフレームワークによって呼び出さウィンドウが有効にします。|  
|[CFrameWndEx::OnShowPanes](#onshowpanes)|ペインを非表示を切り替えるために、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|ポップアップ メニューが有効になっているときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnSize](#onsize)|フレームワークは、フレームのサイズが変更された後、このメソッドを呼び出します。|  
|[CFrameWndEx::OnSizing](#onsizing)|フレームワークは、ユーザー、フレームのサイズを変更するときに、このメソッドを呼び出します。|  
|[CFrameWndEx::OnSysColorChange](#onsyscolorchange)|システム カラーが変更するときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnTearOffMenu](#ontearoffmenu)|ティアオフ バーを持つメニューが有効になっているときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnToolbarContextMenu](#ontoolbarcontextmenu)|ツールバーのコンテキスト メニューを作成するために、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnToolbarCreateNew](#ontoolbarcreatenew)|フレームワークでは、新しいツールバーを作成するには、このメソッドを呼び出します。|  
|[CFrameWndEx::OnToolbarDelete](#ontoolbardelete)|ツールバーが削除されたときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::OnUpdateFrameMenu](#onupdateframemenu)|フレームのメニューを設定するためにフレームワークによって呼び出されます。|  
|[CFrameWndEx::OnUpdateFrameTitle](#onupdateframetitle)|フレームワークでは、フレーム ウィンドウのタイトル バーを更新するには、このメソッドを呼び出します。|  
|[CFrameWndEx::OnUpdatePaneMenu](#onupdatepanemenu)|ウィンドウ メニューを更新するためにフレームワークによって呼び出されます。|  
|[CFrameWndEx::OnWindowPosChanged](#onwindowposchanged)|ウィンドウ管理メソッドの呼び出しのためのフレーム サイズ、位置、または z オーダーが変更されたときに、フレームワークによって呼び出されます。|  
|[CFrameWndEx::PaneFromPoint](#panefrompoint)|指定したポイントを含むドッキング ペインを返します。|  
|[CFrameWndEx::PreTranslateMessage](#pretranslatemessage)|ディスパッチされる前に、特定のウィンドウ メッセージを処理します。|  
|[CFrameWndEx::RecalcLayout](#recalclayout)|フレームとその子ウィンドウのレイアウトを調整します。|  
|[CFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|ペインの登録を解除し、ドッキング マネージャーの内部リストから削除されます。|  
|[CFrameWndEx::SetDockState](#setdockstate)|ドッキング レイアウトをレジストリに格納されているドッキング状態に復元します。|  
|[CFrameWndEx::SetPrintPreviewFrame](#setprintpreviewframe)|印刷プレビューのフレーム ウィンドウを設定します。|  
|[CFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|ユーザー定義コマンドをツール バー メニューに挿入します。|  
|[CFrameWndEx::ShowFullScreen](#showfullscreen)|メインフレームの全画面表示モードと通常モードに切り替えます。|  
|[CFrameWndEx::ShowPane](#showpane)|指定したウィンドウの表示と非表示を切り替えます。|  
|[CFrameWndEx::UpdateCaption](#updatecaption)|ウィンドウ フレームのキャプションを更新するためにフレームワークによって呼び出されます。|  
|[CFrameWndEx::WinHelp](#winhelp)|いずれかを呼び出す、`WinHelp`アプリケーションまたはコンテキスト関連のヘルプ。|  
  
## <a name="example"></a>例  
 次の例からクラスを継承する方法、`CFrameWndEx`クラスです。 このサブクラスでメソッド署名と上書きする方法、例に示す、`OnShowPopupMenu`メソッドです。 このコード スニペットの一部である、 [Word パッド サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_WordPad&#3;](../../mfc/reference/codesnippet/cpp/cframewndex-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad&4;](../../mfc/reference/codesnippet/cpp/cframewndex-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CFrameWndEx](../../mfc/reference/cframewndex-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxframewndex.h  
  
##  <a name="a-nameactiveitemrecalclayouta--cframewndexactiveitemrecalclayout"></a><a name="activeitemrecalclayout"></a>CFrameWndEx::ActiveItemRecalcLayout  
 OLE クライアント アイテムとフレームのクライアント領域のレイアウトを調整します。  
  
```  
void ActiveItemRecalcLayout();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameaddpanea--cframewndexaddpane"></a><a name="addpane"></a>CFrameWndEx::AddPane  
 コントロール バーをドッキング マネージャーに登録します。  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
 登録するコントロール バー ペインです。  
  
 [入力] `bTail`  
 `TRUE`コントロール バー ペインには、リストの末尾に追加する場合`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、コントロール バーが正常に登録されました。`FALSE`それ以外の場合。  
  
##  <a name="a-nameadjustdockinglayouta--cframewndexadjustdockinglayout"></a><a name="adjustdockinglayout"></a>CFrameWndEx::AdjustDockingLayout  
 フレーム ウィンドウにドッキングされているすべてのペインのレイアウトを再計算します。  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `hdwp`  
 複数のウィンドウの位置を格納する構造体へのハンドル。 をクリックします。  
  
### <a name="remarks"></a>コメント  
 によって hdwp 構造体を初期化、 [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672)メソッドです。  
  
##  <a name="a-namedelayupdateframemenua--cframewndexdelayupdateframemenu"></a><a name="delayupdateframemenu"></a>CFrameWndEx::DelayUpdateFrameMenu  
 フレームのメニューを設定し、コマンドの処理がアイドル状態のときに更新します。  
  
```  
virtual void DelayUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hMenuAlt`  
 代替のメニューへのハンドルします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namedockpanea--cframewndexdockpane"></a><a name="dockpane"></a>CFrameWndEx::DockPane  
 フレーム ウィンドウに、指定したウィンドウをドッキングします。  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID=0,  
    LPCRECT lpRect=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 ドッキング コントロール バーへのポインター。  
  
 [入力] `nDockBarID`  
 ドッキングするフレーム ウィンドウの側の ID です。  
  
 [入力] `lpRect`  
 ウィンドウの画面上の位置とサイズを指定する定数 Rect 構造体へのポインター。  
  
### <a name="remarks"></a>コメント  
 `nDockBarID`パラメーターは、次の値のいずれかを設定できます。  
  
-   AFX_IDW_DOCKBAR_TOP  
  
-   AFX_IDW_DOCKBAR_BOTTOM  
  
-   AFX_IDW_DOCKBAR_LEFT  
  
-   AFX_IDW_DOCKBAR_RIGHT  
  
##  <a name="a-namedockpaneleftofa--cframewndexdockpaneleftof"></a><a name="dockpaneleftof"></a>CFrameWndEx::DockPaneLeftOf  
 別のペインの左側に指定されたウィンドウをドッキングします。  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 ドッキングするウィンドウ オブジェクトへのポインター。  
  
 [入力] `pLeftOf`  
 左側で指定されたウィンドウをドッキングするのには、ウィンドウへのポインター`pBar`します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合`pBar`が正常にドッキングされています。 それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定されたツールバーには、`pBar`パラメーターとドッキング ツールバーの左側にあるオプションで指定されて`pLeftOf`パラメーター。  
  
##  <a name="a-nameenableautohidepanesa--cframewndexenableautohidepanes"></a><a name="enableautohidepanes"></a>CFrameWndEx::EnableAutoHidePanes  
 により自動的に隠すペインのモード メイン フレーム ウィンドウの指定した辺にドッキングされている場合。  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwDockStyle`  
 ペインをドッキングするメイン フレーム ウィンドウの端を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、バーによって指定されるフレーム ウィンドウにウィンドウがドッキングされて正常に`dwDockStyle`、`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 `dwDockStyle`次の値のいずれかを設定できます。  
  
-   CBRS_ALIGN_TOP:、フレーム ウィンドウのクライアント領域の上部にドッキングするコントロール バーができるようにします。  
  
-   CBRS_ALIGN_BOTTOM:、フレーム ウィンドウのクライアント領域の下部にドッキングするコントロール バーができるようにします。  
  
-   CBRS_ALIGN_LEFT:、フレーム ウィンドウのクライアント領域の左側にドッキングするコントロール バーができるようにします。  
  
-   CBRS_ALIGN_RIGHT:、フレーム ウィンドウのクライアント領域の右側にドッキングするコントロール バーができるようにします。  
  
##  <a name="a-nameenabledockinga--cframewndexenabledocking"></a><a name="enabledocking"></a>CFrameWndEx::EnableDocking  
 フレーム ウィンドウのペインのドッキングを有効にします。  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwDockStyle`  
 ウィンドウのバーがドッキング メイン フレーム ウィンドウの端を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、バー ペインを正常に指定した辺にドッキングします。 それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 `dwDockStyle`パラメーターは、次の値のいずれかを設定できます。  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="a-nameenablefullscreenmainmenua--cframewndexenablefullscreenmainmenu"></a><a name="enablefullscreenmainmenu"></a>CFrameWndEx::EnableFullScreenMainMenu  
 全画面表示モードのメイン メニューの表示と非表示を切り替えます。  
  
```  
void EnableFullScreenMainMenu(BOOL bEnableMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnableMenu`  
 `TRUE`全画面表示モードでは、メインのメニューを表示する`FALSE`それ以外の場合。  
  
##  <a name="a-nameenablefullscreenmodea--cframewndexenablefullscreenmode"></a><a name="enablefullscreenmode"></a>CFrameWndEx::EnableFullScreenMode  
 フレーム ウィンドウの全画面表示モードを有効にします。  
  
```  
void EnableFullScreenMode(UINT uiFullScreenCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiFullScreenCmd`  
 有効にし、全画面表示モードを無効にするコマンドの ID です。  
  
### <a name="remarks"></a>コメント  
 全画面表示モードですべてのドッキング コントロール バー、ツールバーおよびメニューが非表示になりに全画面表示の上にアクティブなビューのサイズを変更します。  
  
 全画面表示モードを有効にすると、または全画面表示モードを無効にするコマンドの ID を指定する必要があります。 呼び出すことができます`EnableFullScreenMode`からメインフレームの`OnCreate`関数です。 フレーム ウィンドウを全画面表示モードに切り替わる、ときにフレームワークには、指定されたコマンド ID を持つ&1; つのボタンとフローティング ツールバーを作成します。  
  
 画面にメインのメニューを保持する場合は、呼び出す[CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu)します。  
  
##  <a name="a-nameenableloaddockstatea--cframewndexenableloaddockstate"></a><a name="enableloaddockstate"></a>CFrameWndEx::EnableLoadDockState  
 有効またはドッキング状態の読み込みを無効にします。  
  
```  
void EnableLoadDockState(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`ドッキング状態の読み込みを有効にする`FALSE`ドッキング状態の読み込みを無効にします。  
  
##  <a name="a-nameenablepanemenua--cframewndexenablepanemenu"></a><a name="enablepanemenu"></a>CFrameWndEx::EnablePaneMenu  
 有効または、ウィンドウのメニューの自動処理を無効にします。  
  
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
 `TRUE`ポップアップ メニュー バー コントロールの自動処理を有効にするには`FALSE`ポップアップ メニュー バー コントロールの自動処理を無効にします。  
  
 [入力] `uiCustomizeCmd`  
 コマンド ID、**カスタマイズ**メニュー項目です。  
  
 [入力] `strCustomizeLabel`  
 表示されるラベル、**カスタマイズ**メニュー項目  
  
 [入力] `uiViewToolbarsMenuEntryID`  
 コントロール バーで、ポップアップ メニューを開くツール バー メニュー項目の ID。  
  
 [入力] `bContextMenuShowsToolbarsOnly`  
 場合`TRUE`コントロールのコンテキスト メニュー バーにツールバーのみの一覧が表示されます。 場合`FALSE`メニュー、ツールバーとドッキング バーの一覧に表示します。  
  
 [入力] `bViewMenuShowsToolbarsOnly`  
 場合`TRUE`、コントロール バーのメニューには、ツールバーをのみの一覧が表示されます。 場合`FALSE`メニュー、ツールバーとドッキング バーの一覧に表示します。  
  
##  <a name="a-namegetactivepopupa--cframewndexgetactivepopup"></a><a name="getactivepopup"></a>CFrameWndEx::GetActivePopup  
 現在表示されているポップアップ メニューへのポインターを返します。  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在表示されている、ポップアップ メニューへのポインターそれ以外の場合`NULL`します。  
  
##  <a name="a-namegetdefaultresida--cframewndexgetdefaultresid"></a><a name="getdefaultresid"></a>CFrameWndEx::GetDefaultResId  
 フレームワークには、フレーム ウィンドウが読み込まれたときに指定したリソース ID を返します。  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フレームワークが、フレーム ウィンドウに読み込まれるときに、ユーザーが指定されているリソース ID の値。 フレーム ウィンドウには、メニュー バーにいない場合は&0; を返します。  
  
##  <a name="a-namegetdockingmanagera--cframewndexgetdockingmanager"></a><a name="getdockingmanager"></a>CFrameWndEx::GetDockingManager  
 取得、 [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)フレーム ウィンドウのオブジェクト。  
  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)します。  
  
### <a name="remarks"></a>コメント  
 フレーム ウィンドウを作成し、使用、 [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)子ウィンドウのドッキングを管理するオブジェクト。  
  
##  <a name="a-namegetmenubara--cframewndexgetmenubar"></a><a name="getmenubar"></a>CFrameWndEx::GetMenuBar  
 フレーム ウィンドウにアタッチされているメニュー バーのオブジェクトへのポインターを返します。  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メニュー バー オブジェクトが接続されているフレーム ウィンドウへのポインター。  
  
##  <a name="a-namegetpanea--cframewndexgetpane"></a><a name="getpane"></a>CFrameWndEx::GetPane  
 指定した ID を持つペインへのポインターを返します  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 コントロールの id。  
  
### <a name="return-value"></a>戻り値  
 指定した ID を持つペインへのポインター `NULL`このようなウィンドウが存在しない場合。  
  
##  <a name="a-namegetribbonbara--cframewndexgetribbonbar"></a><a name="getribbonbar"></a>CFrameWndEx::GetRibbonBar  
 フレームのリボン バー コントロールを取得します。  
  
```  
CMFCRibbonBar* GetRibbonBar();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)フレーム。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegettearoffbarsa--cframewndexgettearoffbars"></a><a name="gettearoffbars"></a>CFrameWndEx::GetTearOffBars  
 ティアオフ状態にあるウィンドウ オブジェクトの一覧を返します。  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>戻り値  
 参照を`CObList`ティアオフ状態にあるウィンドウ オブジェクトへのポインターのコレクションを格納するオブジェクト。  
  
##  <a name="a-namegettoolbarbuttontooltiptexta--cframewndexgettoolbarbuttontooltiptext"></a><a name="gettoolbarbuttontooltiptext"></a>CFrameWndEx::GetToolbarButtonToolTipText  
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
 既定では、このメソッドは何もしません。 ツール バー ボタンのツールヒントを表示する場合は、このメソッドをオーバーライドします。  
  
##  <a name="a-nameinsertpanea--cframewndexinsertpane"></a><a name="insertpane"></a>CFrameWndEx::InsertPane  
 コントロール バーのリストにウィンドウを挿入し、ドッキング マネージャーに登録します。  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pControlBar`  
 コントロール バーのリストに挿入され、ドッキング マネージャーに登録されるコントロール バーへのポインター。  
  
 `pTarget`  
 ウィンドウの挿入位置の前または後にあるコントロール バーへのポインター。  
  
 `bAfter`  
 `TRUE`挿入する場合は、`pControlBar`後`pTarget`、`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`コントロール バーが正常に挿入し、登録されている場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 各コントロール バーを使用して登録する必要があります、 [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)ドッキング レイアウトの一部を利用します。  
  
##  <a name="a-nameisfullscreena--cframewndexisfullscreen"></a><a name="isfullscreen"></a>CFrameWndEx::IsFullScreen  
 フレーム ウィンドウが全画面表示モードになっているかどうかを判断します。  
  
```  
BOOL IsFullScreen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フレーム ウィンドウが全画面表示モードである場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 全画面表示モードを設定するには呼び出すことによって、 [CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode)メソッドです。  
  
##  <a name="a-nameismenubaravailablea--cframewndexismenubaravailable"></a><a name="ismenubaravailable"></a>CFrameWndEx::IsMenuBarAvailable  
 メニュー バーのオブジェクトへのポインターが有効かどうかを判断します。  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フレーム ウィンドウにメニュー バーです。それ以外の場合`FALSE`します。  
  
##  <a name="a-nameispointneardocksitea--cframewndexispointneardocksite"></a><a name="ispointneardocksite"></a>CFrameWndEx::IsPointNearDockSite  
 配置ゾーンに、ポイントがあるかどうかを決定します。  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 ポイントの位置。  
  
 [出力] `dwBarAlignment`  
 ここで、ポイントが配置されます。 使用可能な値の「解説」表を参照してください。  
  
 [出力] `bOuterEdge`  
 `TRUE`ポイントがフレームの境界線の近くにある場合`FALSE`ポイントがクライアント領域内にある場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ポイントが配置ゾーンにある場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 次の表に、可能な値、`dwBarAlignment`パラメーター。  
  
 `CBRS_ALIGN_TOP`  
 一番上に配置されます。  
  
 `CBRS_ALIGN_RIGHT`  
 右側に配置されます。  
  
 `CBRS_ALIGN_BOTTOM`  
 一番下に配置されます。  
  
 `CBRS_ALIGN_LEFT`  
 左側に配置されます。  
  
##  <a name="a-nameisprintpreviewa--cframewndexisprintpreview"></a><a name="isprintpreview"></a>CFrameWndEx::IsPrintPreview  
 フレーム ウィンドウが印刷プレビュー モードになっているかどうかを判断します。  
  
```  
BOOL IsPrintPreview();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フレーム ウィンドウが印刷プレビュー モードである場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameloadframea--cframewndexloadframe"></a><a name="loadframe"></a>CFrameWndEx::LoadFrame  
 このメソッドは、構造のフレーム ウィンドウを作成し、そのリソースの読み込み後に呼び出されます。  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIDResource`  
 フレームのすべてのリソースを読み込むために使用するリソース ID です。  
  
 [入力] `dwDefaultStyle`  
 既定のフレーム ウィンドウ スタイル。  
  
 [入力] `pParentWnd`  
 フレームの親ウィンドウへのポインター。  
  
 [入力] `pContext`  
 ポインター、 [CCreateContext 構造](../../mfc/reference/ccreatecontext-structure.md)アプリケーションの作成時にフレームワークによって使用されるクラスです。  
  
### <a name="return-value"></a>戻り値  
 メソッドが正常に実行された場合は `TRUE`、それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namenegotiateborderspacea--cframewndexnegotiateborderspace"></a><a name="negotiateborderspace"></a>CFrameWndEx::NegotiateBorderSpace  
 実装して OLE クライアント罫線調整します。  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nBorderCmd`  
 罫線のネゴシエーション コマンドです。 指定できる値については、「解説」を参照してください。  
  
 [入力、出力] `lpRectBorder`  
 境界線のサイズ。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、レイアウトを再計算する必要があります。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 次の表に、可能な値、`nBorderCmd`パラメーター。  
  
 `borderGet`  
 使用可能な OLE クライアント領域を取得します。  
  
 `borderRequest`  
 OLE クライアント領域を要求します。  
  
 `borderSet`  
 OLE クライアント領域を設定します。  
  
##  <a name="a-nameonactivatea--cframewndexonactivate"></a><a name="onactivate"></a>CFrameWndEx::OnActivate  
 フレームワークは、ユーザー入力が切り替えられたにまたはフレームを離れたときに、このメソッドを呼び出します。  
  
```  
afx_msg void OnActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nState`  
 フレームがアクティブまたは非アクティブかどうか。 使用可能な値の「解説」表を参照してください。  
  
 [入力] `pWndOther`  
 現在のユーザー入力に切り替えようとしている別のウィンドウへのポインター。  
  
 [入力] `bMinimized`  
 フレームの最小化された状態です。 `TRUE`フレームを最小限に抑える場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 次の表に、可能な値、`nState`パラメーター。  
  
 `WA_ACTIVE`  
 フレームは、マウスのクリック以外の方法で選択されます。  
  
 `WA_CLICKACTIVE`  
 フレームは、マウスのクリックで選択されます。  
  
 `WA_INACTIVE`  
 フレームが選択されていません。  
  
##  <a name="a-nameonactivateappa--cframewndexonactivateapp"></a><a name="onactivateapp"></a>CFrameWndEx::OnActivateApp  
 アプリケーションが選択または選択解除されたときに、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnActivateApp(
    BOOL bActive,  
    DWORD dwThreadID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bActive`  
 `TRUE`アプリケーションが選択されている場合`FALSE`アプリケーションが選択されていない場合。  
  
 [入力] `dwThreadID`  
 このパラメーターは使用されません。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonchangevisualmanagera--cframewndexonchangevisualmanager"></a><a name="onchangevisualmanager"></a>CFrameWndEx::OnChangeVisualManager  
 フレームへの変更がビジュアル マネージャーへの変更が必要な場合に、フレームワークによって呼び出されます。  
  
```  
afx_msg LRESULT OnChangeVisualManager(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wParam`  
 このパラメーターは使用されません。  
  
 [入力] `lParam`  
 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 常に 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonclosea--cframewndexonclose"></a><a name="onclose"></a>CFrameWndEx::OnClose  
 フレームワークでは、フレームを終了するには、このメソッドを呼び出します。  
  
```  
afx_msg void OnClose();
```  
  
### <a name="remarks"></a>コメント  
 印刷プレビューを終了する Windows メッセージを送信、フレームが印刷プレビュー モードである場合は、それ以外の場合、フレームでは、OLE クライアントをホストしている場合、クライアントが非アクティブ化します。  
  
##  <a name="a-nameonclosedockingpanea--cframewndexonclosedockingpane"></a><a name="onclosedockingpane"></a>CFrameWndEx::OnCloseDockingPane  
 ユーザーがクリックしたときに、フレームワークによって呼び出されます、**閉じる**ドッキング ペインでボタンをクリックします。  
  
```  
virtual BOOL OnCloseDockingPane(CDockablePane* pPane);
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ドッキング バーを閉じることができます。 `FALSE`それ以外の場合  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。 ドッキング バーの非表示を処理する場合は、このメソッドをオーバーライドします。  
  
##  <a name="a-nameoncloseminiframea--cframewndexoncloseminiframe"></a><a name="oncloseminiframe"></a>CFrameWndEx::OnCloseMiniFrame  
 ユーザーがクリックしたときに、フレームワークによって呼び出されます、**閉じる**浮動ミニフレーム ウィンドウのボタンをクリックします。  
  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`浮動ミニフレーム ウィンドウを閉じます。 それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。 浮動ミニフレーム ウィンドウの非表示を処理する場合は、このメソッドをオーバーライドします。  
  
##  <a name="a-nameonclosepopupmenua--cframewndexonclosepopupmenu"></a><a name="onclosepopupmenu"></a>CFrameWndEx::OnClosePopupMenu  
 アクティブなポップアップ メニューが WM_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMenuPopup`  
 ポップアップ メニューへのポインター。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ウィンドウを閉じるしようとしているときに、WM_DESTROY メッセージを送信します。 通知を処理する場合は、このメソッドをオーバーライド`CMFCPopupMenu`フレーム ウィンドウに属しているオブジェクトと、`CMFCPopupMenu`オブジェクトの処理、`WM_DESTROY`ウィンドウが閉じるときに、フレームワークによって送信されたメッセージ。  
  
##  <a name="a-nameoncmdmsga--cframewndexoncmdmsg"></a><a name="oncmdmsg"></a>CFrameWndEx::OnCmdMsg  
 コマンド メッセージをディスパッチします。  
  
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
 コマンド メッセージのカテゴリ。  
  
 [入力、出力] `pExtra`  
 コマンド オブジェクトへのポインター。  
  
 [入力、出力] `pHandlerInfo`  
 コマンド ハンドラーの構造体へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`コマンドのメッセージが処理された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameoncontexthelpa--cframewndexoncontexthelp"></a><a name="oncontexthelp"></a>CFrameWndEx::OnContextHelp  
 コンテキストに関連するヘルプを表示するために、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameoncreatea--cframewndexoncreate"></a><a name="oncreate"></a>CFrameWndEx::OnCreate  
 フレームを作成した後に、フレームワークによって呼び出されます。  
  
```  
afx_msg int OnCreate(LPCREATESTRUCT lpCreateStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpCreateStruct`  
 ポインター、 [CREATESTRUCT 構造体](../../mfc/reference/createstruct-structure.md)新しいフレームのです。  
  
### <a name="return-value"></a>戻り値  
 フレームの作成を続行するには&0;フレームを破棄する-1 です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondestroya--cframewndexondestroy"></a><a name="ondestroy"></a>CFrameWndEx::OnDestroy  
 フレームが破棄されるときに、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnDestroy();
```  
  
### <a name="remarks"></a>コメント  
 アクセラレータ テーブルとすべてのウィンドウが破棄されます。  
  
##  <a name="a-nameondrawmenuimagea--cframewndexondrawmenuimage"></a><a name="ondrawmenuimage"></a>CFrameWndEx::OnDrawMenuImage  
 アプリケーションは、メニュー項目に関連付けられているイメージを描画するときに、フレームワークによって呼び出されます。  
  
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
 レンダリングされるイメージがメニュー ボタンへのポインター。  
  
 [入力] `rectImage`  
 ポインター、`Rect`画面上の位置と、イメージのサイズを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フレームワークは、イメージを正常にレンダリングする場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドをオーバーライドしてが所有するメニュー バーに属しているメニュー項目のイメージの描画をカスタマイズする場合、`CFrameWndEx`派生オブジェクト。  
  
##  <a name="a-nameondrawmenulogoa--cframewndexondrawmenulogo"></a><a name="ondrawmenulogo"></a>CFrameWndEx::OnDrawMenuLogo  
 フレームワークによって呼び出されるときに、`CMFCPopupMenu`オブジェクトは、WM_PAINT メッセージを処理します。  
  
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
 メニュー項目へのポインター。  
  
 [入力] `rectLogo`  
 定数への参照を`CRect` メニューのロゴのサイズと画面上の位置を指定する構造体。  
  
### <a name="remarks"></a>コメント  
 所有するメニュー バーのポップアップ メニューにロゴを表示する場合は、この関数をオーバーライド、`CFrameWndEx`派生オブジェクト。  
  
##  <a name="a-nameondwmcompositionchangeda--cframewndexondwmcompositionchanged"></a><a name="ondwmcompositionchanged"></a>CFrameWndEx::OnDWMCompositionChanged  
 デスクトップ ウィンドウ マネージャー (DWM) の構成を有効になっているか、無効になっているときに、フレームワークによって呼び出されます。  
  
```  
afx_msg LRESULT OnDWMCompositionChanged(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wp`  
 このパラメーターは使用されません。  
  
 [入力] `lp`  
 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 常に 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonexitsizemovea--cframewndexonexitsizemove"></a><a name="onexitsizemove"></a>CFrameWndEx::OnExitSizeMove  
 移動またはサイズ変更、フレームが停止したときに、フレームワークによって呼び出されます。  
  
```  
LRESULT OnExitSizeMove(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wp`  
 このパラメーターは使用されません。  
  
 [入力] `lp`  
 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 常に 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameongetminmaxinfoa--cframewndexongetminmaxinfo"></a><a name="ongetminmaxinfo"></a>CFrameWndEx::OnGetMinMaxInfo  
 ウィンドウのサイズ制限を設定する、フレームのサイズが変更されるときに、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnGetMinMaxInfo(MINMAXINFO FAR* lpMMI);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpMMI`  
 ポインター、 [MINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632605)構造体。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonidleupdatecmduia--cframewndexonidleupdatecmdui"></a><a name="onidleupdatecmdui"></a>CFrameWndEx::OnIdleUpdateCmdUI  
 コマンドの処理がアイドル状態のときに、フレームの表示を更新するためにフレームワークによって呼び出されます。  
  
```  
afx_msg LRESULT OnIdleUpdateCmdUI(
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wParam`  
 このパラメーターは使用されません。  
  
 [入力] `lParam`  
 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 常に 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonlbuttondowna--cframewndexonlbuttondown"></a><a name="onlbuttondown"></a>CFrameWndEx::OnLButtonDown  
 フレームワークは、ユーザーがマウスの左ボタンを押したときに、このメソッドを呼び出します。  
  
```  
afx_msg void OnLButtonDown(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nFlags`  
 ユーザーに修飾子キーが押されたかどうかを示します。 使用可能な値は、パラメーターを参照してください。`wParam`で[WM_LBUTTONDOWN 通知](http://msdn.microsoft.com/library/windows/desktop/ms645607)します。  
  
 [入力] `point`  
 X およびポインターの y 座標、ウィンドウの左上隅を基準に指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonlbuttonupa--cframewndexonlbuttonup"></a><a name="onlbuttonup"></a>CFrameWndEx::OnLButtonUp  
 フレームワークは、マウスの左ボタンを離したときに、このメソッドを呼び出します。  
  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nFlags`  
 ユーザーに修飾子キーが押されたかどうかを示します。 使用可能な値は、パラメーターを参照してください。`wParam`で[WM_LBUTTONUP 通知](http://msdn.microsoft.com/library/windows/desktop/ms645608)します。  
  
 [入力] `point`  
 X およびポインターの y 座標、ウィンドウの左上隅を基準に指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonmenubuttontoolhittesta--cframewndexonmenubuttontoolhittest"></a><a name="onmenubuttontoolhittest"></a>CFrameWndEx::OnMenuButtonToolHitTest  
 フレームワークによって呼び出されますときに、`CMFCToolBarButton`プロセスのオブジェクト、`WM_NCHITTEST`メッセージです。  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
 ツール バー ボタンへのポインター。  
  
 [出力] `pTI`  
 ツールの情報の構造体へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`アプリケーションは入力の場合、`pTI`パラメーター。 それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 特定のメニュー項目のツールヒント情報を提供する場合は、このメソッドをオーバーライドします。  
  
##  <a name="a-nameonmenuchara--cframewndexonmenuchar"></a><a name="onmenuchar"></a>CFrameWndEx::OnMenuChar  
 メニューが表示され、ユーザーがコマンドに対応しないキーを押したときに、フレームワークによって呼び出されます。  
  
```  
afx_msg LRESULT OnMenuChar(
    UINT nChar,  
    UINT nFlags,  
    CMenu* pMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nChar`  
 押されたキーの文字コードです。  
  
 [入力] `nFlags`  
 含む、`MF_POPUP`フラグと表示されるメニューが、サブメニューである場合に、`MF_SYSMENU`表示されるメニューがコントロールのメニューである場合はフラグします。  
  
 [入力] `pMenu`  
 メニューへのポインター。  
  
### <a name="return-value"></a>戻り値  
 上位ワードは、次の値のいずれかにする必要があります。  
  
 `0`  
 フレームワークは、キーストロークを無視してください。  
  
 `1`  
 フレームワークは、メニューを閉じる必要があります。  
  
 `2`  
 フレームワークは、メニューに表示される項目のいずれかを選択してください。 下位ワードには、選択するコマンドの ID が含まれています。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonmousemovea--cframewndexonmousemove"></a><a name="onmousemove"></a>CFrameWndEx::OnMouseMove  
 フレームワークは、ポインターを移動すると、このメソッドを呼び出します。  
  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nFlags`  
 ユーザーに修飾子キーが押されたかどうかを示します。 使用可能な値は、パラメーターを参照してください。`wParam`で[WM_MOUSEMOVE 通知](http://msdn.microsoft.com/library/windows/desktop/ms645616)します。  
  
 [入力] `point`  
 X と y を指定します ウィンドウの左上隅を基準としたポインターの座標。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonmoveminiframea--cframewndexonmoveminiframe"></a><a name="onmoveminiframe"></a>CFrameWndEx::OnMoveMiniFrame  
 ウィンドウ枠に移動したときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pFrame`  
 ポインター、 [CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)ウィンドウです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ウィンドウがドッキングされていません。`FALSE`ペイン ウィンドウがドッキングされた場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonncactivatea--cframewndexonncactivate"></a><a name="onncactivate"></a>CFrameWndEx::OnNcActivate  
 アクティブな状態の変化を示すために、フレームの非クライアント領域が再描画されるときに、フレームワークによって呼び出されます。  
  
```  
afx_msg BOOL OnNcActivate(BOOL bActive);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bActive`  
 `TRUE`アクティブなフレームを描画するには`FALSE`を非アクティブなフレームを描画します。  
  
### <a name="return-value"></a>戻り値  
 既定の処理を続行する 0 以外の値非クライアント領域が非アクティブ化するを防ぐために 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonnccalcsizea--cframewndexonnccalcsize"></a><a name="onnccalcsize"></a>CFrameWndEx::OnNcCalcSize  
 クライアント領域の位置とサイズを計算する必要があるときに、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnNcCalcSize(
    BOOL bCalcValidRects,  
    NCCALCSIZE_PARAMS FAR* lpncsp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bCalcValidRects`  
 `TRUE`アプリケーションが、有効なクライアント領域を指定する必要があります。それ以外の場合、`FALSE`です。  
  
 [入力] `lpncsp`  
 ポインター、`NCCALCSIZE_PARAMS`フレーム ディメンションの変更を格納する構造体。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonnchittesta--cframewndexonnchittest"></a><a name="onnchittest"></a>CFrameWndEx::OnNcHitTest  
 ポインターを移動する、またはマウス ボタンが押されたまたは離されたときに、フレームワークによって呼び出されます。  
  
```  
afx_msg LRESULT OnNcHitTest(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 画面座標でポインターの位置。  
  
### <a name="return-value"></a>戻り値  
 ポインターは、列挙値をヒットします。 使用可能な値の一覧については、次を参照してください。 [WM_NCHITTEST 通知](http://msdn.microsoft.com/library/windows/desktop/ms645618)します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonncmousemovea--cframewndexonncmousemove"></a><a name="onncmousemove"></a>CFrameWndEx::OnNcMouseMove  
 マウス ポインターが非クライアント領域内に移動するときに、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnNcMouseMove(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nHitTest`  
 ポインターは、列挙値をヒットします。 使用可能な値の一覧については、次を参照してください。 [WM_NCHITTEST 通知](http://msdn.microsoft.com/library/windows/desktop/ms645618)します。  
  
 [入力] `point`  
 画面座標でポインターの位置。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonncpainta--cframewndexonncpaint"></a><a name="onncpaint"></a>CFrameWndEx::OnNcPaint  
 非クライアント領域を描画する必要があるときに、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnNcPaint();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonpanechecka--cframewndexonpanecheck"></a><a name="onpanecheck"></a>CFrameWndEx::OnPaneCheck  
 ペインの表示を制御するためにフレームワークによって呼び出されます。  
  
```  
afx_msg BOOL OnPaneCheck(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 ペインのコントロールの ID。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`コマンドが処理された場合`FALSE`コマンドの処理を続行します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonpostpreviewframea--cframewndexonpostpreviewframe"></a><a name="onpostpreviewframe"></a>CFrameWndEx::OnPostPreviewFrame  
 印刷プレビュー モードを変更したときに、フレームワークによって呼び出されます。  
  
```  
afx_msg LRESULT OnPostPreviewFrame(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wParam`  
 このパラメーターは使用されません。  
  
 [入力] `lParam`  
 `TRUE`フレームが印刷プレビュー モードの場合`FALSE`印刷プレビュー モードがオフの場合。  
  
### <a name="return-value"></a>戻り値  
 常に 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonpowerbroadcasta--cframewndexonpowerbroadcast"></a><a name="onpowerbroadcast"></a>CFrameWndEx::OnPowerBroadcast  
 電源管理イベントが発生したときに、フレームワークによって呼び出されます。  
  
```  
afx_msg LRESULT OnPowerBroadcast(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wp`  
 電源管理イベントです。 使用可能な値の一覧については、次を参照してください。 [WM_POWERBROADCAST メッセージ](http://msdn.microsoft.com/library/windows/desktop/aa373247)します。  
  
 [入力] `lp`  
 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 既定のウィンドウ プロシージャを呼び出すことに起因します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonsetmenua--cframewndexonsetmenu"></a><a name="onsetmenu"></a>CFrameWndEx::OnSetMenu  
 フレーム ウィンドウ メニューを置き換えるため、フレームワークによって呼び出されます。  
  
```  
afx_msg LRESULT OnSetMenu(
    WPARAM wp,  
    LPARAM lp);  
  
BOOL OnSetMenu(HMENU hmenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wp`  
 新しいフレーム ウィンドウのメニューへのハンドルします。  
  
 [入力] `lp`  
 新しいウィンドウ メニューへのハンドルします。  
  
 [入力] `hmenu`  
 新しいフレーム ウィンドウのメニューへのハンドルします。  
  
### <a name="return-value"></a>戻り値  
 `LRESULT`既定のウィンドウ プロシージャを呼び出し元からの結果です。  
  
 `BOOL``TRUE`場合は、イベントが処理済み以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonsetpreviewmodea--cframewndexonsetpreviewmode"></a><a name="onsetpreviewmode"></a>CFrameWndEx::OnSetPreviewMode  
 フレームの印刷プレビュー モードを設定するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bPreview`  
 `TRUE`印刷プレビューを有効にするには`FALSE`印刷プレビューを無効にします。  
  
 [入力] `pState`  
 ポインター、`CPrintPreviewState`フレームの状態の構造体。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonsettexta--cframewndexonsettext"></a><a name="onsettext"></a>CFrameWndEx::OnSetText  
 ウィンドウのテキストを設定するためにフレームワークによって呼び出されます。  
  
```  
afx_msg LRESULT OnSetText(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wParam`  
 このパラメーターは使用されません。  
  
 [入力] `lParam`  
 ウィンドウのテキストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 呼び出しから値を返す[DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572)します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonshowcustomizepanea--cframewndexonshowcustomizepane"></a><a name="onshowcustomizepane"></a>CFrameWndEx::OnShowCustomizePane  
 表示するときに、フレームワークによって呼び出され、`QuickCustomizePane`です。  
  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenuPane`  
 簡易へのポインターは、ウィンドウをカスタマイズします。  
  
 [入力] `uiToolbarID`  
 カスタマイズするツールバーのコントロール ID。  
  
### <a name="return-value"></a>戻り値  
 このメソッドの戻り値を常に`TRUE`します。  
  
### <a name="remarks"></a>コメント  
 簡易カスタマイズ メニューは、ツールバーのカスタマイズ ボタンをクリックするときに表示されるポップアップ メニュー  
  
##  <a name="a-nameonshowpanesa--cframewndexonshowpanes"></a><a name="onshowpanes"></a>CFrameWndEx::OnShowPanes  
 ペインを非表示を切り替えるために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
 `TRUE`アプリケーションがペインを表示する場合`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 このメソッドの戻り値を常に`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、ウィンドウを示しています。 場合`bShow`は`TRUE`され、ウィンドウが非表示にまたは`bShow`は`FALSE`ペインが表示されます。  
  
 場合、既定の実装には、ウィンドウが表示されません`bShow`は`TRUE`、ウィンドウが表示およびまたは`bShow`は`FALSE`され、ウィンドウが非表示にします。  
  
 フレームワークを選択すると表示のウィンドウを非表示にするときに、カスタム コードを実行する派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="a-nameonshowpopupmenua--cframewndexonshowpopupmenu"></a><a name="onshowpopupmenu"></a>CFrameWndEx::OnShowPopupMenu  
 ポップアップ メニューを表示するときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenu`  
 ポップアップ メニューへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ポップアップ メニューを表示する場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ポップアップ メニューを表示するときに、カスタム コードを実行する派生クラスでこのメソッドをオーバーライドします。 たとえば、ポップアップ メニューにコマンドの背景色を変更するには、このメソッドをオーバーライドします。  
  
##  <a name="a-nameonsizea--cframewndexonsize"></a><a name="onsize"></a>CFrameWndEx::OnSize  
 フレームのサイズが変更された後、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnSize(
    UINT nType,  
    int cx,  
    int cy);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nType`  
 サイズ変更の種類。 使用可能な値は、パラメーターを参照してください。`wParam`で[WM_SIZE 通知](http://msdn.microsoft.com/library/windows/desktop/ms632646)します。  
  
 [入力] `cx`  
 ピクセル フレームの新しい幅。  
  
 [入力] `cy`  
 ピクセル フレームの新しい高さ。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonsizinga--cframewndexonsizing"></a><a name="onsizing"></a>CFrameWndEx::OnSizing  
 ユーザーのフレーム サイズを変更するときに、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnSizing(
    UINT fwSide,  
    LPRECT pRect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `fwSide`  
 移動したフレームの端。 パラメーターを参照してください`wParam`で[WM_SIZING 通知](http://msdn.microsoft.com/library/windows/desktop/ms632647)します。  
  
 [入力、出力] `pRect`  
 ポインター、 [CRect](../../atl-mfc-shared/reference/crect-class.md)または[RECT](../../mfc/reference/rect-structure1.md)フレームの座標を格納する構造体。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonsyscolorchangea--cframewndexonsyscolorchange"></a><a name="onsyscolorchange"></a>CFrameWndEx::OnSysColorChange  
 システム カラーが変更するときに、フレームワークによって呼び出されます。  
  
```  
void OnSysColorChange();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameontearoffmenua--cframewndexontearoffmenu"></a><a name="ontearoffmenu"></a>CFrameWndEx::OnTearOffMenu  
 アプリケーションには、ティアオフ バーを持つメニューが表示されます。 ときに、フレームワークによって呼び出されます。  
  
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
 `TRUE`ティアオフ バーで、ポップアップ メニューが有効の場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 フレームワークには、コントロール バーが表示されたら、カスタム コードを実行する派生クラスでは、このメソッドをオーバーライドします。  
  
 既定の実装では nothing を返します`TRUE`します。  
  
##  <a name="a-nameontoolbarcontextmenua--cframewndexontoolbarcontextmenu"></a><a name="ontoolbarcontextmenu"></a>CFrameWndEx::OnToolbarContextMenu  
 ツールバーのポップアップ メニューを作成するために、フレームワークによって呼び出されます。  
  
```  
afx_msg LRESULT OnToolbarContextMenu(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wp`  
 このパラメーターは使用されません。  
  
 [入力] `lp`  
 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 常に 1 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameontoolbarcreatenewa--cframewndexontoolbarcreatenew"></a><a name="ontoolbarcreatenew"></a>CFrameWndEx::OnToolbarCreateNew  
 フレームワークでは、新しいツールバーを作成するには、このメソッドを呼び出します。  
  
```  
afx_msg LRESULT OnToolbarCreateNew(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wp`  
 このパラメーターは使用されません。  
  
 [入力] `lp`  
 ツールバーのタイトル バーのテキストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 新しいツールバーへのポインターまたは`NULL`場合ツールバーは作成されませんでした。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameontoolbardeletea--cframewndexontoolbardelete"></a><a name="ontoolbardelete"></a>CFrameWndEx::OnToolbarDelete  
 ツールバーが削除されたときに、フレームワークによって呼び出されます。  
  
```  
afx_msg LRESULT OnToolbarDelete(
    WPARAM, 
    LPARAM lp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力]  
 このパラメーターは使用されません。  
  
 [入力] `lp`  
 ツールバーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ツールバーが削除された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonupdateframemenua--cframewndexonupdateframemenu"></a><a name="onupdateframemenu"></a>CFrameWndEx::OnUpdateFrameMenu  
 フレームのメニューを設定するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hMenuAlt`  
 代替のメニューへのハンドルします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonupdateframetitlea--cframewndexonupdateframetitle"></a><a name="onupdateframetitle"></a>CFrameWndEx::OnUpdateFrameTitle  
 フレームワークでは、フレーム ウィンドウのタイトル バーを更新するには、このメソッドを呼び出します。  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bAddToTitle`  
 `TRUE`フレーム ウィンドウのタイトル バーにアクティブなドキュメントのタイトルを追加するにはそれ以外の場合`FALSE.`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonupdatepanemenua--cframewndexonupdatepanemenu"></a><a name="onupdatepanemenu"></a>CFrameWndEx::OnUpdatePaneMenu  
 ウィンドウ メニューを更新するためにフレームワークによって呼び出されます。  
  
```  
afx_msg void OnUpdatePaneMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pCmdUI`  
 ウィンドウのユーザー インターフェイス オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonwindowposchangeda--cframewndexonwindowposchanged"></a><a name="onwindowposchanged"></a>CFrameWndEx::OnWindowPosChanged  
 ウィンドウ管理メソッドの呼び出しのためのフレーム サイズ、位置、または z オーダーが変更されたときに、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnWindowPosChanged(WINDOWPOS FAR* lpwndpos);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpwndpos`  
 ポインター、 [WINDOWPOS](../../mfc/reference/windowpos-structure1.md)新しいサイズと位置を格納する構造体。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namepanefrompointa--cframewndexpanefrompoint"></a><a name="panefrompoint"></a>CFrameWndEx::PaneFromPoint  
 各ペインで指定したポイントを検索します。  
  
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
 チェック ポイントの画面座標です。  
  
 [入力] `nSensitivity`  
 ポイントを検索するときに、この金額で各コントロール バーの外接する四角形を拡張します。  
  
 [入力] `bExactBar`  
 `TRUE`無視する、`nSensitivity`パラメーター。 そうしないと、`FALSE`です。  
  
 [入力] `pRTCBarType`  
 ない場合`NULL`メソッドは、指定した型のコントロール バーのみを検索します。  
  
 [出力] `dwAlignment`  
 成功した場合、このパラメーターには、指定したポイントに最も近いコントロール バーの側が含まれています。 それ以外の場合、このパラメーターは初期化されていません。  
  
### <a name="return-value"></a>戻り値  
 含むコントロール バーへのポインター、`point`です。`NULL`コントロールが見つからない場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、アプリケーション用にすべてのコントロール バーを検索、`point`です。  
  
 使用`nSensitivity`検索領域のサイズを大ききます。 使用する`pRTCBarType`メソッドを検索するコントロール バーの種類を制限します。  
  
##  <a name="a-namepretranslatemessagea--cframewndexpretranslatemessage"></a><a name="pretranslatemessage"></a>CFrameWndEx::PreTranslateMessage  
 ディスパッチされる前に、特定のウィンドウ メッセージを処理します。  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMsg`  
 ポインター、 [MSG](../../mfc/reference/msg-structure1.md)処理するメッセージを格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 非ゼロの場合は、メッセージが処理されたとディスパッチいない必要があります。メッセージが処理されませんでした、ディスパッチする必要がある場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namerecalclayouta--cframewndexrecalclayout"></a><a name="recalclayout"></a>CFrameWndEx::RecalcLayout  
 フレームとその子ウィンドウのレイアウトを調整します。  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bNotify`  
 レイアウトの変更に関する OLE クライアント アイテム通知するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 フレーム ウィンドウのサイズが変更されたとき、またはコントロール バーの表示/非表示には、このメソッドが呼び出されます。  
  
##  <a name="a-nameremovepanefromdockmanagera--cframewndexremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>CFrameWndEx::RemovePaneFromDockManager  
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
 削除するコントロール バー ペインへのポインター。  
  
 [入力] `bDestroy`  
 `TRUE`それを削除した後、コントロール バーを破棄するには`FALSE`それ以外の場合。  
  
 [入力] `bAdjustLayout`  
 `TRUE`ドッキングのレイアウトを調整するには`FALSE`それ以外の場合。  
  
 [入力] `bAutoHide`  
 `TRUE`コントロール バーが自動非表示モードである場合`FALSE`それ以外の場合。  
  
 [入力] `pBarReplacement`  
 削除されるペインに置き換えられるペインへのポインター。  
  
### <a name="remarks"></a>コメント  
 フレーム ウィンドウのドッキング レイアウトからコントロール バーを削除するのにには、このメソッドを使用します。  
  
 [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)コントロール バーのレイアウトを処理します。 使用して、各コントロール バーをドッキング マネージャーに登録する必要があります、 [CFrameWndEx::AddPane](#addpane)メソッドまたは[CFrameWndEx::InsertPane](#insertpane)メソッドです。  
  
##  <a name="a-namesetdockstatea--cframewndexsetdockstate"></a><a name="setdockstate"></a>CFrameWndEx::SetDockState  
 ドッキング レイアウトをレジストリに格納されているドッキング状態に復元します。  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>パラメーター  
 `state`  
 ドッキング状態。 このパラメーターは無視されます。  
  
##  <a name="a-namesetprintpreviewframea--cframewndexsetprintpreviewframe"></a><a name="setprintpreviewframe"></a>CFrameWndEx::SetPrintPreviewFrame  
 印刷プレビューのフレーム ウィンドウを設定します。  
  
```  
void SetPrintPreviewFrame(CFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 印刷プレビューのフレーム ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetuptoolbarmenua--cframewndexsetuptoolbarmenu"></a><a name="setuptoolbarmenu"></a>CFrameWndEx::SetupToolbarMenu  
 ユーザー定義コマンドをツール バー メニューに挿入します。  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `menu`  
 A`CMenu`オブジェクトを変更できます。  
  
 [入力] `uiViewUserToolbarCmdFirst`  
 最初のユーザー定義のコマンドです。  
  
 [入力] `uiViewUserToolbarCmdLast`  
 最後のユーザー定義のコマンドです。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、ユーザー定義のコマンドを一覧に格納します。 使用`uiViewUserToolbarCmdFirst`と`uiViewUserToolbarCmdList`を挿入するコマンドのインデックスを指定します。  
  
##  <a name="a-nameshowfullscreena--cframewndexshowfullscreen"></a><a name="showfullscreen"></a>CFrameWndEx::ShowFullScreen  
 メインフレームの全画面表示モードと通常モードに切り替えます。  
  
```  
void ShowFullScreen();
```  
  
##  <a name="a-nameshowpanea--cframewndexshowpane"></a><a name="showpane"></a>CFrameWndEx::ShowPane  
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
 コントロール バーを表示または非表示へのポインター。  
  
 [入力] `bShow`  
 場合`TRUE`アプリケーションは、コントロール バーを表示します。 それ以外の場合、アプリケーションでは、コントロール バーを非表示にします。  
  
 [入力] `bDelay`  
 場合`TRUE`、framework 呼び出しまでのドッキング レイアウトの調整を遅らせる[CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)します。 すぐにドッキング レイアウトを再計算それ以外の場合。  
  
 [入力] `bActivate`  
 場合`TRUE`、コントロール バーをアクティブにします。 それ以外の場合、非アクティブな状態でコントロール バーを表示します。  
  
##  <a name="a-nameupdatecaptiona--cframewndexupdatecaption"></a><a name="updatecaption"></a>CFrameWndEx::UpdateCaption  
 ウィンドウ フレームのキャプションを更新するためにフレームワークによって呼び出されます。  
  
```  
void UpdateCaption();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namewinhelpa--cframewndexwinhelp"></a><a name="winhelp"></a>CFrameWndEx::WinHelp  
 WinHelp アプリケーションとコンテキストのいずれかを呼び出す関連ヘルプ。  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwData`  
 依存するデータ、`nCmd`パラメーター。 使用可能な値の一覧については、次を参照してください。 [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267)します。  
  
 `nCmd`  
 ヘルプ コマンドです。 使用可能な値の一覧については、次を参照してください。 [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267)します。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)

