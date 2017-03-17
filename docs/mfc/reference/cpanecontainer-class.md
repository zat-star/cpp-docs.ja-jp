---
title: "CPaneContainer クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaneContainer
- AFXPANECONTAINER/CPaneContainer
- AFXPANECONTAINER/CPaneContainer::CPaneContainer
- AFXPANECONTAINER/CPaneContainer::AddPane
- AFXPANECONTAINER/CPaneContainer::AddRef
- AFXPANECONTAINER/CPaneContainer::AddSubPaneContainer
- AFXPANECONTAINER/CPaneContainer::CalcAvailablePaneSpace
- AFXPANECONTAINER/CPaneContainer::CalcAvailableSpace
- AFXPANECONTAINER/CPaneContainer::CalculateRecentSize
- AFXPANECONTAINER/CPaneContainer::CheckPaneDividerVisibility
- AFXPANECONTAINER/CPaneContainer::Copy
- AFXPANECONTAINER/CPaneContainer::DeletePane
- AFXPANECONTAINER/CPaneContainer::FindSubPaneContainer
- AFXPANECONTAINER/CPaneContainer::FindTabbedPane
- AFXPANECONTAINER/CPaneContainer::GetAssociatedSiblingPaneIDs
- AFXPANECONTAINER/CPaneContainer::GetLeftPane
- AFXPANECONTAINER/CPaneContainer::GetLeftPaneContainer
- AFXPANECONTAINER/CPaneContainer::GetMinSize
- AFXPANECONTAINER/CPaneContainer::GetMinSizeLeft
- AFXPANECONTAINER/CPaneContainer::GetMinSizeRight
- AFXPANECONTAINER/CPaneContainer::GetNodeCount
- AFXPANECONTAINER/CPaneContainer::GetPaneDivider
- AFXPANECONTAINER/CPaneContainer::GetParentPaneContainer
- AFXPANECONTAINER/CPaneContainer::GetRecentPaneDividerRect
- AFXPANECONTAINER/CPaneContainer::GetRecentPaneDividerStyle
- AFXPANECONTAINER/CPaneContainer::GetRecentPercent
- AFXPANECONTAINER/CPaneContainer::GetRefCount
- AFXPANECONTAINER/CPaneContainer::GetResizeStep
- AFXPANECONTAINER/CPaneContainer::GetRightPane
- AFXPANECONTAINER/CPaneContainer::GetRightPaneContainer
- AFXPANECONTAINER/CPaneContainer::GetTotalReferenceCount
- AFXPANECONTAINER/CPaneContainer::GetWindowRect
- AFXPANECONTAINER/CPaneContainer::IsDisposed
- AFXPANECONTAINER/CPaneContainer::IsEmpty
- AFXPANECONTAINER/CPaneContainer::IsLeftPane
- AFXPANECONTAINER/CPaneContainer::IsLeftPaneContainer
- AFXPANECONTAINER/CPaneContainer::IsLeftPartEmpty
- AFXPANECONTAINER/CPaneContainer::IsRightPartEmpty
- AFXPANECONTAINER/CPaneContainer::IsVisible
- AFXPANECONTAINER/CPaneContainer::Move
- AFXPANECONTAINER/CPaneContainer::OnDeleteHidePane
- AFXPANECONTAINER/CPaneContainer::OnMoveInternalPaneDivider
- AFXPANECONTAINER/CPaneContainer::OnShowPane
- AFXPANECONTAINER/CPaneContainer::Release
- AFXPANECONTAINER/CPaneContainer::ReleaseEmptyPaneContainer
- AFXPANECONTAINER/CPaneContainer::RemoveNonValidPanes
- AFXPANECONTAINER/CPaneContainer::RemovePane
- AFXPANECONTAINER/CPaneContainer::Resize
- AFXPANECONTAINER/CPaneContainer::ResizePane
- AFXPANECONTAINER/CPaneContainer::ResizePartOfPaneContainer
- AFXPANECONTAINER/CPaneContainer::Serialize
- AFXPANECONTAINER/CPaneContainer::SetPane
- AFXPANECONTAINER/CPaneContainer::SetPaneContainer
- AFXPANECONTAINER/CPaneContainer::SetPaneDivider
- AFXPANECONTAINER/CPaneContainer::SetParentPaneContainer
- AFXPANECONTAINER/CPaneContainer::SetRecentPercent
- AFXPANECONTAINER/CPaneContainer::SetUpByID
- AFXPANECONTAINER/CPaneContainer::StoreRecentDockSiteInfo
- AFXPANECONTAINER/CPaneContainer::StretchPaneContainer
dev_langs:
- C++
helpviewer_keywords:
- CPaneContainer class
ms.assetid: beb79e08-f611-4d66-ba04-053baa79bf86
caps.latest.revision: 32
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
ms.openlocfilehash: c6db2e98d9c9301559d8a689cc4094a5a423aa7f
ms.lasthandoff: 02/24/2017

---
# <a name="cpanecontainer-class"></a>CPaneContainer クラス
`CPaneContainer`クラスは、MFC によって実装されるドッキング モデルの基本的なコンポーネントです。 このクラスのオブジェクトは、2 つのドッキング ペイン、または `CPaneContainer.` の&2; つのインスタンスへのポインターを格納します。また、ペイン (またはコンテナー) を分割している区分線へのポインターも格納します。 コンテナー内にコンテナーを入れ子にすると、フレームワークは複雑なドッキング レイアウトを表すバイナリ ツリーを構築します。 バイナリ ツリーのルートに格納されている、 [CPaneContainerManager](../../mfc/reference/cpanecontainermanager-class.md)オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
class CPaneContainer : public CObject    
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneContainer::CPaneContainer](#cpanecontainer)|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneContainer::AddPane](#addpane)||  
|[CPaneContainer::AddRef](#addref)||  
|[CPaneContainer::AddSubPaneContainer](#addsubpanecontainer)||  
|[CPaneContainer::CalcAvailablePaneSpace](#calcavailablepanespace)||  
|[CPaneContainer::CalcAvailableSpace](#calcavailablespace)||  
|[CPaneContainer::CalculateRecentSize](#calculaterecentsize)||  
|[CPaneContainer::CheckPaneDividerVisibility](#checkpanedividervisibility)||  
|[CPaneContainer::Copy](#copy)||  
|[CPaneContainer::DeletePane](#deletepane)||  
|[CPaneContainer::FindSubPaneContainer](#findsubpanecontainer)||  
|[CPaneContainer::FindTabbedPane](#findtabbedpane)||  
|[CPaneContainer::GetAssociatedSiblingPaneIDs](#getassociatedsiblingpaneids)||  
|[CPaneContainer::GetLeftPane](#getleftpane)||  
|[CPaneContainer::GetLeftPaneContainer](#getleftpanecontainer)||  
|[CPaneContainer::GetMinSize](#getminsize)||  
|[CPaneContainer::GetMinSizeLeft](#getminsizeleft)||  
|[CPaneContainer::GetMinSizeRight](#getminsizeright)||  
|[CPaneContainer::GetNodeCount](#getnodecount)||  
|[CPaneContainer::GetPaneDivider](#getpanedivider)||  
|[CPaneContainer::GetParentPaneContainer](#getparentpanecontainer)||  
|[CPaneContainer::GetRecentPaneDividerRect](#getrecentpanedividerrect)||  
|[CPaneContainer::GetRecentPaneDividerStyle](#getrecentpanedividerstyle)||  
|[CPaneContainer::GetRecentPercent](#getrecentpercent)||  
|[CPaneContainer::GetRefCount](#getrefcount)||  
|[CPaneContainer::GetResizeStep](#getresizestep)||  
|[CPaneContainer::GetRightPane](#getrightpane)||  
|[CPaneContainer::GetRightPaneContainer](#getrightpanecontainer)||  
|[CPaneContainer::GetTotalReferenceCount](#gettotalreferencecount)||  
|[CPaneContainer::GetWindowRect](#getwindowrect)||  
|[CPaneContainer::IsDisposed](#isdisposed)||  
|[CPaneContainer::IsEmpty](#isempty)||  
|[CPaneContainer::IsLeftPane](#isleftpane)||  
|[CPaneContainer::IsLeftPaneContainer](#isleftpanecontainer)||  
|[CPaneContainer::IsLeftPartEmpty](#isleftpartempty)||  
|[CPaneContainer::IsRightPartEmpty](#isrightpartempty)||  
|[CPaneContainer::IsVisible](#isvisible)||  
|[CPaneContainer::Move](#move)||  
|[CPaneContainer::OnDeleteHidePane](#ondeletehidepane)||  
|[CPaneContainer::OnMoveInternalPaneDivider](#onmoveinternalpanedivider)||  
|[CPaneContainer::OnShowPane](#onshowpane)||  
|[CPaneContainer::Release](#release)||  
|[CPaneContainer::ReleaseEmptyPaneContainer](#releaseemptypanecontainer)||  
|[CPaneContainer::RemoveNonValidPanes](#removenonvalidpanes)||  
|[CPaneContainer::RemovePane](#removepane)||  
|[CPaneContainer::Resize](#resize)||  
|[CPaneContainer::ResizePane](#resizepane)||  
|[CPaneContainer::ResizePartOfPaneContainer](#resizepartofpanecontainer)||  
|[CPaneContainer::Serialize](#serialize)|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。 (上書き[指定](../../mfc/reference/cobject-class.md#serialize))。|  
|[CPaneContainer::SetPane](#setpane)||  
|[CPaneContainer::SetPaneContainer](#setpanecontainer)||  
|[CPaneContainer::SetPaneDivider](#setpanedivider)||  
|[CPaneContainer::SetParentPaneContainer](#setparentpanecontainer)||  
|[CPaneContainer::SetRecentPercent](#setrecentpercent)||  
|[CPaneContainer::SetUpByID](#setupbyid)||  
|[CPaneContainer::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneContainer::StretchPaneContainer](#stretchpanecontainer)||  
  
### <a name="remarks"></a>コメント  
 `CPaneContainer`オブジェクトは、フレームワークによって自動的に作成されます。  
  
## <a name="example"></a>例  
 次の例では、インスタンスを構築、`CPaneContainer`クラスです。 このコード スニペットの一部である、[ウィンドウのサイズを設定サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_SetPaneSize&#2;](../../mfc/reference/codesnippet/cpp/cpanecontainer-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize&#1;](../../mfc/reference/codesnippet/cpp/cpanecontainer-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CPaneContainer](../../mfc/reference/cpanecontainer-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpanecontainer.h  
  
##  <a name="addpane"></a>CPaneContainer::AddPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CDockablePane* AddPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addref"></a>CPaneContainer::AddRef  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AddRef();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addsubpanecontainer"></a>CPaneContainer::AddSubPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL AddSubPaneContainer(
    CPaneContainer* pContainer,  
    BOOL bRightNodeNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pContainer`  
 [入力] `bRightNodeNew`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="calcavailablepanespace"></a>CPaneContainer::CalcAvailablePaneSpace  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int CalcAvailablePaneSpace(
    int nRequiredOffset,  
    CPane* pBar,  
    CPaneContainer* pContainer,  
    BOOL bLeftBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nRequiredOffset`  
 [入力] `pBar`  
 [入力] `pContainer`  
 [入力] `bLeftBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="calcavailablespace"></a>CPaneContainer::CalcAvailableSpace  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize CalcAvailableSpace(
    CSize sizeStretch,  
    BOOL bLeftBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `sizeStretch`  
 [入力] `bLeftBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="calculaterecentsize"></a>CPaneContainer::CalculateRecentSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void CalculateRecentSize();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="checkpanedividervisibility"></a>CPaneContainer::CheckPaneDividerVisibility  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void CheckPaneDividerVisibility();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="copy"></a>CPaneContainer::Copy  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CPaneContainer* Copy(CPaneContainer* pParentContainer);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentContainer`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="cpanecontainer"></a>CPaneContainer::CPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CPaneContainer(
    CPaneContainerManager* pManager = NULL,  
    CDockablePane* pLeftBar = NULL,  
    CDockablePane* pRightBar = NULL,  
    CPaneDivider* pSlider = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pManager`  
 [入力] `pLeftBar`  
 [入力] `pRightBar`  
 [入力] `pSlider`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="deletepane"></a>CPaneContainer::DeletePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void DeletePane(
    CDockablePane* pBar,  
    BC_FIND_CRITERIA barType);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `barType`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="findsubpanecontainer"></a>CPaneContainer::FindSubPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CPaneContainer* FindSubPaneContainer(
    const CObject* pObject,  
    BC_FIND_CRITERIA findCriteria);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pObject`  
 [入力] `findCriteria`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="findtabbedpane"></a>CPaneContainer::FindTabbedPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CDockablePane* FindTabbedPane(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getassociatedsiblingpaneids"></a>CPaneContainer::GetAssociatedSiblingPaneIDs  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CList<UINT, UINT>* GetAssociatedSiblingPaneIDs(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getleftpane"></a>CPaneContainer::GetLeftPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CDockablePane* GetLeftPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getleftpanecontainer"></a>CPaneContainer::GetLeftPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CPaneContainer* GetLeftPaneContainer() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getminsize"></a>CPaneContainer::GetMinSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `size`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getminsizeleft"></a>CPaneContainer::GetMinSizeLeft  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void GetMinSizeLeft(CSize& size) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `size`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getminsizeright"></a>CPaneContainer::GetMinSizeRight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void GetMinSizeRight(CSize& size) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `size`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getnodecount"></a>CPaneContainer::GetNodeCount  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetNodeCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpanedivider"></a>CPaneContainer::GetPaneDivider  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CPaneDivider* GetPaneDivider() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getparentpanecontainer"></a>CPaneContainer::GetParentPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CPaneContainer* GetParentPaneContainer() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrecentpanedividerrect"></a>CPaneContainer::GetRecentPaneDividerRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetRecentPaneDividerRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrecentpanedividerstyle"></a>CPaneContainer::GetRecentPaneDividerStyle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
DWORD GetRecentPaneDividerStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrecentpercent"></a>CPaneContainer::GetRecentPercent  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetRecentPercent();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrefcount"></a>CPaneContainer::GetRefCount  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
LONG GetRefCount();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getresizestep"></a>CPaneContainer::GetResizeStep  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetResizeStep() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrightpane"></a>CPaneContainer::GetRightPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CDockablePane* GetRightPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrightpanecontainer"></a>CPaneContainer::GetRightPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CPaneContainer* GetRightPaneContainer() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettotalreferencecount"></a>CPaneContainer::GetTotalReferenceCount  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTotalReferenceCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getwindowrect"></a>CPaneContainer::GetWindowRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void GetWindowRect(
    CRect& rect,  
    BOOL bIgnoreVisibility = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 [入力] `bIgnoreVisibility`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isdisposed"></a>CPaneContainer::IsDisposed  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsDisposed() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isempty"></a>CPaneContainer::IsEmpty  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isleftpane"></a>CPaneContainer::IsLeftPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsLeftPane(CDockablePane* pBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isleftpanecontainer"></a>CPaneContainer::IsLeftPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsLeftPaneContainer() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isleftpartempty"></a>CPaneContainer::IsLeftPartEmpty  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsLeftPartEmpty(BOOL bCheckVisibility = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bCheckVisibility`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isrightpartempty"></a>CPaneContainer::IsRightPartEmpty  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsRightPartEmpty(BOOL bCheckVisibility = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bCheckVisibility`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isvisible"></a>CPaneContainer::IsVisible  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="move"></a>CPaneContainer::Move  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Move(CPoint ptNewLeftTop);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ptNewLeftTop`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondeletehidepane"></a>CPaneContainer::OnDeleteHidePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void OnDeleteHidePane(
    CDockablePane* pBar,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `bHide`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onmoveinternalpanedivider"></a>CPaneContainer::OnMoveInternalPaneDivider  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int OnMoveInternalPaneDivider(
    int nOffset,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 [入力] `hdwp`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshowpane"></a>CPaneContainer::OnShowPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `bShow`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="release"></a>CPaneContainer::Release  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
DWORD Release();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="releaseemptypanecontainer"></a>CPaneContainer::ReleaseEmptyPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ReleaseEmptyPaneContainer();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removenonvalidpanes"></a>CPaneContainer::RemoveNonValidPanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void RemoveNonValidPanes();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removepane"></a>CPaneContainer::RemovePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RemovePane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="resize"></a>CPaneContainer::Resize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Resize(
    CRect rect,  
    HDWP& hdwp,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 [入力] `hdwp`  
 [入力] `bRedraw`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="resizepane"></a>CPaneContainer::ResizePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ResizePane(
    int nOffset,  
    CPane* pBar,  
    CPaneContainer* pContainer,  
    BOOL bHorz,  
    BOOL bLeftBar,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 [入力] `pBar`  
 [入力] `pContainer`  
 [入力] `bHorz`  
 [入力] `bLeftBar`  
 [入力] `hdwp`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="resizepartofpanecontainer"></a>CPaneContainer::ResizePartOfPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ResizePartOfPaneContainer(
    int nOffset,  
    BOOL bLeftPart,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 [入力] `bLeftPart`  
 [入力] `hdwp`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="serialize"></a>CPaneContainer::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpane"></a>CPaneContainer::SetPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPane(
    CDockablePane* pBar,  
    BOOL bLeft);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `bLeft`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpanecontainer"></a>CPaneContainer::SetPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPaneContainer(
    CPaneContainer* pContainer,  
    BOOL bLeft);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pContainer`  
 [入力] `bLeft`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpanedivider"></a>CPaneContainer::SetPaneDivider  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPaneDivider(CPaneDivider* pSlider);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pSlider`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setparentpanecontainer"></a>CPaneContainer::SetParentPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetParentPaneContainer(CPaneContainer* p);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `p`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setrecentpercent"></a>CPaneContainer::SetRecentPercent  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetRecentPercent(int nRecentPercent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nRecentPercent`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setupbyid"></a>CPaneContainer::SetUpByID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL SetUpByID(
    UINT nID,  
    CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 [入力] `pBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="storerecentdocksiteinfo"></a>CPaneContainer::StoreRecentDockSiteInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void StoreRecentDockSiteInfo(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="stretchpanecontainer"></a>CPaneContainer::StretchPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int StretchPaneContainer(
    int nOffset,  
    BOOL bStretchHorz,  
    BOOL bLeftBar,  
    BOOL bMoveSlider,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 [入力] `bStretchHorz`  
 [入力] `bLeftBar`  
 [入力] `bMoveSlider`  
 [入力] `hdwp`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [CPaneContainerManager クラス](../../mfc/reference/cpanecontainermanager-class.md)

