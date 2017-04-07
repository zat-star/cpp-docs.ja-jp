---
title: "CPaneFrameWnd クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd::AddPane
- AFXPANEFRAMEWND/CPaneFrameWnd::AddRemovePaneFromGlobalList
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustPaneFrames
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcBorderSize
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcExpectedDockedRect
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeAttached
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeDockedToPane
- AFXPANEFRAMEWND/CPaneFrameWnd::CheckGripperVisibility
- AFXPANEFRAMEWND/CPaneFrameWnd::ConvertToTabbedDocument
- AFXPANEFRAMEWND/CPaneFrameWnd::Create
- AFXPANEFRAMEWND/CPaneFrameWnd::CreateEx
- AFXPANEFRAMEWND/CPaneFrameWnd::DockPane
- AFXPANEFRAMEWND/CPaneFrameWnd::FindFloatingPaneByID
- AFXPANEFRAMEWND/CPaneFrameWnd::FrameFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionHeight
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionText
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingMode
- AFXPANEFRAMEWND/CPaneFrameWnd::GetFirstVisiblePane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::GetParent
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPinState
- AFXPANEFRAMEWND/CPaneFrameWnd::GetRecentFloatingRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetVisiblePaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::HitTest
- AFXPANEFRAMEWND/CPaneFrameWnd::IsCaptured
- AFXPANEFRAMEWND/CPaneFrameWnd::IsDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollDown
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollUp
- AFXPANEFRAMEWND/CPaneFrameWnd::KillDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::LoadState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnBeforeDock
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDockToRecentPos
- AFXPANEFRAMEWND/CPaneFrameWnd::OnKillRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnMovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::OnPaneRecalcLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::OnSetRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnShowPane
- AFXPANEFRAMEWND/CPaneFrameWnd::PaneFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::Pin
- AFXPANEFRAMEWND/CPaneFrameWnd::RedrawAll
- AFXPANEFRAMEWND/CPaneFrameWnd::RemoveNonValidPanes
- AFXPANEFRAMEWND/CPaneFrameWnd::RemovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::ReplacePane
- AFXPANEFRAMEWND/CPaneFrameWnd::SaveState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetCaptionButtons
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::SetPreDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SizeToContent
- AFXPANEFRAMEWND/CPaneFrameWnd::StartTearOff
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentDockSiteInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentTabRelatedInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::OnCheckRollState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDrawBorder
- AFXPANEFRAMEWND/CPaneFrameWnd::m_bUseSaveBits
dev_langs:
- C++
helpviewer_keywords:
- CPaneFrameWnd class
- Serialize method
- PreTranslateMessage method
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
caps.latest.revision: 28
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
ms.openlocfilehash: a8609643a9e64127af1d8035c496cedab4b1b1e9
ms.lasthandoff: 02/24/2017

---
# <a name="cpaneframewnd-class"></a>CPaneFrameWnd クラス
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 1 つのペインを含むミニフレーム ウィンドウを実装します。 そのペインは、ウィンドウのクライアント領域になります。  
  
## <a name="syntax"></a>構文  
  
```  
class CPaneFrameWnd : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneFrameWnd::AddPane](#addpane)|ペインを追加します。|  
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](#addremovepanefromgloballist)|グローバル リストに対してペインを追加または削除します。|  
|[CPaneFrameWnd::AdjustLayout](#adjustlayout)|ミニフレーム ウィンドウのレイアウトを調整します。|  
|[CPaneFrameWnd::AdjustPaneFrames](#adjustpaneframes)||  
|[CPaneFrameWnd::CalcBorderSize](#calcbordersize)|ミニフレーム ウィンドウの境界線のサイズを計算します。|  
|[CPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|ドッキング ウィンドウの予想される四角形を計算します。|  
|[CPaneFrameWnd::CanBeAttached](#canbeattached)|現在のペインを別のペインまたはフレーム ウィンドウにドッキングできるかどうかを判定します。|  
|[CPaneFrameWnd::CanBeDockedToPane](#canbedockedtopane)|ミニフレーム ウィンドウをペインにドッキングできるかどうかを判定します。|  
|[CPaneFrameWnd::CheckGripperVisibility](#checkgrippervisibility)||  
|[CPaneFrameWnd::ConvertToTabbedDocument](#converttotabbeddocument)|ペインをタブ付きドキュメントに変換します。|  
|[CPaneFrameWnd::Create](#create)|ミニフレーム ウィンドウを作成し、`CPaneFrameWnd` オブジェクトにアタッチします。|  
|[CPaneFrameWnd::CreateEx](#createex)|ミニフレーム ウィンドウを作成し、`CPaneFrameWnd` オブジェクトにアタッチします。|  
|[CPaneFrameWnd::DockPane](#dockpane)|ペインをドッキングします。|  
|[CPaneFrameWnd::FindFloatingPaneByID](#findfloatingpanebyid)|フローティング ペインのグローバル リストで、指定したコントロール ID のペインを検索します。|  
|[CPaneFrameWnd::FrameFromPoint](#framefrompoint)|ユーザーが指定したポイントを含むミニフレーム ウィンドウを検索します。|  
|[CPaneFrameWnd::GetCaptionHeight](#getcaptionheight)|ミニフレーム ウィンドウのキャプションの高さを返します。|  
|[CPaneFrameWnd::GetCaptionRect](#getcaptionrect)|ミニフレーム ウィンドウのキャプションに外接する四角形を計算します。|  
|[CPaneFrameWnd::GetCaptionText](#getcaptiontext)|キャプション テキストを返します。|  
|[CPaneFrameWnd::GetDockingManager](#getdockingmanager)||  
|[CPaneFrameWnd::GetDockingMode](#getdockingmode)|ドッキングのモードを返します。|  
|[CPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|ミニフレーム ウィンドウに含まれる最初の可視ペインを返します。|  
|[CPaneFrameWnd::GetHotPoint](#gethotpoint)||  
|[CPaneFrameWnd::GetPane](#getpane)|ミニフレーム ウィンドウに含まれるペインを返します。|  
|[CPaneFrameWnd::GetPaneCount](#getpanecount)|ミニフレーム ウィンドウに含まれるペインの数を返します。|  
|[CPaneFrameWnd::GetParent](#getparent)||  
|[CPaneFrameWnd::GetPinState](#getpinstate)||  
|[CPaneFrameWnd::GetRecentFloatingRect](#getrecentfloatingrect)||  
|[CPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|ミニフレーム ウィンドウに含まれる可視ペインの数を返します。|  
|[CPaneFrameWnd::HitTest](#hittest)|特定のポイントに、ミニフレーム ウィンドウのどの部分があるか判定します。|  
|[CPaneFrameWnd::IsCaptured](#iscaptured)||  
|[CPaneFrameWnd::IsDelayShow](#isdelayshow)||  
|[CPaneFrameWnd::IsRollDown](#isrolldown)|ミニフレーム ウィンドウをロール ダウンするかどうかを判断します。|  
|[CPaneFrameWnd::IsRollUp](#isrollup)|ミニフレーム ウィンドウをロール アップするかどうかを判断します。|  
|[CPaneFrameWnd::KillDockingTimer](#killdockingtimer)|ドッキング タイマーを停止します。|  
|[CPaneFrameWnd::LoadState](#loadstate)|レジストリからペインの状態を読み込みます。|  
|[CPaneFrameWnd::OnBeforeDock](#onbeforedock)|ドッキングが可能かどうかを判定します。|  
|[CPaneFrameWnd::OnDockToRecentPos](#ondocktorecentpos)|ミニフレーム ウィンドウを直前の位置にドッキングします。|  
|[CPaneFrameWnd::OnKillRollUpTimer](#onkillrolluptimer)|ロールアップ タイマーを停止します。|  
|[CPaneFrameWnd::OnMovePane](#onmovepane)|ミニフレーム ウィンドウを指定したオフセットだけ移動します。|  
|[CPaneFrameWnd::OnPaneRecalcLayout](#onpanerecalclayout)|含まれているペインのレイアウトを調整します。|  
|[CPaneFrameWnd::OnSetRollUpTimer](#onsetrolluptimer)|ロールアップ タイマーを設定します。|  
|[CPaneFrameWnd::OnShowPane](#onshowpane)|ミニフレーム ウィンドウ内のペインが非表示になるとき、または表示されるときに、フレームワークによって呼び出されます。|  
|[CPaneFrameWnd::PaneFromPoint](#panefrompoint)|ユーザーが指定した位置がミニフレーム ウィンドウ内のペインに含まれている場合、そのペインを返します。|  
|[CPaneFrameWnd::Pin](#pin)||  
|`CPaneFrameWnd::PreTranslateMessage`|クラスで使用される[CWinApp](../../mfc/reference/cwinapp-class.md)にディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数です。|  
|[CPaneFrameWnd::RedrawAll](#redrawall)|すべてのミニフレーム ウィンドウを再描画します。|  
|[CPaneFrameWnd::RemoveNonValidPanes](#removenonvalidpanes)|有効でないウィンドウを削除するために、フレームワークによって呼び出されます。|  
|[CPaneFrameWnd::RemovePane](#removepane)|ミニフレーム ウィンドウから、ペインを削除します。|  
|[CPaneFrameWnd::ReplacePane](#replacepane)|ペインを別のペインに置き換えます。|  
|[CPaneFrameWnd::SaveState](#savestate)|レジストリにペインの状態を保存します。|  
|`CPaneFrameWnd::Serialize`|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。|  
|[CPaneFrameWnd::SetCaptionButtons](#setcaptionbuttons)|キャプションのボタンを設定します。|  
|[CPaneFrameWnd::SetDelayShow](#setdelayshow)||  
|[CPaneFrameWnd::SetDockingManager](#setdockingmanager)||  
|[CPaneFrameWnd::SetDockingTimer](#setdockingtimer)|ドッキング タイマーを設定します。|  
|[CPaneFrameWnd::SetDockState](#setdockstate)|ドッキング状態を設定します。|  
|[CPaneFrameWnd::SetHotPoint](#sethotpoint)||  
|[CPaneFrameWnd::SetPreDockState](#setpredockstate)|ドッキング前の状態を設定するために、フレームワークによって呼び出されます。|  
|[CPaneFrameWnd::SizeToContent](#sizetocontent)|含まれているペインとサイズを同じにするために、ミニフレーム ウィンドウのサイズを調整します。|  
|[CPaneFrameWnd::StartTearOff](#starttearoff)|メニューをティアオフします。|  
|[CPaneFrameWnd::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneFrameWnd::OnCheckRollState](#oncheckrollstate)|ミニフレーム ウィンドウをロール アップまたはロール ダウンするかどうかを判断します。|  
|[CPaneFrameWnd::OnDrawBorder](#ondrawborder)|ミニフレーム ウィンドウの境界線を描画します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|`CS_SAVEBITS` クラス スタイルにウィンドウ クラスを登録するかどうかを指定します。|  
  
## <a name="remarks"></a>コメント  
 ペインがドッキング状態からフローティング状態に切り替わるときに、フレームワークは自動的に `CPaneFrameWnd` オブジェクトを作成します。  
  
 ミニフレーム ウィンドウは内容を表示した状態でドラッグ (直接ドッキング) するか、ドラッグ四角形を使用してドラッグ (標準ドッキング) することができます。 ミニフレームのコンテナー ペインのドッキング モードにより、ミニフレームのドラッグ動作が決まります。 詳細については、次を参照してください。 [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode)します。  
  
 ミニフレーム ウィンドウには、含まれているペインのスタイルに従って、キャプションのボタンが表示されます。 ウィンドウを閉じることができる場合 ( [CBasePane::CanBeClosed](../../mfc/reference/cbasepane-class.md#canbeclosed))、[閉じる] ボタンが表示されます。 ペインのスタイルが `AFX_CBRS_AUTO_ROLLUP` である場合は、ピンが表示されます。  
  
 `CPaneFrameWnd` からクラスを派生させる場合は、フレームワークで作成方法を定義する必要があります。 オーバーライドすることで、クラスを作成するか[CPane::CreateDefaultMiniframe](../../mfc/reference/cpane-class.md#createdefaultminiframe)、設定、または、`CPane::m_pMiniFrameRTC`メンバーことが、クラスのランタイム クラス情報を指すようにします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPaneFrameWnd`   
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxPaneFrameWnd.h  
  
##  <a name="addpane"></a>CPaneFrameWnd::AddPane  
 ペインを追加します。  
  
```  
virtual void AddPane(CBasePane* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 追加のウィンドウ。  
  
##  <a name="addremovepanefromgloballist"></a>CPaneFrameWnd::AddRemovePaneFromGlobalList  
 グローバル リストに対してペインを追加または削除します。  
  
```  
static BOOL __stdcall AddRemovePaneFromGlobalList(
    CBasePane* pWnd,  
    BOOL bAdd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 追加または削除するウィンドウ。  
  
 [入力] `bAdd`  
 0 以外の場合、ウィンドウを追加します。 0 の場合は、ウィンドウを削除します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="adjustlayout"></a>CPaneFrameWnd::AdjustLayout  
 ミニフレーム ウィンドウのレイアウトを調整します。  
  
```  
virtual void AdjustLayout();
```  
  
##  <a name="adjustpaneframes"></a>CPaneFrameWnd::AdjustPaneFrames  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="calcbordersize"></a>CPaneFrameWnd::CalcBorderSize  
 ミニフレーム ウィンドウの境界線のサイズを計算します。  
  
```  
virtual void CalcBorderSize(CRect& rectBorderSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rectBorderSize`  
 ミニフレーム ウィンドウの枠線のピクセル単位のサイズが含まれています。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ミニフレーム ウィンドウの枠線のサイズを計算するためにフレームワークによって呼び出されます。 返されるサイズによって異なりますミニフレーム ウィンドウのツールバーにあるかどうか、または、 [CDockablePane](../../mfc/reference/cdockablepane-class.md)します。  
  
##  <a name="calcexpecteddockedrect"></a>CPaneFrameWnd::CalcExpectedDockedRect  
 ドッキング ウィンドウの予想される四角形を計算します。  
  
```  
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndToDock`  
 ドッキングするウィンドウへのポインター。  
  
 [入力] `ptMouse`  
 マウスの位置。  
  
 [出力] `rectResult`  
 計算される四角形。  
  
 [出力] `bDrawTab`  
 場合`TRUE`タブを描画します。 場合`FALSE`タブを描画しません。  
  
 [出力] `ppTargetBar`  
 ターゲット ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ウィンドウがユーザーによって指定された地点をウィンドウをドラッグする場合に使用する四角形を計算`ptMouse`し、そこにドッキングします。  
  
##  <a name="canbeattached"></a>CPaneFrameWnd::CanBeAttached  
 現在のペインを別のペインまたはフレーム ウィンドウにドッキングできるかどうかを判定します。  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`別のウィンドウまたはフレーム ウィンドウに、ウィンドウをドッキングできる場合それ以外の場合`FALSE`します。  
  
##  <a name="canbedockedtopane"></a>CPaneFrameWnd::CanBeDockedToPane  
 ミニフレーム ウィンドウをペインにドッキングできるかどうかを判定します。  
  
```  
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockingBar`  
 ウィンドウ。  
  
### <a name="return-value"></a>戻り値  
 ミニ フレームをドッキングする場合は 0 以外`pDockingBar`。 それ以外の場合に 0 です。  
  
##  <a name="checkgrippervisibility"></a>CPaneFrameWnd::CheckGripperVisibility  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CheckGripperVisibility();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="converttotabbeddocument"></a>CPaneFrameWnd::ConvertToTabbedDocument  
 ペインをタブ付きドキュメントに変換します。  
  
```  
virtual void ConvertToTabbedDocument();
```  
  
##  <a name="create"></a>CPaneFrameWnd::Create  
 ミニフレーム ウィンドウを作成し、それにアタッチ、 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)オブジェクトです。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszWindowName`  
 ミニフレーム ウィンドウに表示されるテキストを指定します。  
  
 [入力] `dwStyle`  
 ウィンドウ スタイルを指定します。 詳細については、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/window-styles.md)します。  
  
 [入力] `rect`  
 初期サイズとミニフレーム ウィンドウの位置を指定します。  
  
 [in][out]`pParentWnd`  
 ミニフレーム ウィンドウの親フレームを指定します。 この値である必要があります`NULL`します。  
  
 [in][out]`pContext`  
 ユーザー定義のコンテキストを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウを正常に作成した場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ミニフレーム ウィンドウは、2 つの手順で作成されます。 最初に、フレームワークを作成、`CPaneFrameWnd`オブジェクトです。 次から`Create`Windows ミニフレーム ウィンドウを作成し、添付、`CPaneFrameWnd`オブジェクトです。  
  
##  <a name="createex"></a>CPaneFrameWnd::CreateEx  
 ミニフレーム ウィンドウを作成し、それにアタッチ、 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwStyleEx`  
 拡張ウィンドウ スタイルを指定します。 詳細については、次を参照してください[拡張ウィンドウ スタイル。](../../mfc/reference/extended-window-styles.md)  
  
 [入力] `lpszWindowName`  
 ミニフレーム ウィンドウに表示されるテキストを指定します。  
  
 [入力] `dwStyle`  
 ウィンドウ スタイルを指定します。 詳細については、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/window-styles.md)します。  
  
 [入力] `rect`  
 初期サイズとミニフレーム ウィンドウの位置を指定します。  
  
 [in][out]`pParentWnd`  
 ミニフレーム ウィンドウの親フレームを指定します。 この値である必要があります`NULL`します。  
  
 [in][out]`pContext`  
 ユーザー定義のコンテキストを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウを正常に作成した場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ミニフレーム ウィンドウは、2 つの手順で作成されます。 最初に、フレームワークを作成、`CPaneFrameWnd`オブジェクトです。 次から`Create`Windows ミニフレーム ウィンドウを作成し、添付、`CPaneFrameWnd`オブジェクトです。  
  
##  <a name="dockpane"></a>CPaneFrameWnd::DockPane  
 ペインをドッキングします。  
  
```  
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `bWasDocked`  
 `TRUE`ウィンドウが既にドッキングされている場合それ以外の場合`FALSE`します。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合、`CDockablePane`以外の場合、ウィンドウがドッキングされている`NULL`します。  
  
##  <a name="findfloatingpanebyid"></a>CPaneFrameWnd::FindFloatingPaneByID  
 フローティング ペインのグローバル リストで、指定したコントロール ID のペインを検索します。  
  
```  
static CBasePane* FindFloatingPaneByID(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 検索するウィンドウのコントロール ID を表します。  
  
### <a name="return-value"></a>戻り値  
 指定したコントロールの ID を持つペインそれ以外の場合、`NULL`ウィンドウには、指定したコントロールの ID があるない場合は、  
  
##  <a name="framefrompoint"></a>CPaneFrameWnd::FrameFromPoint  
 指定したポイントを含むミニフレーム ウィンドウを検索します。  
  
```  
static CPaneFrameWnd* __stdcall FrameFromPoint(
    CPoint pt,  
    int nSensitivity,  
    CPaneFrameWnd* pFrameToExclude = NULL,  
    BOOL bFloatMultiOnly = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pt`  
 画面座標でのポイント。  
  
 [入力] `nSensitivity`  
 このサイズにミニフレーム ウィンドウの検索領域を増やします。 ミニフレーム ウィンドウは、指定したポイントが拡大された領域で該当する場合に、検索条件を満たします。  
  
 [入力] `pFrameToExclude`  
 検索対象から除外するミニフレーム ウィンドウを指定します。  
  
 [入力] `bFloatMultiOnly`  
 場合`TRUE`、のみを持つミニフレーム ウィンドウを検索、`CBRS_FLOAT_MULTI`スタイル。 場合`FALSE`、すべてのミニフレーム ウィンドウを検索します。  
  
### <a name="return-value"></a>戻り値  
 含むミニフレーム ウィンドウへのポインター `pt`。 そうしないと`NULL`です。  
  
##  <a name="getcaptionheight"></a>CPaneFrameWnd::GetCaptionHeight  
 ミニフレーム ウィンドウのキャプションの高さを返します。  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ミニフレーム ウィンドウのピクセル単位の高さ。  
  
### <a name="remarks"></a>コメント  
 ミニフレーム ウィンドウの高さを決定するには、このメソッドを呼び出します。 既定では、高さに設定`SM_CYSMCAPTION`します。 詳細については、次を参照してください。 [GetSystemMetrics 関数](http://msdn.microsoft.com/library/windows/desktop/ms724385)します。  
  
##  <a name="getcaptionrect"></a>CPaneFrameWnd::GetCaptionRect  
 ミニフレーム ウィンドウのキャプションに外接する四角形を計算します。  
  
```  
virtual void GetCaptionRect(CRect& rectCaption) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rectCaption`  
 サイズと画面座標でミニフレーム ウィンドウのキャプションの位置が含まれています。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ミニフレーム ウィンドウのキャプションの外接する四角形を計算するためにフレームワークによって呼び出されます。  
  
##  <a name="getcaptiontext"></a>CPaneFrameWnd::GetCaptionText  
 キャプション テキストを返します。  
  
```  
virtual CString GetCaptionText();
```  
  
### <a name="return-value"></a>戻り値  
 ミニフレーム ウィンドウのキャプションのテキスト。  
  
### <a name="remarks"></a>コメント  
 キャプション テキストを表示するとき、このメソッドは、フレームワークによって呼び出されます。  
  
##  <a name="getdockingmanager"></a>CPaneFrameWnd::GetDockingManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CDockingManager* GetDockingManager() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdockingmode"></a>CPaneFrameWnd::GetDockingMode  
 ドッキングのモードを返します。  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドッキング モードです。 次のいずれかの値です。  
  
- `DT_STANDARD`  
  
- `DT_IMMEDIATE`  
  
- `DT_SMART`  
  
##  <a name="getfirstvisiblepane"></a>CPaneFrameWnd::GetFirstVisiblePane  
 ミニフレーム ウィンドウに含まれる最初の可視ペインを返します。  
  
```  
virtual CWnd* GetFirstVisiblePane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ミニフレーム ウィンドウの最初のペインまたは`NULL`ミニフレーム ウィンドウにウィンドウが含まれていない場合。  
  
##  <a name="gethotpoint"></a>CPaneFrameWnd::GetHotPoint  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CPoint GetHotPoint() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpane"></a>CPaneFrameWnd::GetPane  
 ミニフレーム ウィンドウに含まれるペインを返します。  
  
```  
virtual CWnd* GetPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ミニ フレームに含まれているウィンドウまたは`NULL`ミニフレーム ウィンドウにウィンドウが含まれていない場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpanecount"></a>CPaneFrameWnd::GetPaneCount  
 ミニフレーム ウィンドウに含まれるペインの数を返します。  
  
```  
virtual int GetPaneCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ミニフレーム ウィンドウのペインの数。 この値は、0 にすることができます。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getparent"></a>CPaneFrameWnd::GetParent  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CWnd* GetParent();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpinstate"></a>CPaneFrameWnd::GetPinState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL GetPinState() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrecentfloatingrect"></a>CPaneFrameWnd::GetRecentFloatingRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetRecentFloatingRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getvisiblepanecount"></a>CPaneFrameWnd::GetVisiblePaneCount  
 ミニフレーム ウィンドウに含まれる可視ペインの数を返します。  
  
```  
virtual int GetVisiblePaneCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 表示ペインの数。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hittest"></a>CPaneFrameWnd::HitTest  
 特定のポイントに、ミニフレーム ウィンドウのどの部分があるか判定します。  
  
```  
virtual LRESULT HitTest(
    CPoint point,  
    BOOL bDetectCaption);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 テストする点です。  
  
 [入力] `bDetectCaption`  
 場合`TRUE`、キャプションに対して点を確認します。 場合`FALSE`キャプションを無視します。  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの値です。  
  
|値|説明|  
|-----------|-------------|  
|`HTNOWHERE`|点は、ミニフレーム ウィンドウの外側です。|  
|`HTCLIENT`|クライアント領域は、ポイントです。|  
|`HTCAPTION`|キャプションです。|  
|`HTTOP`|ポイントは、上部にあります。|  
|`HTTOPLEFT`|ポイントは、左上にあります。|  
|`HTTOPRIGHT`|ポイントは、右上にあります。|  
|`HTLEFT`|ポイントは、左側にあります。|  
|`HTRIGHT`|ポイントは、右側にあります。|  
|`HTBOTTOM`|ポイントは、下部にあります。|  
|`HTBOTTOMLEFT`|ポイントは、左下です。|  
|`HTBOTTOMRIGHT`|ポイントは、右下にあります。|  
  
##  <a name="iscaptured"></a>CPaneFrameWnd::IsCaptured  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsCaptured() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isdelayshow"></a>CPaneFrameWnd::IsDelayShow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsDelayShow() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isrolldown"></a>CPaneFrameWnd::IsRollDown  
 ミニフレーム ウィンドウをロール ダウンするかどうかを判断します。  
  
```  
virtual BOOL IsRollDown() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`下ミニフレーム ウィンドウをロールバックする必要がある場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ミニフレーム ウィンドウをロール ダウンするかどうかを判断するためにフレームワークによって呼び出されます。 持つ少なくとも&1; つのペインが含まれている場合は、ミニフレーム ウィンドウの プログラムのロールアップ/ロールダウン機能が有効な`AFX_CBRS_AUTO_ROLLUP`フラグ。 ペインの作成時に、このフラグが設定されます。 詳細については、次を参照してください。 [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)します。  
  
 既定では、フレームワークは、マウス ポインターがウィンドウにロール ダウンする必要があるかどうかを判断するミニフレーム ウィンドウ外接する四角形の内部があるかどうかを確認します。 派生クラスでこの動作をオーバーライドすることができます。  
  
##  <a name="isrollup"></a>CPaneFrameWnd::IsRollUp  
 ミニフレーム ウィンドウをロール アップするかどうかを判断します。  
  
```  
virtual BOOL IsRollUp() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ミニフレーム ウィンドウをロール アップする必要があります。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ミニフレーム ウィンドウをロール アップするかどうかを判断するためにフレームワークによって呼び出されます。 持つ少なくとも&1; つのペインが含まれている場合は、ミニフレーム ウィンドウの プログラムのロールアップ/ロールダウン機能が有効な`AFX_CBRS_AUTO_ROLLUP`フラグ。 ペインの作成時に、このフラグが設定されます。 詳細については、次を参照してください。 [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)します。  
  
 既定では、フレームワークは、マウス ポインターをウィンドウにロール アップする必要があるかどうかを判断するミニフレーム ウィンドウ外接する四角形があるかどうかを確認します。 派生クラスでこの動作をオーバーライドすることができます。  
  
##  <a name="killdockingtimer"></a>CPaneFrameWnd::KillDockingTimer  
 ドッキング タイマーを停止します。  
  
```  
void KillDockingTimer();
```  
  
##  <a name="loadstate"></a>CPaneFrameWnd::LoadState  
 レジストリからペインの状態を読み込みます。  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 プロファイル名。  
  
 [入力] `uiID`  
 ペインの ID  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインの状態が正常に読み込まれている場合それ以外の場合`FALSE`します。  
  
##  <a name="m_busesavebits"></a>CPaneFrameWnd::m_bUseSaveBits  
 持つウィンドウ クラスを登録するかどうかを示す、`CS_SAVEBITS`クラスのスタイル。  
  
```  
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;  
```  
  
### <a name="remarks"></a>コメント  
 この静的メンバーを設定`TRUE`を持つミニフレーム ウィンドウ クラスを登録する、`CS_SAVEBITS`スタイル。 これにより、ミニフレーム ウィンドウをドラッグすると、ちらつきを減らすことができます。  
  
##  <a name="onbeforedock"></a>CPaneFrameWnd::OnBeforeDock  
 ドッキングが可能かどうかを判定します。  
  
```  
virtual BOOL OnBeforeDock();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング可能な場合それ以外の場合、`FALSE`です。  
  
##  <a name="oncheckrollstate"></a>CPaneFrameWnd::OnCheckRollState  
 ミニフレーム ウィンドウをロール アップまたはロール ダウンするかどうかを判断します。  
  
```  
virtual void OnCheckRollState();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、上または下に、ミニフレーム ウィンドウをロールバックするかどうかを判断するためにフレームワークによって呼び出されます。  
  
 既定では、フレームワーク[CPaneFrameWnd::IsRollUp](#isrollup)と[CPaneFrameWnd::IsRollDown](#isrolldown)とだけ拡大またはミニフレーム ウィンドウを復元します。 別の視覚効果を使用する派生クラスでこのメソッドをオーバーライドすることができます。  
  
##  <a name="ondocktorecentpos"></a>CPaneFrameWnd::OnDockToRecentPos  
 ミニフレーム ウィンドウを直前の位置にドッキングします。  
  
```  
virtual void OnDockToRecentPos();
```  
  
##  <a name="ondrawborder"></a>CPaneFrameWnd::OnDrawBorder  
 ミニフレーム ウィンドウの境界線を描画します。  
  
```  
virtual void OnDrawBorder(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 境界線の描画に使用されるデバイス コンテキスト。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ミニフレーム ウィンドウの枠線を描画するためにフレームワークによって呼び出されます。  
  
##  <a name="onkillrolluptimer"></a>CPaneFrameWnd::OnKillRollUpTimer  
 ロールアップ タイマーを停止します。  
  
```  
virtual void OnKillRollUpTimer();
```  
  
##  <a name="onmovepane"></a>CPaneFrameWnd::OnMovePane  
 ミニフレーム ウィンドウを指定したオフセットだけ移動します。  
  
```  
virtual void OnMovePane(
    CPane* pBar,  
    CPoint ptOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 (無視されます) ウィンドウへのポインター。  
  
 [入力] `ptOffset`  
 ウィンドウを移動する位置のオフセット。  
  
##  <a name="onpanerecalclayout"></a>CPaneFrameWnd::OnPaneRecalcLayout  
 ミニフレーム ウィンドウ内のペインのレイアウトを調整します。  
  
```  
virtual void OnPaneRecalcLayout();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ミニフレーム ウィンドウ内のペインのレイアウトを調整する必要があるときに、このメソッドを呼び出します。  
  
 既定では、ミニフレーム ウィンドウの完全なクライアント領域をカバーする、ウィンドウが配置されます。  
  
##  <a name="onsetrolluptimer"></a>CPaneFrameWnd::OnSetRollUpTimer  
 ロールアップ タイマーを設定します。  
  
```  
virtual void OnSetRollUpTimer();
```  
  
##  <a name="onshowpane"></a>CPaneFrameWnd::OnShowPane  
 ミニフレーム ウィンドウ内のペインが非表示になるとき、または表示されるときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 化されるウィンドウが表示または非表示にします。  
  
 [入力] `bShow`  
 `TRUE`ウィンドウが表示されている場合`FALSE`場合は、ウィンドウが非表示にします。  
  
### <a name="remarks"></a>コメント  
 ミニフレーム ウィンドウのペインを表示または非表示のときに、フレームワークによって呼び出されます。 既定の実装では、何も行われません。  
  
##  <a name="pin"></a>CPaneFrameWnd::Pin  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Pin(BOOL bPin = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bPin`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="panefrompoint"></a>CPaneFrameWnd::PaneFromPoint  
 ユーザーが指定した位置がミニフレーム ウィンドウ内のペインに含まれている場合、そのペインを返します。  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    BOOL bCheckVisibility);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 ポイント画面座標でのユーザーがクリックしました。  
  
 [入力] `nSensitivity`  
 このパラメーターは使用されません。  
  
 [入力] `bCheckVisibility`  
 `TRUE`表示されているペインのみ返すことができます。それ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 ユーザーがクリックすると、ウィンドウまたは`NULL`その場所でウィンドウが存在しない場合。  
  
### <a name="remarks"></a>コメント  
 指定したポイントを含むペインを取得するには、このメソッドを呼び出します。  
  
##  <a name="redrawall"></a>CPaneFrameWnd::RedrawAll  
 すべてのミニフレーム ウィンドウを再描画します。  
  
```  
static void RedrawAll();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出してすべてミニフレーム ウィンドウを更新する[CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow)ウィンドウごとにします。  
  
##  <a name="removenonvalidpanes"></a>CPaneFrameWnd::RemoveNonValidPanes  
 有効でないウィンドウを削除するために、フレームワークによって呼び出されます。  
  
```  
virtual void RemoveNonValidPanes();
```  
  
##  <a name="removepane"></a>CPaneFrameWnd::RemovePane  
 ミニフレーム ウィンドウから、ペインを削除します。  
  
```  
virtual void RemovePane(
    CBasePane* pWnd,  
    BOOL bDestroy = FALSE,  
    BOOL bNoDelayedDestroy = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 削除するのには、ウィンドウへのポインター。  
  
 [入力] `bDestroy`  
 ミニフレーム ウィンドウへの動作を指定します。 場合`bDestroy`は`TRUE`、このメソッドはすぐにミニフレーム ウィンドウを破棄します。 ある場合`FALSE`、このメソッドは、特定の時間が経過したらミニフレーム ウィンドウを破棄します。  
  
 [入力] `bNoDelayedDestroy`  
 場合`TRUE`遅延、破棄が無効になっています。 場合`FALSE`遅延、破棄が有効にします。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、すぐに、または特定の時間が経過したら、ミニフレーム ウィンドウを破棄できます。 ミニフレーム ウィンドウの破棄を遅延する場合は、渡す`FALSE`で、`bNoDelayedDestroy`パラメーター。 フレームワークを処理するとき、遅延の破壊が発生する、`AFX_WM_CHECKEMPTYMINIFRAME`メッセージです。  
  
##  <a name="replacepane"></a>CPaneFrameWnd::ReplacePane  
 ペインを別のペインに置き換えます。  
  
```  
virtual void ReplacePane(
    CBasePane* pBarOrg,  
    CBasePane* pBarReplaceWith);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBarOrg`  
 元のウィンドウへのポインター。  
  
 [入力] `pBarReplaceWith`  
 元のウィンドウに切り替わりますウィンドウへのポインター。  
  
##  <a name="savestate"></a>CPaneFrameWnd::SaveState  
 レジストリにペインの状態を保存します。  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 プロファイル名。  
  
 [入力] `uiID`  
 ペインの ID  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインの状態が正常に保存されている場合それ以外の場合`FALSE`します。  
  
##  <a name="setcaptionbuttons"></a>CPaneFrameWnd::SetCaptionButtons  
 キャプションのボタンを設定します。  
  
```  
virtual void SetCaptionButtons(DWORD dwButtons);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwButtons`  
 次の値のビットごとの OR の組み合わせ。  
  
- `AFX_CAPTION_BTN_CLOSE`  
  
- `AFX_CAPTION_BTN_PIN`  
  
- `AFX_CAPTION_BTN_MENU`  
  
- `AFX_CAPTION_BTN_CUSTOMIZE`  
  
##  <a name="setdelayshow"></a>CPaneFrameWnd::SetDelayShow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetDelayShow(BOOL bDelayShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDelayShow`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setdockingmanager"></a>CPaneFrameWnd::SetDockingManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetDockingManager(CDockingManager* pManager);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pManager`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setdockingtimer"></a>CPaneFrameWnd::SetDockingTimer  
 ドッキング タイマーを設定します。  
  
```  
void SetDockingTimer(UINT nTimeOut);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nTimeOut`  
 タイムアウト値 (ミリ秒単位)。  
  
##  <a name="setdockstate"></a>CPaneFrameWnd::SetDockState  
 ドッキング状態を設定します。  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockManager`  
 ドッキング マネージャーへのポインター。  
  
##  <a name="sethotpoint"></a>CPaneFrameWnd::SetHotPoint  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetHotPoint(CPoint& ptNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ptNew`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpredockstate"></a>CPaneFrameWnd::SetPreDockState  
 ドッキング前の状態を設定するために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,  
    CBasePane* pBarToDock = NULL,  
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `preDockState`  
 次の値を使用できます。  
  
- `PDS_NOTHING`、  
  
- `PDS_DOCK_REGULAR`、  
  
- `PDS_DOCK_TO_TAB`  
  
 [入力] `pBarToDock`  
 ドッキングするのには、ウィンドウへのポインター。  
  
 [入力] `dockMethod`  
 ドッキング方法。 (このパラメーターが無視されます)  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ミニフレーム ウィンドウがドッキング解除する場合`FALSE`がドッキングされている場合。  
  
##  <a name="sizetocontent"></a>CPaneFrameWnd::SizeToContent  
 含まれているウィンドウと同じであるように、ミニフレーム ウィンドウのサイズを調整します。  
  
```  
virtual void SizeToContent();
```  
  
### <a name="remarks"></a>コメント  
 含まれているウィンドウのサイズをミニフレーム ウィンドウのサイズを調整するには、このメソッドを呼び出します。  
  
##  <a name="starttearoff"></a>CPaneFrameWnd::StartTearOff  
 メニューをティアオフします。  
  
```  
BOOL StartTearOff(CMFCPopu* pMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenu`  
 メニューへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが正常に実行された場合は `TRUE`、それ以外の場合は `FALSE`。  
  
##  <a name="storerecentdocksiteinfo"></a>CPaneFrameWnd::StoreRecentDockSiteInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="storerecenttabrelatedinfo"></a>CPaneFrameWnd::StoreRecentTabRelatedInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,  
    CDockablePane* pTabbedBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockingBar`  
 [入力] `pTabbedBar`  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)

