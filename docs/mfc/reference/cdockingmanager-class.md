---
title: "CDockingManager クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockingManager
- AFXDOCKINGMANAGER/CDockingManager
- AFXDOCKINGMANAGER/CDockingManager::AddDockSite
- AFXDOCKINGMANAGER/CDockingManager::AddHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::AddMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::AddPane
- AFXDOCKINGMANAGER/CDockingManager::AdjustDockingLayout
- AFXDOCKINGMANAGER/CDockingManager::AdjustPaneFrames
- AFXDOCKINGMANAGER/CDockingManager::AdjustRectToClientArea
- AFXDOCKINGMANAGER/CDockingManager::AlignAutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::AutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::BringBarsToTop
- AFXDOCKINGMANAGER/CDockingManager::BuildPanesMenu
- AFXDOCKINGMANAGER/CDockingManager::CalcExpectedDockedRect
- AFXDOCKINGMANAGER/CDockingManager::Create
- AFXDOCKINGMANAGER/CDockingManager::DeterminePaneAndStatus
- AFXDOCKINGMANAGER/CDockingManager::DisableRestoreDockState
- AFXDOCKINGMANAGER/CDockingManager::DockPane
- AFXDOCKINGMANAGER/CDockingManager::DockPaneLeftOf
- AFXDOCKINGMANAGER/CDockingManager::EnableAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::EnableDocking
- AFXDOCKINGMANAGER/CDockingManager::EnableDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::EnablePaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::FindDockSite
- AFXDOCKINGMANAGER/CDockingManager::FindDockSiteByPane
- AFXDOCKINGMANAGER/CDockingManager::FindPaneByID
- AFXDOCKINGMANAGER/CDockingManager::FixupVirtualRects
- AFXDOCKINGMANAGER/CDockingManager::FrameFromPoint
- AFXDOCKINGMANAGER/CDockingManager::GetClientAreaBounds
- AFXDOCKINGMANAGER/CDockingManager::GetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::GetDockSiteFrameWnd
- AFXDOCKINGMANAGER/CDockingManager::GetEnabledAutoHideAlignment
- AFXDOCKINGMANAGER/CDockingManager::GetMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::GetOuterEdgeBounds
- AFXDOCKINGMANAGER/CDockingManager::GetPaneList
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManager
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManagerPermanent
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingTheme
- AFXDOCKINGMANAGER/CDockingManager::HideAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::InsertDockSite
- AFXDOCKINGMANAGER/CDockingManager::InsertPane
- AFXDOCKINGMANAGER/CDockingManager::IsDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::IsInAdjustLayout
- AFXDOCKINGMANAGER/CDockingManager::IsOLEContainerMode
- AFXDOCKINGMANAGER/CDockingManager::IsPointNearDockSite
- AFXDOCKINGMANAGER/CDockingManager::IsPrintPreviewValid
- AFXDOCKINGMANAGER/CDockingManager::LoadState
- AFXDOCKINGMANAGER/CDockingManager::LockUpdate
- AFXDOCKINGMANAGER/CDockingManager::OnActivateFrame
- AFXDOCKINGMANAGER/CDockingManager::OnClosePopupMenu
- AFXDOCKINGMANAGER/CDockingManager::OnMoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::OnPaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::PaneFromPoint
- AFXDOCKINGMANAGER/CDockingManager::ProcessPaneContextMenuCommand
- AFXDOCKINGMANAGER/CDockingManager::RecalcLayout
- AFXDOCKINGMANAGER/CDockingManager::ReleaseEmptyPaneContainers
- AFXDOCKINGMANAGER/CDockingManager::RemoveHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::RemoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::RemovePaneFromDockManager
- AFXDOCKINGMANAGER/CDockingManager::ReplacePane
- AFXDOCKINGMANAGER/CDockingManager::ResortMiniFramesForZOrder
- AFXDOCKINGMANAGER/CDockingManager::SaveState
- AFXDOCKINGMANAGER/CDockingManager::SendMessageToMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::Serialize
- AFXDOCKINGMANAGER/CDockingManager::SetAutohideZOrder
- AFXDOCKINGMANAGER/CDockingManager::SetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::SetDockState
- AFXDOCKINGMANAGER/CDockingManager::SetPrintPreviewMode
- AFXDOCKINGMANAGER/CDockingManager::SetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::ShowDelayShowMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::ShowPanes
- AFXDOCKINGMANAGER/CDockingManager::StartSDocking
- AFXDOCKINGMANAGER/CDockingManager::StopSDocking
- AFXDOCKINGMANAGER/CDockingManager::m_bHideDockingBarsInContainerMode
- AFXDOCKINGMANAGER/CDockingManager::m_dockModeGlobal
- AFXDOCKINGMANAGER/CDockingManager::m_nDockSensitivity
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeDockingBarDock
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeToolBarDock
dev_langs:
- C++
helpviewer_keywords:
- CDockingManager class
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
caps.latest.revision: 37
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
ms.openlocfilehash: 106046dc9dc671b5baea7c6df78b91ba37098978
ms.lasthandoff: 02/24/2017

---
# <a name="cdockingmanager-class"></a>CDockingManager クラス
メイン フレーム ウィンドウのドッキング レイアウトを制御するコア機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDockingManager : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDockingManager::AddDockSite](#adddocksite)|ドッキング ペインを作成し、コントロール バーのリストに追加します。|  
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|バーへのハンドルの追加 ウィンドウを非表示の MDI タブ付きバー ペインの一覧にします。|  
|[CDockingManager::AddMiniFrame](#addminiframe)|フレームをミニフレームの一覧に追加します。|  
|[CDockingManager::AddPane](#addpane)|ペインをドッキング マネージャーに登録します。|  
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|再計算し、フレーム ウィンドウ内のすべてのウィンドウのレイアウトを調整します。|  
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|により、`WM_NCCALCSIZE`すべてのペインに送信されるメッセージと`CPaneFrameWnd`windows です。|  
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|四角形の配置を調整します。|  
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|全体の幅またはで囲まれたフレームのクライアント領域の高さはドッキング サイトになるため、自動非表示モードのドッキング ペインのサイズを変更します。|  
|[CDockingManager::AutoHidePane](#autohidepane)|自動的に隠すツールバーを作成します。|  
|[CDockingManager::BringBarsToTop](#bringbarstotop)|最上位に指定された配置を含むドッキング バーが表示されます。|  
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|ドッキング ペインおよびツールバーの名前をメニューに追加します。|  
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|ドッキング ウィンドウの予想される四角形を計算します。|  
|[CDockingManager::Create](#create)|ドッキング マネージャーを作成します。|  
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|指定した位置とドッキング状態を含むウィンドウを決定します。|  
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|有効またはレジストリからのドッキング レイアウトの読み込みを無効にします。|  
|[CDockingManager::DockPane](#dockpane)|別のウィンドウまたはフレームのウィンドウ ペインをドッキングします。|  
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|ペインを別のペインの左側にドッキングします。|  
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|メイン フレーム ウィンドウのドッキングを有効に、ドッキング ペインを作成し、コントロール バーのリストに追加します。|  
|[CDockingManager::EnableDocking](#enabledocking)|ドッキング ペインを作成し、メイン フレーム ウィンドウのドッキングを有効にします。|  
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|すべてのドッキング ペインのキャプションにポップアップ メニューを開き、追加のボタンが表示されます。|  
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|マウスの右ボタンをクリックし、ライブラリが WM_CONTEXTMENU メッセージを処理するときにアプリケーションのツールバーとドッキング ペインの一覧を持つ特別なコンテキスト メニューを表示するライブラリを通知します。|  
|[CDockingManager::FindDockSite](#finddocksite)|バーを取得は、指定した位置と指定された配置を含むウィンドウ。|  
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|バーを返す対象のバー ペインの id を持つウィンドウです。|  
|[CDockingManager::FindPaneByID](#findpanebyid)|指定したコントロール ID によってウィンドウを検索します。|  
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|ツールバーの現在位置の仮想四角形をコミットします。|  
|[CDockingManager::FrameFromPoint](#framefrompoint)|指定したポイントを含むフレームを返します。|  
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|クライアント領域の境界を示す四角形を取得します。|  
|[CDockingManager::GetDockingMode](#getdockingmode)|現在のドッキング モードを返します。|  
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|親ウィンドウ フレームへのポインターを取得します。|  
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|ウィンドウの有効な配置を返します。|  
|[CDockingManager::GetMiniFrames](#getminiframes)|ミニフレームの一覧を取得します。|  
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|フレームの外側のエッジを含む四角形を取得します。|  
|[CDockingManager::GetPaneList](#getpanelist)|ドッキングのマネージャーに属するペインの一覧を返します。 これには、すべての浮動ペインが含まれます。|  
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|スマート ドッキング マネージャーへのポインターを取得します。|  
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|スマート ドッキング マネージャーへのポインターを取得します。|  
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|ドッキング マネージャーのスマート ドッキングのパラメーターを返します。|  
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|スマート ドッキング マーカーの表示に使用されるテーマを返す静的メソッドです。|  
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|自動非表示モードになっているウィンドウを非表示にします。|  
|[CDockingManager::InsertDockSite](#insertdocksite)|ドッキング ペインを作成し、コントロール バーのリストに挿入します。|  
|[CDockingManager::InsertPane](#insertpane)|コントロール バーのリストには、コントロール パネルを挿入します。|  
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|すべてのペインのキャプションにポップアップ メニューが表示されるかどうかを指定します。|  
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|すべてのウィンドウ レイアウトを調整するかどうかを判断します。|  
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|ドッキング マネージャーが OLE コンテナー モードになっているかどうかを指定します。|  
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|指定した点がドッキング サイトの近くにいるかどうかを判断します。|  
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|印刷プレビュー モードが設定されているかどうかを判断します。|  
|[CDockingManager::LoadState](#loadstate)|レジストリからドッキング マネージャーの状態を読み込みます。|  
|[CDockingManager::LockUpdate](#lockupdate)|指定されたウィンドウをロックします。|  
|[CDockingManager::OnActivateFrame](#onactivateframe)|フレーム ウィンドウはアクティブになり、または非アクティブ化するときに、フレームワークによって呼び出されます。|  
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|アクティブなポップアップ メニューが WM_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。|  
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|ウィンドウのリストを持つメニューを作成するときに、フレームワークによって呼び出されます。|  
|[CDockingManager::PaneFromPoint](#panefrompoint)|指定したポイントを含むペインを返します。|  
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|選択するか、指定されたコマンドのチェック ボックスをオフにして表示されるペインのレイアウトを再計算するため、フレームワークによって呼び出されます。|  
|[CDockingManager::RecalcLayout](#recalclayout)|コントロールのリストに提示されるコントロールの内部のレイアウトを再計算します。|  
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|空のペインのコンテナーを解放します。|  
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|指定した非表示のウィンドウ バーを削除します。|  
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|ミニフレームの一覧から、指定したフレームを削除します。|  
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|ペインの登録を解除し、ドッキング マネージャーの一覧から削除されます。|  
|[CDockingManager::ReplacePane](#replacepane)|ペインを別のペインに置き換えます。|  
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|ミニフレームの一覧内のフレームを使用します。|  
|[CDockingManager::SaveState](#savestate)|ドッキング マネージャーの状態をレジストリに保存します。|  
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|ミニのすべてのフレームを指定したメッセージを送信します。|  
|[CDockingManager::Serialize](#serialize)|ドッキングのマネージャーをアーカイブに書き込みます。 (上書き[指定](../../mfc/reference/cobject-class.md#serialize))。|  
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|サイズ、幅、およびコントロール バーと、指定したウィンドウの高さを設定します。|  
|[CDockingManager::SetDockingMode](#setdockingmode)|ドッキングのモードを設定します。|  
|[CDockingManager::SetDockState](#setdockstate)|コントロール バー、ミニ フレーム、および自動非表示バーのドッキング状態を設定します。|  
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|印刷プレビューで表示されるバーの印刷プレビュー モードを設定します。|  
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|スマート ドッキングの動作を定義するパラメーターを設定します。|  
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|ミニフレーム ウィンドウの表示と非表示を切り替えます。|  
|[CDockingManager::ShowPanes](#showpanes)|コントロールと自動的に隠す の横棒のペインの表示と非表示を切り替えます。|  
|[CDockingManager::StartSDocking](#startsdocking)|スマート ドッキング マネージャーの配置に基づいて、指定したウィンドウのスマート ドッキングを開始します。|  
|[CDockingManager::StopSDocking](#stopsdocking)|スマート ドッキングを停止します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|OLE コンテナー モードのペインをドッキング マネージャーが非表示にするかどうかを指定します。|  
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|グローバル ドッキング モードを指定します。|  
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|ドッキングの感度を指定します。|  
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|イミディ エイト モードでドッキング ドッキング ペインをドッキングする前に、時間 (ミリ秒単位) を指定します。|  
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|ツールバーがメイン フレーム ウィンドウにドッキングされるまでは、時間 (ミリ秒単位) を指定します。|  
  
## <a name="remarks"></a>コメント  
 メイン フレーム ウィンドウを作成し、このクラスを自動的に初期化します。  
  
 ドッキング マネージャー オブジェクトは、すべてのリストとドッキング レイアウト内にあるすべてのペインのリストを保持[CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)メイン フレーム ウィンドウに属するウィンドウのことです。  
  
 `CDockingManager`クラスは、ウィンドウの検索に使用できる一部のサービスを実装または`CPaneFrameWnd`ウィンドウです。 通常はこれらのサービスを直接呼び出しませんメイン フレーム ウィンドウのオブジェクトにラップされるためです。 詳細については、次を参照してください。 [CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)します。  
  
## <a name="customization-tips"></a>カスタマイズのヒント  
 次のヒントを適用する`CDockingManager`オブジェクト。  
  
- [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)ドッキング モードをサポートしています。  
  
    - `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    - `AFX_DOCK_TYPE::DT_STANDARD`  
  
    - `AFX_DOCK_TYPE::DT_SMART`  
  
     これらのドッキング モードが定義されている[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)呼び出すことによって設定および[CDockingManager::SetDockingMode](#setdockingmode)します。  
  
-   サイズを変更できない、フローティング ウィンドウを作成する場合を呼び出す、 [CDockingManager::AddPane](#addpane)メソッドです。 このメソッドでは、ウィンドウのレイアウトは、ドッキングのマネージャーのウィンドウを登録します。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CDockingManager`を構成するクラス、`CDockingManager`オブジェクトです。 例では、すべてのドッキング ペインのキャプションにポップアップ メニューを開き、追加のボタンを表示する方法と、オブジェクトのドッキング モードを設定する方法を示します。 このコード スニペットの一部である、 [Visual Studio のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&24;](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxDockingManager.h  
  
##  <a name="adddocksite"></a>CDockingManager::AddDockSite  
 ドッキング ペインを作成し、コントロール バーのリストに追加します。  
  
```  
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `info`  
 含む情報構造体への参照はドッキング ペインの配置です。  
  
 [出力] `ppDockBar`  
 新しいドッキング ペインへのポインターへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング ペインが正常に作成された場合`FALSE`それ以外の場合。  
  
##  <a name="addhiddenmditabbedbar"></a>CDockingManager::AddHiddenMDITabbedBar  
 バーへのハンドルの追加 ウィンドウを非表示の MDI タブ付きバー ペインの一覧にします。  
  
```  
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 バーへのポインター ウィンドウ  
  
##  <a name="addpane"></a>CDockingManager::AddPane  
 ペインをドッキング マネージャーに登録します。  
  
```  
BOOL AddPane(
    CBasePane* pWnd,  
    BOOL bTail = TRUE,  
    BOOL bAutoHide = FALSE,  
    BOOL bInsertForOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `pWnd`  
 ドッキングのマネージャーに追加するウィンドウを指定します。  
  
 [入力] `bTail`  
 `TRUE`ドッキング マネージャーのペインの一覧の最後に、ウィンドウを追加するにはそれ以外の場合、`FALSE`です。  
  
 [入力] `bAutoHide`  
 内部使用のみ。 常に既定値を使用して`FALSE`します。  
  
 [入力] `bInsertForOuterEdge`  
 内部使用のみ。 常に既定値を使用して`FALSE`します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ウィンドウはドッキング マネージャーに正常に登録されましたそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 サイズを変更できない、フローティング ウィンドウをドッキング マネージャーに登録するには、このメソッドを呼び出します。 ウィンドウを登録しない場合が正しく表示されないドッキング マネージャーを配置するとします。  
  
##  <a name="adjustdockinglayout"></a>CDockingManager::AdjustDockingLayout  
 再計算し、フレーム ウィンドウ内のすべてのウィンドウのレイアウトを調整します。  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hdwp`  
 遅延ウィンドウ位置構造体を指定します。 詳細については、次を参照してください。 [Windows Data Types](http://msdn.microsoft.com/library/windows/desktop/aa383751)します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addminiframe"></a>CDockingManager::AddMiniFrame  
 フレームをミニフレームの一覧に追加します。  
  
```  
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 フレームへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フレームがミニフレームの一覧にないと正常に追加された場合`FALSE`それ以外の場合。  
  
##  <a name="adjustpaneframes"></a>CDockingManager::AdjustPaneFrames  
 により、`WM_NCCALCSIZE`すべてのペインに送信されるメッセージと`CPaneFrameWnd`windows です。  
  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="adjustrecttoclientarea"></a>CDockingManager::AdjustRectToClientArea  
 四角形の配置を調整します。  
  
```  
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectResult`  
 参照、`CRect`オブジェクト  
  
 [入力] `dwAlignment`  
 配置、`CRect`オブジェクト  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合の配置、`CRect`オブジェクトが調整されました。`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 `dwAlignment`パラメーターは、次の値のいずれかを設定できます。  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="alignautohidepane"></a>CDockingManager::AlignAutoHidePane  
 全体の幅またはで囲まれたフレームのクライアント領域の高さはドッキング サイトになるため、自動非表示モードのドッキング ペインのサイズを変更します。  
  
```  
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,  
    BOOL bIsVisible = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDefaultSlider`  
 ドッキング スライダー ペイン。  
  
 [入力] `bIsVisible`  
 `TRUE`ドッキング ペインを表示する場合`FALSE`それ以外の場合。  
  
##  <a name="autohidepane"></a>CDockingManager::AutoHidePane  
 自動的に隠すツールバーを作成します。  
  
```  
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,  
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 バーへのポインター ウィンドウです。  
  
 [入力] `pCurrAutoHideToolBar`  
 自動非表示 ツールバーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `NULL`自動ツールバーを非表示にする場合は作成されませんでした。それ以外の場合、新しいツールバーへのポインター。  
  
##  <a name="bringbarstotop"></a>CDockingManager::BringBarsToTop  
 最上位に指定された配置を含むドッキング バーが表示されます。  
  
```  
void BringBarsToTop(
    DWORD dwAlignment = 0,  
    BOOL bExcludeDockedBars = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 他のウィンドウの一番上に置かれるドッキング バーの配置です。  
  
 [入力] `bExcludeDockedBars`  
 `TRUE`一番上にからドッキング バーを除外するにはそれ以外の場合`FALSE`します。  
  
##  <a name="buildpanesmenu"></a>CDockingManager::BuildPanesMenu  
 ドッキング ペインおよびツールバーの名前をメニューに追加します。  
  
```  
void BuildPanesMenu(
    CMenu& menu,  
    BOOL bToolbarsOnly);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `menu`  
 ドッキング ペインおよびツールバーの名前を追加するメニューです。  
  
 [入力] `bToolbarsOnly`  
 `TRUE`ツールバー名のみをメニューに追加するには`FALSE`それ以外の場合。  
  
##  <a name="calcexpecteddockedrect"></a>CDockingManager::CalcExpectedDockedRect  
 ドッキング ウィンドウの予想される四角形を計算します。  
  
```  
void CalcExpectedDockedRect(
    CWnd* pWnd,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 ドッキングするウィンドウへのポインター。  
  
 [入力] `ptMouse`  
 マウスの位置。  
  
 [出力] `rectResult`  
 計算される四角形。  
  
 [入力] `bDrawTab`  
 `TRUE`タブを描画するにはそれ以外の場合`FALSE`します。  
  
 [出力] `ppTargetBar`  
 ターゲット ウィンドウへのポインターへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ウィンドウがユーザーによって指定された地点をウィンドウをドラッグする場合に使用する四角形を計算`ptMouse`し、そこにドッキングします。  
  
##  <a name="create"></a>CDockingManager::Create  
 ドッキング マネージャーを作成します。  
  
```  
BOOL Create(CFrameWnd* pParentWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentWnd`  
 ドッキングのマネージャーの親のフレームへのポインター。 この値である必要があります`NULL`します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`いつも。  
  
##  <a name="determinepaneandstatus"></a>CDockingManager::DeterminePaneAndStatus  
 指定した位置とドッキング状態を含むウィンドウを決定します。  
  
```  
virtual AFX_CS_STATUS DeterminePaneAndStatus(
    CPoint pt,  
    int nSensitivity,  
    DWORD dwEnabledAlignment,  
    CBasePane** ppTargetBar,  
    const CBasePane* pBarToIgnore,  
    const CBasePane* pBarToDock);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pt`  
 確認するウィンドウの場所。  
  
 [入力] `nSensitivity`  
 チェックする各ペインのウィンドウの四角形を増加する値。 ペインは、指定したポイントが拡大されたこの領域にある場合に、検索条件を満たします。  
  
 [入力] `dwEnabledAlignment`  
 ドッキング ペインの配置です。  
  
 [出力] `ppTargetBar`  
 ターゲット ウィンドウへのポインターへのポインター。  
  
 [入力] `pBarToIgnore`  
 このメソッドは無視するウィンドウ。  
  
 [入力] `pBarToDock`  
 このウィンドウがドッキングされています。  
  
### <a name="return-value"></a>戻り値  
 ドッキング状態です。  
  
### <a name="remarks"></a>コメント  
 ドッキング状態は、次の値のいずれかになります。  
  
|AFX_CS_STATUS 値|説明|  
|---------------------------|-------------|  
|CS_NOTHING|ポインターがドッキング サイト上でないです。 そのため、ウィンドウがようにフローティングします。|  
|CS_DOCK_IMMEDIATELY|イミディ エイト モードでのドッキング サイト上に、ポインターが (DT_IMMEDIATE スタイルが有効になって) ため、直ちに、ウィンドウをドッキングする必要があります。|  
|CS_DELAY_DOCK|ポインターとは別のドッキング ペインまたはメイン フレームの端は、ドッキング サイト上です。|  
|CS_DELAY_DOCK_TO_TAB|ポインターは、タブ付きウィンドウにドッキングするウィンドウをドッキング サイトにです。 これは、別のドッキング ペインのキャプションまたはタブ付きペインのタブ領域上にマウスが発生します。|  
  
##  <a name="disablerestoredockstate"></a>CDockingManager::DisableRestoreDockState  
 有効またはレジストリからのドッキング レイアウトの読み込みを無効にします。  
  
```  
void DisableRestoreDockState(BOOL bDisable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDisable`  
 `TRUE`レジストリからのドッキング レイアウトの読み込みを無効にするにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 アプリケーションの状態を読み込むときに、ドッキング ペインおよびツールバーの現在のレイアウトを維持する必要がある場合は、このメソッドを呼び出します。  
  
##  <a name="dockpane"></a>CDockingManager::DockPane  
 別のウィンドウまたはフレームのウィンドウ ペインをドッキングします。  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 バーへのポインターにドッキングするウィンドウです。  
  
 [入力] `nDockBarID`  
 ドッキングするのには、バーの id です。  
  
 [入力] `lpRect`  
 移行先の四角形。  
  
##  <a name="dockpaneleftof"></a>CDockingManager::DockPaneLeftOf  
 ペインを別のペインの左側にドッキングします。  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBarToDock`  
 左側にドッキングするウィンドウへのポインター`pTargetBar`します。  
  
 [入力] `pTargetBar`  
 ターゲット ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウが正常にドッキングされている場合それ以外の場合、`FALSE`です。  
  
##  <a name="enableautohidepanes"></a>CDockingManager::EnableAutoHidePanes  
 メイン フレーム ウィンドウのドッキングを有効に、ドッキング ペインを作成し、コントロール バーのリストに追加します。  
  
```  
BOOL EnableAutoHidePanes(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwStyle`  
 ドッキングの配置。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング ペインが正常に作成された場合`FALSE`それ以外の場合。  
  
##  <a name="enabledocking"></a>CDockingManager::EnableDocking  
 ドッキング ペインを作成し、メイン フレーム ウィンドウのドッキングを有効にします。  
  
```  
BOOL EnableDocking(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwStyle`  
 ドッキングの配置。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング ペインが正常に作成された場合`FALSE`それ以外の場合。  
  
##  <a name="enabledocksitemenu"></a>CDockingManager::EnableDockSiteMenu  
 すべてのドッキング ペインのキャプションにポップアップ メニューを開き、追加のボタンが表示されます。  
  
```  
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`ドッキング サイトのメニューを有効にするにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ドッキング サイト メニューには、ペインのドッキング状態を変更するための次のオプションが表示されます。  
  
- `Floating`-ペインをフローティングします。  
  
- `Docking`-のペインが最後にドッキングされた位置にあるメイン フレーム ウィンドウをドッキングします。  
  
- `AutoHide`ウィンドウを自動的に隠すモードに切り替えます  
  
- `Hide`-ペインを非表示になります  
  
 既定では、このメニューは表示されません。  
  
##  <a name="enablepanecontextmenu"></a>CDockingManager::EnablePaneContextMenu  
 マウスの右ボタンをクリックし、ライブラリが WM_CONTEXTMENU メッセージを処理するときにアプリケーションのツールバーとドッキング ペインの一覧を持つ特別なコンテキスト メニューを表示するライブラリを通知します。  
  
```  
void EnablePaneContextMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeText,  
    BOOL bToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 場合`TRUE`、ライブラリ サポートをオンに自動のコンテキスト メニューの場合は`FALSE`ライブラリは、自動のコンテキスト メニューのサポートをオフにします。  
  
 [入力] `uiCustomizeCmd`  
 コマンド id、**カスタマイズ**メニューの項目。  
  
 [入力] `strCustomizeText`  
 テキスト、**カスタマイズ**項目。  
  
 [入力] `bToolbarsOnly`  
 場合`TRUE`、メニューは、場合に、アプリケーションのツールバーの一覧だけを表示`FALSE`ライブラリでは、アプリケーションのドッキング ペインをこの一覧に追加します。  
  
##  <a name="finddocksite"></a>CDockingManager::FindDockSite  
 バーを取得は、指定した位置と指定された配置を含むウィンドウ。  
  
```  
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,  
    BOOL bOuter);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 バーの配置 ウィンドウ。  
  
 [入力] `bOuter`  
 場合`TRUE`リスト内のコントロール バーのヘッドの位置にあるバーを取得します。 それ以外の場合、コントロール バーのリスト内の末尾位置にあるバーを取得します。  
  
### <a name="return-value"></a>戻り値  
 指定した位置が、ドッキング ペイン`NULL`それ以外の場合。  
  
##  <a name="findpanebyid"></a>CDockingManager::FindPaneByID  
 指定したコントロール ID によってウィンドウを検索します。  
  
```  
virtual CBasePane* FindPaneByID(
    UINT uBarID,  
    BOOL bSearchMiniFrames = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uBarID`  
 検索するウィンドウのコントロール ID を指定します。  
  
 [入力] `bSearchMiniFrames`  
 `TRUE`検索に含めるすべての浮動ペイン、します。 `FALSE`ドッキング ウィンドウだけを含める。  
  
### <a name="return-value"></a>戻り値  
 [CBasePane](../../mfc/reference/cbasepane-class.md)を指定したコントロール ID を持つオブジェクトまたは`NULL`場合は、指定したウィンドウが見つかりません。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="finddocksitebypane"></a>CDockingManager::FindDockSiteByPane  
 バーを返す対象のバー ペインの id を持つウィンドウです。  
  
```  
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pTargetBar`  
 対象のバー ペインへのポインター。  
  
### <a name="return-value"></a>戻り値  
 バーを対象のバー ペインの id を持つペイン`NULL`バー ウィンドウなどが存在しない場合。  
  
##  <a name="fixupvirtualrects"></a>CDockingManager::FixupVirtualRects  
 ツールバーの現在位置の仮想四角形をコミットします。  
  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>コメント  
 アプリケーションの元の位置が記憶されて、ユーザーは、ツールバーのドラッグを開始、*仮想の長方形*します。 ドッキング サイト間で、ユーザーがツールバーを移動するとき、ツールバーには他のツールバーが変わることがあります。 他のツールバーの元の位置は、対応する仮想四角形に格納されます。  
  
##  <a name="framefrompoint"></a>CDockingManager::FrameFromPoint  
 指定したポイントを含むフレームを返します。  
  
```  
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,  
    CPaneFrameWnd* pFrameToExclude,  
    BOOL bFloatMultiOnly) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pt`  
 確認の画面座標で、ポイントを指定します。  
  
 [入力] `pFrameToExclude`  
 除外するフレームへのポインター。  
  
 [入力] `bFloatMultiOnly`  
 `TRUE`インスタンスではなくフレームを除外する`CMultiPaneFrameWnd`です。`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 指定したポイントを含むフレーム`NULL`それ以外の場合。  
  
##  <a name="getclientareabounds"></a>CDockingManager::GetClientAreaBounds  
 クライアント領域の境界を示す四角形を取得します。  
  
```  
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rcClient`  
 クライアント領域の境界を示す四角形への参照。  
  
### <a name="return-value"></a>戻り値  
 クライアント領域の境界を示す四角形。  
  
##  <a name="getdockingmode"></a>CDockingManager::GetDockingMode  
 現在のドッキング モードを返します。  
  
```  
static AFX_DOCK_TYPE GetDockingMode();
```  
  
### <a name="return-value"></a>戻り値  
 現在のドッキング モードを表す列挙値。 次の値のいずれかを指定できます。  
  
- `DT_STANDARD`  
  
- `DT_IMMEDIATE`  
  
- `DT_SMART`  
  
### <a name="remarks"></a>コメント  
 ドッキングのモードを設定するには、呼び出す[CDockingManager::SetDockingMode](#setdockingmode)します。  
  
##  <a name="getdocksiteframewnd"></a>CDockingManager::GetDockSiteFrameWnd  
 親ウィンドウ フレームへのポインターを取得します。  
  
```  
CFrameWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 親ウィンドウ フレームへのポインター。  
  
##  <a name="getenabledautohidealignment"></a>CDockingManager::GetEnabledAutoHideAlignment  
 ウィンドウの有効な配置を返します。  
  
```  
DWORD GetEnabledAutoHideAlignment() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビットごとの組み合わせ`CBRS_ALIGN_`フラグ、または自動的に隠すペインが有効になっていない場合は 0 です。 詳細については、次を参照してください。 [CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking)します。  
  
### <a name="remarks"></a>コメント  
 メソッドは、自動非表示のコントロール バーの有効な配置を返します。 自動非表示バーを有効にする[CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes)します。  
  
##  <a name="getminiframes"></a>CDockingManager::GetMiniFrames  
 ミニフレームの一覧を取得します。  
  
```  
const CObList& GetMiniFrames() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドッキングのマネージャーに属するコントロール バーを含むミニフレームの一覧です。  
  
##  <a name="getouteredgebounds"></a>CDockingManager::GetOuterEdgeBounds  
 フレームの外側のエッジを含む四角形を取得します。  
  
```  
CRect GetOuterEdgeBounds() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フレームの外側のエッジを含む四角形。  
  
##  <a name="getpanelist"></a>CDockingManager::GetPaneList  
 ドッキングのマネージャーに属するペインの一覧を返します。 これには、すべての浮動ペインが含まれます。  
  
```  
void GetPaneList(
    CObList& lstBars,  
    BOOL bIncludeAutohide = FALSE,  
    CRuntimeClass* pRTCFilter = NULL,  
    BOOL bIncludeTabs = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `lstBars`  
 現在のドッキング マネージャーのすべてのペインが含まれています。  
  
 [入力] `bIncludeAutohide`  
 `TRUE`自動非表示モードではペインを含めるそれ以外の場合、`FALSE`です。  
  
 [入力] `pRTCFilter`  
 ない場合`NULL`リストが返されますが、指定したランタイム クラスのペインだけを含みます。  
  
 [入力] `bIncludeTabs`  
 `TRUE`タブを含めるそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ドッキングのマネージャーに任意のタブ付きペインがある場合、このメソッドはへのポインターを返します[CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)オブジェクトとする必要があります列挙タブ明示的にします。  
  
 使用`pRTCFilter`をウィンドウの特定のクラスを取得します。 たとえば、この値を適切に設定して、ツールバーのみを取得できます。  
  
##  <a name="getsmartdockingmanager"></a>CDockingManager::GetSmartDockingManager  
 スマート ドッキング マネージャーへのポインターを取得します。  
  
```  
CSmartDockingManager* GetSmartDockingManager();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、[スマート ドッキング マネージャー](http://msdn.microsoft.com/en-us/f537a1a6-fb9e-41d7-952f-0f25d5ee7534)します。  
  
##  <a name="getsmartdockingmanagerpermanent"></a>CDockingManager::GetSmartDockingManagerPermanent  
 スマート ドッキング マネージャーへのポインターを取得します。  
  
```  
CSmartDockingManager* GetSmartDockingManagerPermanent() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スマート ドッキング マネージャーへのポインター。  
  
##  <a name="getsmartdockingparams"></a>CDockingManager::GetSmartDockingParams  
 ドッキング マネージャーのスマート ドッキングのパラメーターを返します。  
  
```  
static CSmartDockingInfo& GetSmartDockingParams();
```  
  
### <a name="return-value"></a>戻り値  
 このクラスは、現在のドッキング マネージャーのスマート ドッキングのパラメーターが含まれています。 詳細については、次を参照してください。 [CSmartDockingInfo クラス](../../mfc/reference/csmartdockinginfo-class.md)します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hideautohidepanes"></a>CDockingManager::HideAutoHidePanes  
 自動非表示モードになっているウィンドウを非表示にします。  
  
```  
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,  
    BOOL bImmediately = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBarToExclude`  
 非表示から除外するバーへのポインター。  
  
 [入力] `bImmediately`  
 `TRUE`すぐに、ウィンドウを非表示にするには`FALSE`を自動的に隠す効果のあるウィンドウを非表示にします。  
  
##  <a name="insertdocksite"></a>CDockingManager::InsertDockSite  
 ドッキング ペインを作成し、コントロール バーのリストに挿入します。  
  
```  
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,  
    DWORD dwAlignToInsertAfter,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `info`  
 ドッキング ペインに関する配置情報を含む構造体。  
  
 [入力] `dwAlignToInsertAfter`  
 ドッキング ペインの配置です。  
  
 [出力] `ppDockBar`  
 ドッキング ペインへのポインターへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング ペインが正常に作成された場合`FALSE`それ以外の場合。  
  
##  <a name="insertpane"></a>CDockingManager::InsertPane  
 コントロール バーのリストには、コントロール パネルを挿入します。  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
 コントロール パネルへのポインター。  
  
 [入力] `pTarget`  
 ターゲット ウィンドウへのポインター。  
  
 [入力] `bAfter`  
 `TRUE`対象のペインの位置の後に、ウィンドウを挿入するには`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`コントロール パネルがコントロール バーのリストに正しく追加された場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コントロール パネルは既にコントロール バーのリストの場合、またはターゲット ウィンドウがコントロール バーのリストに存在しない場合に false を返します。  
  
##  <a name="isdocksitemenu"></a>CDockingManager::IsDockSiteMenu  
 すべてのペインのキャプションにポップアップ メニューが表示されるかどうかを指定します。  
  
```  
static BOOL IsDockSiteMenu();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング サイトのメニューがすべてのドッキング ペインのキャプションに表示されている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 呼び出して、ドッキング サイト メニューを有効にすることができます[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)します。  
  
##  <a name="isinadjustlayout"></a>CDockingManager::IsInAdjustLayout  
 すべてのウィンドウ レイアウトを調整するかどうかを判断します。  
  
```  
BOOL IsInAdjustLayout() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`すべてのウィンドウのレイアウトが調整されている場合`FALSE`それ以外の場合。  
  
##  <a name="isolecontainermode"></a>CDockingManager::IsOLEContainerMode  
 ドッキング マネージャーが OLE コンテナー モードになっているかどうかを指定します。  
  
```  
BOOL IsOLEContainerMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキングのマネージャーが OLE コンテナー モードである場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 OLE コンテナー モードですべてのドッキング ペインおよびアプリケーションのツールバーが表示されません。 設定する場合に、ペインはこのモードで非表示も[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)に`TRUE`します。  
  
##  <a name="ispointneardocksite"></a>CDockingManager::IsPointNearDockSite  
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
 どちらの端点が近いを指定します。 指定できる値は、`CBRS_ALIGN_LEFT`、`CBRS_ALIGN_RIGHT`、`CBRS_ALIGN_TOP`、および `CBRS_ALIGN_BOTTOM` です。  
  
 [出力] `bOuterEdge`  
 `TRUE`ドッキング サイトの外側の境界線の近くのポイントがある場合`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング サイトの近くのポイントがある場合それ以外の場合`FALSE`します。  
  
##  <a name="isprintpreviewvalid"></a>CDockingManager::IsPrintPreviewValid  
 印刷プレビュー モードが設定されているかどうかを判断します。  
  
```  
BOOL IsPrintPreviewValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`印刷プレビュー モードが設定されている場合`FALSE`それ以外の場合。  
  
##  <a name="loadstate"></a>CDockingManager::LoadState  
 レジストリからドッキング マネージャーの状態を読み込みます。  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 プロファイルの名前。  
  
 [入力] `uiID`  
 ドッキングのマネージャーの id です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキングのマネージャーの状態が正常に読み込まれている場合それ以外の場合`FALSE`します。  
  
##  <a name="lockupdate"></a>CDockingManager::LockUpdate  
 指定されたウィンドウをロックします。  
  
```  
void LockUpdate(BOOL bLock);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bLock`  
 `TRUE`場合は、ウィンドウはロックされています。`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 ウィンドウがロックされると、移動することはできませんし、再描画されることはできません。  
  
##  <a name="m_bhidedockingbarsincontainermode"></a>CDockingManager::m_bHideDockingBarsInContainerMode  
 OLE コンテナー モードのペインをドッキング マネージャーが非表示にするかどうかを指定します。  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;  
```  
  
### <a name="remarks"></a>コメント  
 この値に設定`FALSE`メイン フレームにドッキングされているすべてのペインを保持する場合と、アプリケーションが OLE コンテナー モードです。 この値は、既定では、`TRUE`です。  
  
##  <a name="m_dockmodeglobal"></a>CDockingManager::m_dockModeGlobal  
 グローバル ドッキング モードを指定します。  
  
```  
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;  
```  
  
### <a name="remarks"></a>コメント  
 既定では、各ドッキング ペインは、このドッキング モードを使用します。 このフィールドに設定できる値の詳細については、次を参照してください。 [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode)します。  
  
##  <a name="m_ndocksensitivity"></a>CDockingManager::m_nDockSensitivity  
 ドッキングの感度を指定します。  
  
```  
AFX_IMPORT_DATA static int m_nDockSensitivity;  
```  
  
### <a name="remarks"></a>コメント  
 ドッキングと小文字の区別を定義、どのくらい近づいての浮動ペインから、framework のドッキング状態を変更する前に、ドッキング ペイン、ドッキング サイト、または別のペインを得ることができます。  
  
##  <a name="m_ntimeoutbeforedockingbardock"></a>CDockingManager::m_nTimeOutBeforeDockingBarDock  
 イミディ エイト モードでドッキング ドッキング ペインをドッキングする前に、時間 (ミリ秒単位) を指定します。  
  
```  
static UINT m_nTimeOutBeforeDockingBarDock;  
```  
  
### <a name="remarks"></a>コメント  
 ペインをドッキングすると、前に、フレームワークは、一定の時間を待機します。 これは、ウィンドウが、ユーザーがドラッグしても中に誤っての場所にドッキングすることを防止できます。  
  
##  <a name="m_ntimeoutbeforetoolbardock"></a>CDockingManager::m_nTimeOutBeforeToolBarDock  
 ツールバーがメイン フレーム ウィンドウにドッキングされるまでは、時間 (ミリ秒単位) を指定します。  
  
```  
static UINT m_nTimeOutBeforeToolBarDock;  
```  
  
### <a name="remarks"></a>コメント  
 ツールバーをドッキングすると、前に、フレームワークは、一定の時間を待機します。 これは、ツールバーが誤ったにドッキングされる場所、ユーザーがドラッグしても中にすることを防止できます。  
  
##  <a name="onactivateframe"></a>CDockingManager::OnActivateFrame  
 フレーム ウィンドウはアクティブになり、または非アクティブ化するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnActivateFrame(BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bActivate`  
 場合`TRUE`、フレーム ウィンドウがアクティブになり、場合`FALSE`、フレーム ウィンドウが非アクティブ化します。  
  
##  <a name="onclosepopupmenu"></a>CDockingManager::OnClosePopupMenu  
 アクティブなポップアップ メニューが WM_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。  
  
```  
void OnClosePopupMenu();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、現在のメイン ウィンドウを閉じるしようとしているときに、WM_DESTROY メッセージを送信します。 通知を処理するには、このメソッドをオーバーライド`CMFCPopupMenu`フレーム ウィンドウに属しているオブジェクトと、`CMFCPopupMenu`プロセスのオブジェクト、`WM_DESTROY`メッセージです。  
  
##  <a name="onmoveminiframe"></a>CDockingManager::OnMoveMiniFrame  
 ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pFrame`  
 ミニフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
##  <a name="onpanecontextmenu"></a>CDockingManager::OnPaneContextMenu  
 ウィンドウのリストを持つメニューを作成するときに、フレームワークによって呼び出されます。  
  
```  
void OnPaneContextMenu(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 メニューの場所を指定します。  
  
##  <a name="panefrompoint"></a>CDockingManager::PaneFromPoint  
 指定したポイントを含むペインを返します。  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL,  
    BOOL bCheckVisibility = FALSE,  
    const CBasePane* pBarToIgnore = NULL) const;  
  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType = NULL,  
    const CBasePane* pBarToIgnore = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 確認の画面座標で、ポイントを指定します。  
  
 [入力] `nSensitivity`  
 チェックする各ペインのウィンドウの四角形の拡張値です。 ペインは、指定したポイントが高めのこの領域にある場合に、検索条件を満たします。  
  
 [入力] `bExactBar`  
 `TRUE`無視する、`nSensitivity`パラメーター。 そうしないと、`FALSE`です。  
  
 [入力] `pRTCBarType`  
 ない場合`NULL`、指定した型のペインだけが検索されます。  
  
 [入力] `bCheckVisibility`  
 `TRUE`表示ペインにのみをチェックするにはそれ以外の場合、`FALSE`です。  
  
 [出力] `dwAlignment`  
 指定したポイントに、ウィンドウが見つかった場合、このパラメーターが指定したポイントに最も近いペインの横にはが含まれています。 詳細については、「解説」を参照してください。  
  
 [入力] `pBarToIgnore`  
 ない場合`NULL`、このメソッドはこのパラメーターで指定されたウィンドウを無視します。  
  
### <a name="return-value"></a>戻り値  
 [CBasePane](../../mfc/reference/cbasepane-class.md)-指定したポイントを格納しているオブジェクトを派生または`NULL`ウィンドウが検出されなかった場合。  
  
### <a name="remarks"></a>コメント  
 この関数に戻り、ペインが見つかった`dwAlignment`指定した点の配置が含まれています。 たとえば、次の点が、ウィンドウの上部に最も近い`dwAlignment`に設定されている`CBRS_ALIGN_TOP`します。  
  
##  <a name="processpanecontextmenucommand"></a>CDockingManager::ProcessPaneContextMenuCommand  
 選択するか、指定されたコマンドのチェック ボックスをオフにして表示されるペインのレイアウトを再計算するため、フレームワークによって呼び出されます。  
  
```  
BOOL ProcessPaneContextMenuCommand(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 コントロール バー、メニュー内の id です。  
  
 [入力] `nCode`  
 コマンド通知コード。  
  
 [入力] `pExtra`  
 無効にすることへのポインターはへのポインターにキャストされる`CCmdUI`場合`nCode`は CN_UPDATE_COMMAND_UI です。  
  
 [入力] `pHandlerInfo`  
 情報の構造体へのポインター。 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合`pEXtra`が NULL でないと`nCode`CN_UPDATE_COMMAND_UI に等しい、指定したコントロール バーがある場合、または`nID`です。  
  
##  <a name="recalclayout"></a>CDockingManager::RecalcLayout  
 コントロールのリストに提示されるコントロールの内部のレイアウトを再計算します。  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bNotify`  
 このパラメーターは使用されません。  
  
##  <a name="releaseemptypanecontainers"></a>CDockingManager::ReleaseEmptyPaneContainers  
 空のペインのコンテナーを解放します。  
  
```  
void ReleaseEmptyPaneContainers();
```  
  
##  <a name="removehiddenmditabbedbar"></a>CDockingManager::RemoveHiddenMDITabbedBar  
 指定した非表示のウィンドウ バーを削除します。  
  
```  
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 バーへのポインターを削除するウィンドウです。  
  
##  <a name="removeminiframe"></a>CDockingManager::RemoveMiniFrame  
 ミニフレームの一覧から、指定したフレームを削除します。  
  
```  
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 削除するためのフレームへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`指定したフレームが削除された場合`FALSE`それ以外の場合。  
  
##  <a name="removepanefromdockmanager"></a>CDockingManager::RemovePaneFromDockManager  
 ペインの登録を解除し、ドッキング マネージャーの一覧から削除されます。  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pWnd,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 削除するペインへのポインター。  
  
 [入力] `bDestroy`  
 場合`TRUE`、削除されたウィンドウを破棄します。  
  
 [入力] `bAdjustLayout`  
 場合`TRUE`、すぐにドッキング レイアウトを調整します。  
  
 [入力] `bAutoHide`  
 場合`TRUE`、自動非表示バーの一覧から、ウィンドウを削除します。 場合`FALSE`ウィンドウは、標準のペインの一覧から削除されます。  
  
 [入力] `pBarReplacement`  
 削除されるペインに置き換えられるペインへのポインター。  
  
##  <a name="replacepane"></a>CDockingManager::ReplacePane  
 ペインを別のペインに置き換えます。  
  
```  
BOOL ReplacePane(
    CDockablePane* pOriginalBar,  
    CDockablePane* pNewBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pOriginalBar`  
 元のウィンドウへのポインター。  
  
 [入力] `pNewBar`  
 元のウィンドウに切り替わりますウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ウィンドウが正常に置換されます。`FALSE`それ以外の場合。  
  
##  <a name="resortminiframesforzorder"></a>CDockingManager::ResortMiniFramesForZOrder  
 ミニフレームの一覧内のフレームを使用します。  
  
```  
void ResortMiniFramesForZOrder();
```  
  
##  <a name="savestate"></a>CDockingManager::SaveState  
 ドッキング マネージャーの状態をレジストリに保存します。  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 レジストリ キーへのパス。  
  
 [入力] `uiID`  
 ドッキング マネージャー id。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`状態が正常に保存されている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 レジストリにドッキング マネージャーの状態の保存、コントロール バーの状態、自動非表示バーの状態およびミニフレーム ドッキング マネージャーの現在の状態を保存する必要があります。  
  
##  <a name="sendmessagetominiframes"></a>CDockingManager::SendMessageToMiniFrames  
 ミニのすべてのフレームを指定したメッセージを送信します。  
  
```  
BOOL SendMessageToMiniFrames(
    UINT uMessage,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uMessage`  
 送信するメッセージ。  
  
 [入力] `wParam`  
 追加のメッセージの依存情報。  
  
 [入力] `lParam`  
 追加のメッセージの依存情報。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`いつも。  
  
##  <a name="serialize"></a>CDockingManager::Serialize  
 ドッキングのマネージャーをアーカイブに書き込みます。  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ar`  
 アーカイブ オブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 アーカイブにドッキング マネージャーを作成するには、ドッキング コントロール バーとスライダーと、コントロール バー、ミニ フレーム、自動非表示バー、および MDI タブ付きバーをアーカイブに書き込みの数の決定があります。  
  
##  <a name="setautohidezorder"></a>CDockingManager::SetAutohideZOrder  
 サイズ、幅、およびコントロール バーと、指定したウィンドウの高さを設定します。  
  
```  
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pAHDockingBar`  
 ドッキング可能ペインへのポインター。  
  
##  <a name="setdockingmode"></a>CDockingManager::SetDockingMode  
 ドッキングのモードを設定します。  
  
```  
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,  
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```  
  
### <a name="parameters"></a>パラメーター  
 `dockMode`  
 新しいドッキング モードを指定します。 詳細については、「解説」を参照してください。  
  
 `theme`  
 スマート ドッキング マーカーに使用されるテーマを指定します。 次の列挙値のいずれか: AFX_SDT_DEFAULT AFX_SDT_VS2005、AFX_SDT_VS2008 です。  
  
### <a name="remarks"></a>コメント  
 この静的メソッドを呼び出してドッキング モードを設定します。  
  
 `dockMode`次の値のいずれかを指定できます。  
  
- `DT_STANDARD`標準 Visual Studio .NET 2003 で実装されているモードをドッキングします。 ウィンドウは、ドラッグのコンテキストを使用せずにドラッグします。  
  
- `DT_IMMEDIATE`即時のドッキング モードとしては、Microsoft Visio で実装されます。 ドラッグのコンテキストでウィンドウがドラッグされるが、マーカーは表示されません。  
  
- `DT_SMART`-Visual Studio 2005 に実装されるとは、ドッキング モードをスマートにします。 ドラッグのコンテキストでウィンドウがドラッグされ、スマート マーカーを表示するペインのドッキング位置を示します。  
  
##  <a name="setdockstate"></a>CDockingManager::SetDockState  
 コントロール バー、ミニ フレーム、および自動非表示バーのドッキング状態を設定します。  
  
```  
virtual void SetDockState();
```  
  
##  <a name="setprintpreviewmode"></a>CDockingManager::SetPrintPreviewMode  
 印刷プレビューで表示されるバーの印刷プレビュー モードを設定します。  
  
```  
void SetPrintPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bPreview`  
 `TRUE`印刷プレビュー モードが設定されている場合`FALSE`それ以外の場合。  
  
 [入力] `pState`  
 プレビュー状態へのポインター。 このパラメーターは使用されません。  
  
##  <a name="setsmartdockingparams"></a>CDockingManager::SetSmartDockingParams  
 スマート ドッキングの動作を定義するパラメーターを設定します。  
  
```  
static void SetSmartDockingParams(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `params`  
 スマート ドッキングのパラメーターを定義します。  
  
### <a name="remarks"></a>コメント  
 外観、色、またはスマート ドッキング マーカーの形状をカスタマイズする場合は、このメソッドを呼び出します。  
  
 スマート ドッキング マーカーに既定の表示形式を使用するには、初期化されていないインスタンスを渡す[CSmartDockingInfo クラス](../../mfc/reference/csmartdockinginfo-class.md)に`params`します。  
  
##  <a name="showdelayshowminiframes"></a>CDockingManager::ShowDelayShowMiniFrames  
 ミニフレーム ウィンドウの表示と非表示を切り替えます。  
  
```  
void ShowDelayShowMiniFrames(BOOL bshow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
 `TRUE`すると、表示されているフレームのウィンドウがアクティブです。`FALSE to`フレームのウィンドウを非表示にします。  
  
##  <a name="showpanes"></a>CDockingManager::ShowPanes  
 コントロールと自動的に隠す の横棒のペインの表示と非表示を切り替えます。  
  
```  
virtual BOOL ShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
 `TRUE`ウィンドウを表示するには`FALSE to`ペインを非表示にします。  
  
### <a name="return-value"></a>戻り値  
 常に `FALSE`。  
  
##  <a name="startsdocking"></a>CDockingManager::StartSDocking  
 スマート ドッキング マネージャーの配置に基づいて、指定したウィンドウのスマート ドッキングを開始します。  
  
```  
void StartSDocking(CWnd* pDockingWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockingWnd`  
 ドッキングするウィンドウへのポインター。  
  
##  <a name="stopsdocking"></a>CDockingManager::StopSDocking  
 スマート ドッキングを停止します。  
  
```  
void StopSDocking();
```  
  
##  <a name="getsmartdockingtheme"></a>CDockingManager::GetSmartDockingTheme  
 スマート ドッキング マーカーの表示に使用されるテーマを返す静的メソッドです。  
  
```  
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```  
  
### <a name="return-value"></a>戻り値  
 次の列挙値のいずれかを返します。 AFX_SDT_DEFAULT AFX_SDT_VS2005、AFX_SDT_VS2008 です。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)   
 [CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)

