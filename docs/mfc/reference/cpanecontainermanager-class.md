---
title: "CPaneContainerManager クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaneContainerManager
- AFXPANECONTAINERMANAGER/CPaneContainerManager
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneContainerManager
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneContainerManagerToDockablePane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPanesToList
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneToList
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneToRecentPaneContainer
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CalcRects
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CanBeAttached
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CheckAndRemoveNonValidPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CheckForMiniFrameAndCaption
- AFXPANECONTAINERMANAGER/CPaneContainerManager::Create
- AFXPANECONTAINERMANAGER/CPaneContainerManager::DoesAllowDynInsertBefore
- AFXPANECONTAINERMANAGER/CPaneContainerManager::DoesContainFloatingPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::EnableGrippers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::FindPaneContainer
- AFXPANECONTAINERMANAGER/CPaneContainerManager::FindTabbedPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetAvailableSpace
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetDefaultPaneDivider
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetDockSiteFrameWnd
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetFirstPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetFirstVisiblePane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetMinMaxOffset
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetMinSize
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetNodeCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetPaneContainerRTC
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetPaneCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetTotalRefCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetVisiblePaneCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetWindowRect
- AFXPANECONTAINERMANAGER/CPaneContainerManager::HideAll
- AFXPANECONTAINERMANAGER/CPaneContainerManager::InsertPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::IsAutoHideMode
- AFXPANECONTAINERMANAGER/CPaneContainerManager::IsEmpty
- AFXPANECONTAINERMANAGER/CPaneContainerManager::IsRootPaneContainerVisible
- AFXPANECONTAINERMANAGER/CPaneContainerManager::NotifyPaneDivider
- AFXPANECONTAINERMANAGER/CPaneContainerManager::OnPaneDividerMove
- AFXPANECONTAINERMANAGER/CPaneContainerManager::OnShowPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::PaneFromPoint
- AFXPANECONTAINERMANAGER/CPaneContainerManager::ReleaseEmptyPaneContainers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemoveAllPanesAndPaneDividers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemoveNonValidPanes
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemovePaneDivider
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemovePaneFromPaneContainer
- AFXPANECONTAINERMANAGER/CPaneContainerManager::ReplacePane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::ResizePaneContainers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::Serialize
- AFXPANECONTAINERMANAGER/CPaneContainerManager::SetDefaultPaneDividerForPanes
- AFXPANECONTAINERMANAGER/CPaneContainerManager::SetPaneContainerRTC
- AFXPANECONTAINERMANAGER/CPaneContainerManager::SetResizeMode
- AFXPANECONTAINERMANAGER/CPaneContainerManager::StoreRecentDockSiteInfo
dev_langs:
- C++
helpviewer_keywords:
- CPaneContainerManager class
ms.assetid: 3d974c15-a62f-4648-bb5b-cc31ab7950af
caps.latest.revision: 29
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
ms.openlocfilehash: 377b80ba193d1bf8bf358b709aade192e55dab86
ms.lasthandoff: 02/24/2017

---
# <a name="cpanecontainermanager-class"></a>CPaneContainerManager クラス
`CPaneContainerManager`クラスは、記憶域と現在のドッキング レイアウトの表示を管理します。  
  
## <a name="syntax"></a>構文  
  
```  
class CPaneContainerManager : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneContainerManager::AddPane](#addpane)||  
|[CPaneContainerManager::AddPaneContainerManager](#addpanecontainermanager)||  
|[CPaneContainerManager::AddPaneContainerManagerToDockablePane](#addpanecontainermanagertodockablepane)||  
|[CPaneContainerManager::AddPanesToList](#addpanestolist)||  
|[CPaneContainerManager::AddPaneToList](#addpanetolist)||  
|[CPaneContainerManager::AddPaneToRecentPaneContainer](#addpanetorecentpanecontainer)||  
|[CPaneContainerManager::CalcRects](#calcrects)||  
|[CPaneContainerManager::CanBeAttached](#canbeattached)||  
|[CPaneContainerManager::CheckAndRemoveNonValidPane](#checkandremovenonvalidpane)||  
|[CPaneContainerManager::CheckForMiniFrameAndCaption](#checkforminiframeandcaption)||  
|[CPaneContainerManager::Create](#create)||  
|[CPaneContainerManager::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)||  
|[CPaneContainerManager::DoesContainFloatingPane](#doescontainfloatingpane)||  
|[CPaneContainerManager::EnableGrippers](#enablegrippers)||  
|[CPaneContainerManager::FindPaneContainer](#findpanecontainer)||  
|[CPaneContainerManager::FindTabbedPane](#findtabbedpane)||  
|[CPaneContainerManager::GetAvailableSpace](#getavailablespace)||  
|[CPaneContainerManager::GetDefaultPaneDivider](#getdefaultpanedivider)||  
|[CPaneContainerManager::GetDockSiteFrameWnd](#getdocksiteframewnd)||  
|[CPaneContainerManager::GetFirstPane](#getfirstpane)||  
|[CPaneContainerManager::GetFirstVisiblePane](#getfirstvisiblepane)||  
|[CPaneContainerManager::GetMinMaxOffset](#getminmaxoffset)||  
|[CPaneContainerManager::GetMinSize](#getminsize)||  
|[CPaneContainerManager::GetNodeCount](#getnodecount)||  
|[CPaneContainerManager::GetPaneContainerRTC](#getpanecontainerrtc)||  
|[CPaneContainerManager::GetPaneCount](#getpanecount)||  
|[CPaneContainerManager::GetTotalRefCount](#gettotalrefcount)||  
|[CPaneContainerManager::GetVisiblePaneCount](#getvisiblepanecount)||  
|[CPaneContainerManager::GetWindowRect](#getwindowrect)||  
|[CPaneContainerManager::HideAll](#hideall)||  
|[CPaneContainerManager::InsertPane](#insertpane)||  
|[CPaneContainerManager::IsAutoHideMode](#isautohidemode)||  
|[CPaneContainerManager::IsEmpty](#isempty)||  
|[CPaneContainerManager::IsRootPaneContainerVisible](#isrootpanecontainervisible)||  
|[CPaneContainerManager::NotifyPaneDivider](#notifypanedivider)||  
|[CPaneContainerManager::OnPaneDividerMove](#onpanedividermove)||  
|[CPaneContainerManager::OnShowPane](#onshowpane)||  
|[CPaneContainerManager::PaneFromPoint](#panefrompoint)||  
|[CPaneContainerManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)||  
|[CPaneContainerManager::RemoveAllPanesAndPaneDividers](#removeallpanesandpanedividers)||  
|[CPaneContainerManager::RemoveNonValidPanes](#removenonvalidpanes)||  
|[CPaneContainerManager::RemovePaneDivider](#removepanedivider)||  
|[CPaneContainerManager::RemovePaneFromPaneContainer](#removepanefrompanecontainer)||  
|[CPaneContainerManager::ReplacePane](#replacepane)||  
|[CPaneContainerManager::ResizePaneContainers](#resizepanecontainers)||  
|[CPaneContainerManager::Serialize](#serialize)|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。 (上書き[指定](../../mfc/reference/cobject-class.md#serialize))。|  
|[CPaneContainerManager::SetDefaultPaneDividerForPanes](#setdefaultpanedividerforpanes)||  
|[CPaneContainerManager::SetPaneContainerRTC](#setpanecontainerrtc)||  
|[CPaneContainerManager::SetResizeMode](#setresizemode)||  
|[CPaneContainerManager::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
  
### <a name="remarks"></a>コメント  
 フレームワークのインスタンスを自動的に作成する`CPaneContainerManager`オブジェクトし、そのファイルを埋め込みますに[CPaneDivider クラス](../../mfc/reference/cpanedivider-class.md)オブジェクトまたは[CMultiPaneFrameWnd クラス](../../mfc/reference/cmultipaneframewnd-class.md)オブジェクトです。  
  
 `CPaneContainerManager`クラスから構築されるバイナリ ツリーのルートへのポインターを格納する[CPaneContainer](../../mfc/reference/cpanecontainer-class.md)オブジェクトです。  
  
## <a name="example"></a>例  
 次の例への参照を取得する方法、`CPaneContainerManager`オブジェクトです。 このコード スニペットの一部である、[ウィンドウのサイズを設定サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_SetPaneSize&#5;](../../mfc/reference/codesnippet/cpp/cpanecontainermanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CPaneContainerManager](../../mfc/reference/cpanecontainermanager-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpanecontainermanager.h  
  
##  <a name="addpane"></a>CPaneContainerManager::AddPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void AddPane(CDockablePane* pControlBarToAdd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBarToAdd`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addpanecontainermanager"></a>CPaneContainerManager::AddPaneContainerManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AddPaneContainerManager(
    CPaneContainerManager& srcManager,  
    BOOL bOuterEdge);

 
virtual BOOL AddPaneContainerManager(
    CDockablePane* pTargetControlBar,  
    DWORD dwAlignment,  
    CPaneContainerManager& srcManager,  
    BOOL bCopy);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `srcManager`  
 [入力] `bOuterEdge`  
 [入力] `pTargetControlBar`  
 [入力] `dwAlignment`  
 [入力] `bCopy`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addpanecontainermanagertodockablepane"></a>CPaneContainerManager::AddPaneContainerManagerToDockablePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AddPaneContainerManagerToDockablePane(
    CDockablePane* pTargetControlBar,  
    CPaneContainerManager& srcManager);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pTargetControlBar`  
 [入力] `srcManager`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addpanestolist"></a>CPaneContainerManager::AddPanesToList  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AddPanesToList(
    CObList* plstControlBars,  
    CObList* plstSliders);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `plstControlBars`  
 [入力] `plstSliders`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addpanetolist"></a>CPaneContainerManager::AddPaneToList  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AddPaneToList(CDockablePane* pControlBarToAdd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBarToAdd`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addpanetorecentpanecontainer"></a>CPaneContainerManager::AddPaneToRecentPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CDockablePane* AddPaneToRecentPaneContainer(
    CDockablePane* pBarToAdd,  
    CPaneContainer* pRecentContainer);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBarToAdd`  
 [入力] `pRecentContainer`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="calcrects"></a>CPaneContainerManager::CalcRects  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void CalcRects(
    CRect& rectOriginal,  
    CRect& rectInserted,  
    CRect& rectSlider,  
    DWORD& dwSliderStyle,  
    DWORD dwAlignment,  
    CSize sizeMinOriginal,  
    CSize sizeMinInserted);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectOriginal`  
 [入力] `rectInserted`  
 [入力] `rectSlider`  
 [入力] `dwSliderStyle`  
 [入力] `dwAlignment`  
 [入力] `sizeMinOriginal`  
 [入力] `sizeMinInserted`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="canbeattached"></a>CPaneContainerManager::CanBeAttached  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="checkandremovenonvalidpane"></a>CPaneContainerManager::CheckAndRemoveNonValidPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CheckAndRemoveNonValidPane(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="checkforminiframeandcaption"></a>CPaneContainerManager::CheckForMiniFrameAndCaption  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CheckForMiniFrameAndCaption(
    CPoint point,  
    CDockablePane** ppTargetControlBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 [入力] `ppTargetControlBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="create"></a>CPaneContainerManager::Create  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    CPaneDivider* pDefaultSlider,  
    CRuntimeClass* pContainerRTC = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentWnd`  
 [入力] `pDefaultSlider`  
 [入力] `pContainerRTC`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="doesallowdyninsertbefore"></a>CPaneContainerManager::DoesAllowDynInsertBefore  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="doescontainfloatingpane"></a>CPaneContainerManager::DoesContainFloatingPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DoesContainFloatingPane();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enablegrippers"></a>CPaneContainerManager::EnableGrippers  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void EnableGrippers(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="findpanecontainer"></a>CPaneContainerManager::FindPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,  
    BOOL& bLeftBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `bLeftBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="findtabbedpane"></a>CPaneContainerManager::FindTabbedPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CDockablePane* FindTabbedPane(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getavailablespace"></a>CPaneContainerManager::GetAvailableSpace  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void GetAvailableSpace(CRect& rect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdefaultpanedivider"></a>CPaneContainerManager::GetDefaultPaneDivider  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CPaneDivider* GetDefaultPaneDivider() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdocksiteframewnd"></a>CPaneContainerManager::GetDockSiteFrameWnd  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CWnd* GetDockSiteFrameWnd();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getfirstpane"></a>CPaneContainerManager::GetFirstPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CBasePane* GetFirstPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getfirstvisiblepane"></a>CPaneContainerManager::GetFirstVisiblePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CWnd* GetFirstVisiblePane() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getminmaxoffset"></a>CPaneContainerManager::GetMinMaxOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void GetMinMaxOffset(
    CPaneDivider* pSlider,  
    int& nMinOffset,  
    int& nMaxOffset,  
    int& nStep);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pSlider`  
 [入力] `nMinOffset`  
 [入力] `nMaxOffset`  
 [入力] `nStep`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getminsize"></a>CPaneContainerManager::GetMinSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void GetMinSize(CSize& size);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `size`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getnodecount"></a>CPaneContainerManager::GetNodeCount  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetNodeCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpanecontainerrtc"></a>CPaneContainerManager::GetPaneContainerRTC  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRuntimeClass* GetPaneContainerRTC() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpanecount"></a>CPaneContainerManager::GetPaneCount  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetPaneCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettotalrefcount"></a>CPaneContainerManager::GetTotalRefCount  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTotalRefCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getvisiblepanecount"></a>CPaneContainerManager::GetVisiblePaneCount  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetVisiblePaneCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getwindowrect"></a>CPaneContainerManager::GetWindowRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void GetWindowRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hideall"></a>CPaneContainerManager::HideAll  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void HideAll();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="insertpane"></a>CPaneContainerManager::InsertPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL InsertPane(
    CDockablePane* pControlBarToInsert,  
    CDockablePane* pTargetControlBar,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL,  
    AFX_DOCK_METHOD dockMethod = DM_UNKNOWN);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBarToInsert`  
 [入力] `pTargetControlBar`  
 [入力] `dwAlignment`  
 [入力] `lpRect`  
 [入力] `dockMethod`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isautohidemode"></a>CPaneContainerManager::IsAutoHideMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isempty"></a>CPaneContainerManager::IsEmpty  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isrootpanecontainervisible"></a>CPaneContainerManager::IsRootPaneContainerVisible  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsRootPaneContainerVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="notifypanedivider"></a>CPaneContainerManager::NotifyPaneDivider  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void NotifyPaneDivider();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onpanedividermove"></a>CPaneContainerManager::OnPaneDividerMove  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int OnPaneDividerMove(
    CPaneDivider* pSlider,  
    UINT uFlags,  
    int nOffset,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pSlider`  
 [入力] `uFlags`  
 [入力] `nOffset`  
 [入力] `hdwp`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshowpane"></a>CPaneContainerManager::OnShowPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `bShow`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="panefrompoint"></a>CPaneContainerManager::PaneFromPoint  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CDockablePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    BOOL bExactBar,  
    BOOL& bIsTabArea,  
    BOOL& bCaption);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 [入力] `nSensitivity`  
 [入力] `bExactBar`  
 [入力] `bIsTabArea`  
 [入力] `bCaption`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="releaseemptypanecontainers"></a>CPaneContainerManager::ReleaseEmptyPaneContainers  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ReleaseEmptyPaneContainers();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removeallpanesandpanedividers"></a>CPaneContainerManager::RemoveAllPanesAndPaneDividers  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void RemoveAllPanesAndPaneDividers();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removenonvalidpanes"></a>CPaneContainerManager::RemoveNonValidPanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void RemoveNonValidPanes();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removepanedivider"></a>CPaneContainerManager::RemovePaneDivider  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RemovePaneDivider(CPaneDivider* pSlider);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pSlider`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removepanefrompanecontainer"></a>CPaneContainerManager::RemovePaneFromPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL RemovePaneFromPaneContainer(CDockablePane* pControlBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="replacepane"></a>CPaneContainerManager::ReplacePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL ReplacePane(
    CDockablePane* pBarOld,  
    CDockablePane* pBarNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBarOld`  
 [入力] `pBarNew`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="resizepanecontainers"></a>CPaneContainerManager::ResizePaneContainers  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ResizePaneContainers(
    UINT nSide,  
    BOOL bExpand,  
    int nOffset,  
    HDWP& hdwp);

 
virtual void ResizePaneContainers(
    CRect rect,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nSide`  
 [入力] `bExpand`  
 [入力] `nOffset`  
 [入力] `hdwp`  
 [入力] `rect`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="serialize"></a>CPaneContainerManager::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setdefaultpanedividerforpanes"></a>CPaneContainerManager::SetDefaultPaneDividerForPanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetDefaultPaneDividerForPanes(CPaneDivider* pSlider);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pSlider`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpanecontainerrtc"></a>CPaneContainerManager::SetPaneContainerRTC  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPaneContainerRTC(CRuntimeClass* pContainerRTC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pContainerRTC`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setresizemode"></a>CPaneContainerManager::SetResizeMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetResizeMode(BOOL bResize);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bResize`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="storerecentdocksiteinfo"></a>CPaneContainerManager::StoreRecentDockSiteInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void StoreRecentDockSiteInfo(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)   
 [CPaneDivider クラス](../../mfc/reference/cpanedivider-class.md)

