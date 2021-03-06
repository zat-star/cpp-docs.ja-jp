---
title: CDockSite クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CDockSite
- AFXDOCKSITE/CDockSite
- AFXDOCKSITE/CDockSite::AddRow
- AFXDOCKSITE/CDockSite::AdjustDockingLayout
- AFXDOCKSITE/CDockSite::AdjustLayout
- AFXDOCKSITE/CDockSite::AlignDockSite
- AFXDOCKSITE/CDockSite::CalcFixedLayout
- AFXDOCKSITE/CDockSite::CanAcceptPane
- AFXDOCKSITE/CDockSite::CreateEx
- AFXDOCKSITE/CDockSite::CreateRow
- AFXDOCKSITE/CDockSite::DockPane
- AFXDOCKSITE/CDockSite::DoesAllowDynInsertBefore
- AFXDOCKSITE/CDockSite::FindRowIndex
- AFXDOCKSITE/CDockSite::FixupVirtualRects
- AFXDOCKSITE/CDockSite::GetDockSiteID
- AFXDOCKSITE/CDockSite::GetDockSiteRowsList
- AFXDOCKSITE/CDockSite::IsAccessibilityCompatible
- AFXDOCKSITE/CDockSite::IsDragMode
- AFXDOCKSITE/CDockSite::IsLastRow
- AFXDOCKSITE/CDockSite::IsRectWithinDockSite
- AFXDOCKSITE/CDockSite::IsResizable
- AFXDOCKSITE/CDockSite::MovePane
- AFXDOCKSITE/CDockSite::OnInsertRow
- AFXDOCKSITE/CDockSite::OnRemoveRow
- AFXDOCKSITE/CDockSite::OnResizeRow
- AFXDOCKSITE/CDockSite::OnSetWindowPos
- AFXDOCKSITE/CDockSite::OnShowRow
- AFXDOCKSITE/CDockSite::OnSizeParent
- AFXDOCKSITE/CDockSite::PaneFromPoint
- AFXDOCKSITE/CDockSite::DockPaneLeftOf
- AFXDOCKSITE/CDockSite::FindPaneByID
- AFXDOCKSITE/CDockSite::GetPaneList
- AFXDOCKSITE/CDockSite::RectSideFromPoint
- AFXDOCKSITE/CDockSite::RemovePane
- AFXDOCKSITE/CDockSite::RemoveRow
- AFXDOCKSITE/CDockSite::ReplacePane
- AFXDOCKSITE/CDockSite::RepositionPanes
- AFXDOCKSITE/CDockSite::ResizeDockSite
- AFXDOCKSITE/CDockSite::ResizeRow
- AFXDOCKSITE/CDockSite::ShowPane
- AFXDOCKSITE/CDockSite::ShowRow
- AFXDOCKSITE/CDockSite::SwapRows
dev_langs:
- C++
helpviewer_keywords:
- CDockSite [MFC], AddRow
- CDockSite [MFC], AdjustDockingLayout
- CDockSite [MFC], AdjustLayout
- CDockSite [MFC], AlignDockSite
- CDockSite [MFC], CalcFixedLayout
- CDockSite [MFC], CanAcceptPane
- CDockSite [MFC], CreateEx
- CDockSite [MFC], CreateRow
- CDockSite [MFC], DockPane
- CDockSite [MFC], DoesAllowDynInsertBefore
- CDockSite [MFC], FindRowIndex
- CDockSite [MFC], FixupVirtualRects
- CDockSite [MFC], GetDockSiteID
- CDockSite [MFC], GetDockSiteRowsList
- CDockSite [MFC], IsAccessibilityCompatible
- CDockSite [MFC], IsDragMode
- CDockSite [MFC], IsLastRow
- CDockSite [MFC], IsRectWithinDockSite
- CDockSite [MFC], IsResizable
- CDockSite [MFC], MovePane
- CDockSite [MFC], OnInsertRow
- CDockSite [MFC], OnRemoveRow
- CDockSite [MFC], OnResizeRow
- CDockSite [MFC], OnSetWindowPos
- CDockSite [MFC], OnShowRow
- CDockSite [MFC], OnSizeParent
- CDockSite [MFC], PaneFromPoint
- CDockSite [MFC], DockPaneLeftOf
- CDockSite [MFC], FindPaneByID
- CDockSite [MFC], GetPaneList
- CDockSite [MFC], RectSideFromPoint
- CDockSite [MFC], RemovePane
- CDockSite [MFC], RemoveRow
- CDockSite [MFC], ReplacePane
- CDockSite [MFC], RepositionPanes
- CDockSite [MFC], ResizeDockSite
- CDockSite [MFC], ResizeRow
- CDockSite [MFC], ShowPane
- CDockSite [MFC], ShowRow
- CDockSite [MFC], SwapRows
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
caps.latest.revision: 28
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e2492738914062be692c1ddd02fd04bc461cd6b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdocksite-class"></a>CDockSite Class
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 [CPane Class](../../mfc/reference/cpane-class.md) から派生したペインを一連の行に配置する機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDockSite: public CBasePane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDockSite::AddRow](#addrow)||  
|[CDockSite::AdjustDockingLayout](#adjustdockinglayout)|(上書き[cbasepane::adjustdockinglayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout))。|  
|[CDockSite::AdjustLayout](#adjustlayout)|(上書き[cbasepane::adjustlayout](../../mfc/reference/cbasepane-class.md#adjustlayout))。|  
|[CDockSite::AlignDockSite](#aligndocksite)||  
|[CDockSite::CalcFixedLayout](#calcfixedlayout)|(上書き[cbasepane::calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout))。|  
|[CDockSite::CanAcceptPane](#canacceptpane)|(上書き[cbasepane::canacceptpane](../../mfc/reference/cbasepane-class.md#canacceptpane))。|  
|[CDockSite::CreateEx](#createex)|(上書き[cbasepane::createex](../../mfc/reference/cbasepane-class.md#createex))。|  
|[CDockSite::CreateRow](#createrow)||  
|[CDockSite::DockPane](#dockpane)|(上書き[cbasepane::dockpane](../../mfc/reference/cbasepane-class.md#dockpane))。|  
|[CDockSite::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(上書き[cbasepane::doesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore))。|  
|[CDockSite::FindRowIndex](#findrowindex)||  
|[CDockSite::FixupVirtualRects](#fixupvirtualrects)||  
|[CDockSite::GetDockSiteID](#getdocksiteid)||  
|[CDockSite::GetDockSiteRowsList](#getdocksiterowslist)||  
|[CDockSite::IsAccessibilityCompatible](#isaccessibilitycompatible)|(`CBasePane::IsAccessibilityCompatible` をオーバーライドします)。|  
|[CDockSite::IsDragMode](#isdragmode)||  
|[CDockSite::IsLastRow](#islastrow)||  
|[CDockSite::IsRectWithinDockSite](#isrectwithindocksite)||  
|[CDockSite::IsResizable](#isresizable)|(上書き[cbasepane::isresizable](../../mfc/reference/cbasepane-class.md#isresizable))。|  
|[CDockSite::MovePane](#movepane)||  
|[CDockSite::OnInsertRow](#oninsertrow)||  
|[CDockSite::OnRemoveRow](#onremoverow)||  
|[CDockSite::OnResizeRow](#onresizerow)||  
|[CDockSite::OnSetWindowPos](#onsetwindowpos)||  
|[CDockSite::OnShowRow](#onshowrow)||  
|[CDockSite::OnSizeParent](#onsizeparent)||  
|[CDockSite::PaneFromPoint](#panefrompoint)|パラメーターによって指定された点にあるドッキング サイトにドッキングされているペインを返します。|  
|[CDockSite::DockPaneLeftOf](#dockpaneleftof)|ペインを別のペインの左側にドッキングします。|  
|[CDockSite::FindPaneByID](#findpanebyid)|指定された ID によって識別されるペインを返します。|  
|[CDockSite::GetPaneList](#getpanelist)|ドッキング サイトにドッキングされているペインの一覧を返します。|  
|[CDockSite::RectSideFromPoint](#rectsidefrompoint)||  
|[CDockSite::RemovePane](#removepane)||  
|[CDockSite::RemoveRow](#removerow)||  
|[CDockSite::ReplacePane](#replacepane)||  
|[CDockSite::RepositionPanes](#repositionpanes)||  
|[CDockSite::ResizeDockSite](#resizedocksite)||  
|[CDockSite::ResizeRow](#resizerow)||  
|[CDockSite::ShowPane](#showpane)|ペインを表示します。|  
|[CDockSite::ShowRow](#showrow)||  
|[CDockSite::SwapRows](#swaprows)||  
  
## <a name="remarks"></a>コメント  
 フレームワークによって作成`CDockSite`を呼び出すときに自動的にオブジェクト[:enabledocking](../../mfc/reference/cframewndex-class.md#enabledocking)です。 ドッキング サイト ウィンドウは、メイン フレーム ウィンドウ上のクライアント領域の端に配置されます。  
  
 通常がありませんので、ドッキング サイトによって提供されるサービスを呼び出す[CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)これらのサービスを処理します。  
  
## <a name="example"></a>例  
 次の例では、`CDockSite` クラスのオブジェクトを作成する方法を示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/cpp/cdocksite-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxDockSite.h  
  
##  <a name="addrow"></a>CDockSite::AddRow  

  
```  
CDockingPanesRow* AddRow(
    POSITION pos,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pos`  
 [入力] `nHeight`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="adjustdockinglayout"></a>CDockSite::AdjustDockingLayout  

  
```  
virtual void AdjustDockingLayout();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="adjustlayout"></a>CDockSite::AdjustLayout  

  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="aligndocksite"></a>CDockSite::AlignDockSite  

  
```  
void AlignDockSite(
    const CRect& rectToAlignBy,  
    CRect& rectResult,  
    BOOL bMoveImmediately);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectToAlignBy`  
 [入力] `rectResult`  
 [入力] `bMoveImmediately`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="calcfixedlayout"></a>CDockSite::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bStretch`  
 [入力] `bHorz`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="canacceptpane"></a>CDockSite::CanAcceptPane  

  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="createex"></a>CDockSite::CreateEx  

  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    DWORD dwControlBarStyle,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwStyleEx`  
 [入力] `dwStyle`  
 [入力] `rect`  
 [入力] `pParentWnd`  
 [入力] `dwControlBarStyle`  
 [入力] `pContext`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="createrow"></a>CDockSite::CreateRow  

  
```  
virtual CDockingPanesRow* CreateRow(
    CDockSite* pParentDockBar,  
    int nOffset,  
    int nRowHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentDockBar`  
 [入力] `nOffset`  
 [入力] `nRowHeight`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="dockpane"></a>CDockSite::DockPane  

  
```  
virtual void DockPane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 [入力] `dockMethod`  
 [入力] `lpRect`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="dockpaneleftof"></a>CDockSite::DockPaneLeftOf  
 ペインを別のペインの左側にドッキングします。  
  
```  
virtual BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pBarToDock`  
 左側にドッキングするウィンドウへのポインター`pTargetBar`です。  
  
 [in][out]`pTargetBar`  
 ターゲット ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウが正常にドッキングされている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="doesallowdyninsertbefore"></a>CDockSite::DoesAllowDynInsertBefore  

  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="findpanebyid"></a>CDockSite::FindPaneByID  
 その ID を持つペインを返します  
  
```  
CPane* FindPaneByID(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 検索する、ウィンドウのコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 指定されたコマンド ID を持つペインへのポインターまたは`NULL`ウィンドウが見つからない場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="findrowindex"></a>CDockSite::FindRowIndex  

  
```  
int FindRowIndex(CDockingPanesRow* pRow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pRow`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="fixupvirtualrects"></a>CDockSite::FixupVirtualRects  

  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdocksiteid"></a>CDockSite::GetDockSiteID  

  
```  
virtual UINT GetDockSiteID() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdocksiterowslist"></a>CDockSite::GetDockSiteRowsList  

  
```  
const CObList& GetDockSiteRowsList() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpanelist"></a>CDockSite::GetPaneList  
 ドッキング サイトにドッキングされているペインの一覧を返します。  
  
```  
const CObList& GetPaneList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在、ドッキング バーにドッキングされているペインの一覧への参照を読み取り専用です。  
  
##  <a name="isaccessibilitycompatible"></a>CDockSite::IsAccessibilityCompatible  

  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isdragmode"></a>CDockSite::IsDragMode  

  
```  
virtual BOOL IsDragMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="islastrow"></a>CDockSite::IsLastRow  

  
```  
bool IsLastRow(CDockingPanesRow* pRow) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pRow`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isrectwithindocksite"></a>CDockSite::IsRectWithinDockSite  

  
```  
BOOL IsRectWithinDockSite(
    CRect rect,  
    CPoint& ptDelta);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 [入力] `ptDelta`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isresizable"></a>CDockSite::IsResizable  

  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="movepane"></a>CDockSite::MovePane  

  
```  
virtual BOOL MovePane(
    CPane* pWnd,  
    UINT nFlags,  
    CPoint ptOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 [入力] `nFlags`  
 [入力] `ptOffset`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="oninsertrow"></a>CDockSite::OnInsertRow  

  
```  
virtual void OnInsertRow(POSITION pos);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pos`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onremoverow"></a>CDockSite::OnRemoveRow  

  
```  
virtual void OnRemoveRow(
    POSITION pos,  
    BOOL bByShow = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pos`  
 [入力] `bByShow`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onresizerow"></a>CDockSite::OnResizeRow  

  
```  
virtual int OnResizeRow(
    CDockingPanesRow* pRowToResize,  
    int nOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pRowToResize`  
 [入力] `nOffset`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onsizeparent"></a>CDockSite::OnSizeParent  

  
```  
virtual void OnSizeParent(
    CRect& rectAvailable,  
    UINT nSide,  
    BOOL bExpand,  
    int nOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectAvailable`  
 [入力] `nSide`  
 [入力] `bExpand`  
 [入力] `nOffset`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onsetwindowpos"></a>CDockSite::OnSetWindowPos  

  
```  
virtual BOOL OnSetWindowPos(
    const CWnd* pWndInsertAfter,  
    const CRect& rectWnd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndInsertAfter`  
 [入力] `rectWnd`  
 [入力] `nFlags`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshowrow"></a>CDockSite::OnShowRow  

  
```  
virtual void OnShowRow(
    POSITION pos,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pos`  
 [入力] `bShow`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="panefrompoint"></a>CDockSite::PaneFromPoint  
 パラメーターによって指定された点にあるドッキング サイトにドッキングされているペインを返します。  
  
```  
virtual CPane* PaneFromPoint(CPoint pt);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pt`  
 取得するウィンドウを画面座標でのポイント。  
  
### <a name="return-value"></a>戻り値  
 指定した位置にあるペインへのポインターまたは`NULL`場合は、ウィンドウは指定した位置に存在しません。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="rectsidefrompoint"></a>CDockSite::RectSideFromPoint  

  
```  
static int __stdcall RectSideFromPoint(
    const CRect& rect,  
    const CPoint& point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 [入力] `point`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removepane"></a>CDockSite::RemovePane  

  
```  
virtual void RemovePane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 [入力] `dockMethod`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removerow"></a>CDockSite::RemoveRow  

  
```  
void RemoveRow(CDockingPanesRow* pRow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pRow`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="replacepane"></a>CDockSite::ReplacePane  

  
```  
BOOL ReplacePane(
    CPane* pOldBar,  
    CPane* pNewBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pOldBar`  
 [入力] `pNewBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="repositionpanes"></a>CDockSite::RepositionPanes  

  
```  
virtual void RepositionPanes(CRect& rectNewClientArea);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectNewClientArea`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="resizedocksite"></a>CDockSite::ResizeDockSite  

  
```  
void ResizeDockSite(
    int nNewWidth,  
    int nNewHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nNewWidth`  
 [入力] `nNewHeight`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="resizerow"></a>CDockSite::ResizeRow  

  
```  
int ResizeRow(
    CDockingPanesRow* pRow,  
    int nNewSize,  
    BOOL bAdjustLayout = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pRow`  
 [入力] `nNewSize`  
 [入力] `bAdjustLayout`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="showpane"></a>CDockSite::ShowPane  
 ペインを表示します。  
  
```  
virtual BOOL ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pBar`  
 ウィンドウを表示するか非表示へのポインター。  
  
 [入力] `bShow`  
 `TRUE`ウィンドウを表示することを指定するには`FALSE`ウィンドウが非表示にすることを指定します。  
  
 [入力] `bDelay`  
 `TRUE`ウィンドウのレイアウトをペインが終了するまで遅延させることを指定するを示すです。それ以外の場合、`FALSE`です。  
  
 [入力] `bActivate`  
 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ウィンドウが表示または非表示に正常にします。 `FALSE`指定されたペインがこれに属していない場合は、サイトをドッキングします。  
  
### <a name="remarks"></a>コメント  
 ドッキング ウィンドウを非表示には、このメソッドを呼び出します。 通常がありませんを呼び出す`CDockSite::ShowPane`直接、親フレーム ウィンドウまたはベースのウィンドウで、これを呼び出すためです。  
  
##  <a name="showrow"></a>CDockSite::ShowRow  

  
```  
void ShowRow(
    CDockingPanesRow* pRow,  
    BOOL bShow,  
    BOOL bAdjustLayout);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pRow`  
 [入力] `bShow`  
 [入力] `bAdjustLayout`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="swaprows"></a>CDockSite::SwapRows  

  
```  
void SwapRows(
    CDockingPanesRow* pFirstRow,  
    CDockingPanesRow* pSecondRow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pFirstRow`  
 [入力] `pSecondRow`  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CBasePane クラス](../../mfc/reference/cbasepane-class.md)
