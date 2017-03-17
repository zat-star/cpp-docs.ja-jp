---
title: "CPaneDivider クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaneDivider
- AFXPANEDIVIDER/CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::AddPaneContainer
- AFXPANEDIVIDER/CPaneDivider::AddPane
- AFXPANEDIVIDER/CPaneDivider::AddRecentPane
- AFXPANEDIVIDER/CPaneDivider::CalcExpectedDockedRect
- AFXPANEDIVIDER/CPaneDivider::CalcFixedLayout
- AFXPANEDIVIDER/CPaneDivider::CheckVisibility
- AFXPANEDIVIDER/CPaneDivider::CreateEx
- AFXPANEDIVIDER/CPaneDivider::DoesAllowDynInsertBefore
- AFXPANEDIVIDER/CPaneDivider::DoesContainFloatingPane
- AFXPANEDIVIDER/CPaneDivider::FindPaneContainer
- AFXPANEDIVIDER/CPaneDivider::FindTabbedPane
- AFXPANEDIVIDER/CPaneDivider::GetDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::GetFirstPane
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividerStyle
- AFXPANEDIVIDER/CPaneDivider::GetRootContainerRect
- AFXPANEDIVIDER/CPaneDivider::GetWidth
- AFXPANEDIVIDER/CPaneDivider::Init
- AFXPANEDIVIDER/CPaneDivider::InsertPane
- AFXPANEDIVIDER/CPaneDivider::IsAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::IsDefault
- AFXPANEDIVIDER/CPaneDivider::IsHorizontal
- AFXPANEDIVIDER/CPaneDivider::Move
- AFXPANEDIVIDER/CPaneDivider::NotifyAboutRelease
- AFXPANEDIVIDER/CPaneDivider::OnShowPane
- AFXPANEDIVIDER/CPaneDivider::ReleaseEmptyPaneContainers
- AFXPANEDIVIDER/CPaneDivider::RemovePane
- AFXPANEDIVIDER/CPaneDivider::ReplacePane
- AFXPANEDIVIDER/CPaneDivider::RepositionPanes
- AFXPANEDIVIDER/CPaneDivider::Serialize
- AFXPANEDIVIDER/CPaneDivider::SetAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::SetPaneContainerManager
- AFXPANEDIVIDER/CPaneDivider::ShowWindow
- AFXPANEDIVIDER/CPaneDivider::StoreRecentDockSiteInfo
- AFXPANEDIVIDER/CPaneDivider::StoreRecentTabRelatedInfo
- AFXPANEDIVIDER/CPaneDivider::GetPanes
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividers
- AFXPANEDIVIDER/CPaneDivider::m_nDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::m_pSliderRTC
dev_langs:
- C++
helpviewer_keywords:
- CPaneDivider class
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
caps.latest.revision: 25
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
ms.openlocfilehash: b1c6b8b608deb2c81a2a646345ee4020c27820e7
ms.lasthandoff: 02/24/2017

---
# <a name="cpanedivider-class"></a>CPaneDivider クラス
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 `CPaneDivider`クラスが&2; つのペインに分割し、ウィンドウの&2; つのグループに分割またはメイン フレーム ウィンドウのクライアント領域からグループを区切ます。  
  
## <a name="syntax"></a>構文  
  
```  
class CPaneDivider : public CBasePane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneDivider::CPaneDivider](#cpanedivider)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneDivider::AddPaneContainer](#addpanecontainer)||  
|[CPaneDivider::AddPane](#addpane)||  
|[CPaneDivider::AddRecentPane](#addrecentpane)||  
|[CPaneDivider::CalcExpectedDockedRect](#calcexpecteddockedrect)||  
|[CPaneDivider::CalcFixedLayout](#calcfixedlayout)|(上書き[CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout))。|  
|[CPaneDivider::CheckVisibility](#checkvisibility)||  
|[CPaneDivider::CreateEx](#createex)|(上書き[CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex))。|  
|[CPaneDivider::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(上書き[CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore))。|  
|[CPaneDivider::DoesContainFloatingPane](#doescontainfloatingpane)||  
|[CPaneDivider::FindPaneContainer](#findpanecontainer)||  
|[CPaneDivider::FindTabbedPane](#findtabbedpane)||  
|[CPaneDivider::GetDefaultWidth](#getdefaultwidth)||  
|[CPaneDivider::GetFirstPane](#getfirstpane)||  
|[CPaneDivider::GetPaneDividerStyle](#getpanedividerstyle)||  
|[CPaneDivider::GetRootContainerRect](#getrootcontainerrect)||  
|[CPaneDivider::GetWidth](#getwidth)||  
|[CPaneDivider::Init](#init)||  
|[CPaneDivider::InsertPane](#insertpane)||  
|[CPaneDivider::IsAutoHideMode](#isautohidemode)|(上書き[CBasePane::IsAutoHideMode](../../mfc/reference/cbasepane-class.md#isautohidemode))。|  
|[CPaneDivider::IsDefault](#isdefault)||  
|[CPaneDivider::IsHorizontal](#ishorizontal)|(上書き[CBasePane::IsHorizontal](../../mfc/reference/cbasepane-class.md#ishorizontal))。|  
|[CPaneDivider::Move](#move)||  
|[CPaneDivider::NotifyAboutRelease](#notifyaboutrelease)||  
|[CPaneDivider::OnShowPane](#onshowpane)||  
|[CPaneDivider::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)||  
|[CPaneDivider::RemovePane](#removepane)||  
|[CPaneDivider::ReplacePane](#replacepane)||  
|[CPaneDivider::RepositionPanes](#repositionpanes)||  
|[CPaneDivider::Serialize](#serialize)|(`CBasePane::Serialize` をオーバーライドします)。|  
|[CPaneDivider::SetAutoHideMode](#setautohidemode)||  
|[CPaneDivider::SetPaneContainerManager](#setpanecontainermanager)||  
|[CPaneDivider::ShowWindow](#showwindow)||  
|[CPaneDivider::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneDivider::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneDivider::GetPanes](#getpanes)|存在するペインのリストを返す、 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)します。 このメソッドは、既定ペインの区分線に対してのみ呼び出す必要があります。|  
|[CPaneDivider::GetPaneDividers](#getpanedividers)|配置されているペイン分割バーのリストを返す、 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)します。 このメソッドは、既定ペインの区分線に対してのみ呼び出す必要があります。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneDivider::m_nDefaultWidth](#m_ndefaultwidth)|アプリケーション内のすべてのペイン区分線のピクセルで、既定の幅を指定します。|  
|[CPaneDivider::m_pSliderRTC](#m_psliderrtc)|ランタイム クラス情報へのポインターを保持する`CPaneDivider`-派生オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 フレームワークを作成`CPaneDivider`ペインをドッキングしたときに自動的にオブジェクトです。  
  
 ペイン分割バーの&2; 種類があります。  
  
-   ウィンドウのグループがメイン フレーム ウィンドウの端にドッキングされているときは、既定のウィンドウの区分線が作成されます。 既定ペインの区分線へのポインターを保持して、 [CPaneContainerManager クラス](../../mfc/reference/cpanecontainermanager-class.md)し、ウィンドウのグループでほとんどの操作をリダイレクト (など、ウィンドウのサイズ変更、または別のドッキング ペインまたはコンテナー) コンテナー マネージャーにします。 各ドッキング ペインでは、その既定ペインの区分線へのポインターを保持します。  
  
-   標準のペインの区分線は、コンテナー内の&2; つのペインを分割するだけです。 詳細については、次を参照してください。 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)します。  
  
## <a name="example"></a>例  
 `CWorkspaceBar` オブジェクトから `CPaneDivider` オブジェクトを取得する方法を次の例に示します。 このコード スニペットの一部である、 [MDI タブのデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#5;](../../mfc/reference/codesnippet/cpp/cpanedivider-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPaneDivider](../../mfc/reference/cpanedivider-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxPaneDivider.h  
  
##  <a name="setautohidemode"></a>CPaneDivider::SetAutoHideMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetAutoHideMode(BOOL bMode);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bMode`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpanecontainermanager"></a>CPaneDivider::SetPaneContainerManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPaneContainerManager(CPaneContainerManager* p);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `p`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addpane"></a>CPaneDivider::AddPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void AddPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addpanecontainer"></a>CPaneDivider::AddPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AddPaneContainer(
    CPaneContainerManager& barContainerManager,  
    BOOL bOuterEdge);

 
virtual BOOL AddPaneContainer(
    CDockablePane* pTargetBar,  
    CPaneContainerManager& barContainerManager,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `barContainerManager`  
 [入力] `bOuterEdge`  
 [入力] `pTargetBar`  
 [入力] `dwAlignment`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addrecentpane"></a>CPaneDivider::AddRecentPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CDockablePane* AddRecentPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="calcexpecteddockedrect"></a>CPaneDivider::CalcExpectedDockedRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 [入力] `ptMouse`  
 [入力] `rectResult`  
 [入力] `bDrawTab`  
 [入力] `ppTargetBar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="calcfixedlayout"></a>CPaneDivider::CalcFixedLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
  
##  <a name="checkvisibility"></a>CPaneDivider::CheckVisibility  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CheckVisibility();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="cpanedivider"></a>CPaneDivider::CPaneDivider  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CPaneDivider();

 
CPaneDivider(
    BOOL bDefaultSlider,  
    CWnd* pParent = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDefaultSlider`  
 [入力] `pParent`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="createex"></a>CPaneDivider::CreateEx  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwStyleEx`  
 [入力] `dwStyle`  
 [入力] `rect`  
 [入力] `pParentWnd`  
 [入力] `nID`  
 [入力] `pContext`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="doesallowdyninsertbefore"></a>CPaneDivider::DoesAllowDynInsertBefore  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="doescontainfloatingpane"></a>CPaneDivider::DoesContainFloatingPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DoesContainFloatingPane();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="findpanecontainer"></a>CPaneDivider::FindPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,  
    BOOL& bLeftBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `bLeftBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="findtabbedpane"></a>CPaneDivider::FindTabbedPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CDockablePane* FindTabbedPane(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdefaultwidth"></a>CPaneDivider::GetDefaultWidth  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static int __stdcall GetDefaultWidth();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getfirstpane"></a>CPaneDivider::GetFirstPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CBasePane* GetFirstPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpanedividers"></a>CPaneDivider::GetPaneDividers  
 配置されているペイン分割バーのリストを返す、 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)します。 このメソッドは、既定ペインの区分線に対してのみ呼び出す必要があります。  
  
```  
void GetPaneDividers(CObList& lstSliders);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `lstSliders`  
 ウィンドウのコンテナーに存在するペイン分割バーの一覧が含まれています。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、既定のペイン分割バーのみを呼び出す必要があります。 既定ペインの区分線は、ウィンドウ全体のコンテナーのサイズを変更している区分線です。  
  
##  <a name="getpanedividerstyle"></a>CPaneDivider::GetPaneDividerStyle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
DWORD GetPaneDividerStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpanes"></a>CPaneDivider::GetPanes  
 存在するペインのリストを返す、 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)します。 このメソッドは、既定のペイン分割バーを取得する場合のみ呼び出す必要があります。  
  
```  
void GetPanes(CObList& lstBars);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `lstBars`  
 ウィンドウのコンテナーに格納されているペインのリストが含まれています。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、既定のペイン分割バーのみを呼び出す必要があります。 既定ペインの区分線は、ウィンドウ全体のコンテナーのサイズを変更している区分線です。  
  
##  <a name="getrootcontainerrect"></a>CPaneDivider::GetRootContainerRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetRootContainerRect();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getwidth"></a>CPaneDivider::GetWidth  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="init"></a>CPaneDivider::Init  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Init(
    BOOL bDefaultSlider = FALSE,  
    CWnd* pParent = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDefaultSlider`  
 [入力] `pParent`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="insertpane"></a>CPaneDivider::InsertPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL InsertPane(
    CDockablePane* pBarToInsert,  
    CDockablePane* pTargetBar,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBarToInsert`  
 [入力] `pTargetBar`  
 [入力] `dwAlignment`  
 [入力] `lpRect`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isautohidemode"></a>CPaneDivider::IsAutoHideMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isdefault"></a>CPaneDivider::IsDefault  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsDefault() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ishorizontal"></a>CPaneDivider::IsHorizontal  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_ndefaultwidth"></a>CPaneDivider::m_nDefaultWidth  
 アプリケーション内のすべてのペイン区分線のピクセル単位の既定の幅を指定します。  
  
```  
AFX_IMPORT_DATA static int m_nDefaultWidth;  
```  
  
##  <a name="move"></a>CPaneDivider::Move  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Move(
    CPoint& ptOffset,  
    BOOL bAdjustLayout = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ptOffset`  
 [入力] `bAdjustLayout`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_psliderrtc"></a>CPaneDivider::m_pSliderRTC  
 ランタイム クラス情報へのポインターを保持する`CPaneDivider`-派生オブジェクト。  
  
```  
AFX_IMPORT_DATA static CRuntimeClass* m_pSliderRTC;  
```  
  
### <a name="remarks"></a>コメント  
 カスタムのウィンドウの区分線を作成する場合は、このメンバー変数を設定します。 これはにより、ウィンドウが描画されると、ペイン分割バーを作成するフレームワークです。  
  
### <a name="example"></a>例  
 次の例では、設定する方法、`m_pSliderRTC`メンバー変数。  
  
```  
class CMySplitter : public CPaneDivider  
{  
...  
};  
 
CPaneDivider::m_pSliderRTC = RUNTIME_CLASS(CMySpliter);
```  
  
##  <a name="notifyaboutrelease"></a>CPaneDivider::NotifyAboutRelease  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void NotifyAboutRelease();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshowpane"></a>CPaneDivider::OnShowPane  
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
  
##  <a name="releaseemptypanecontainers"></a>CPaneDivider::ReleaseEmptyPaneContainers  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ReleaseEmptyPaneContainers();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removepane"></a>CPaneDivider::RemovePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RemovePane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="replacepane"></a>CPaneDivider::ReplacePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL ReplacePane(
    CDockablePane* pBarToReplace,  
    CDockablePane* pBarToReplaceWith);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBarToReplace`  
 [入力] `pBarToReplaceWith`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="repositionpanes"></a>CPaneDivider::RepositionPanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RepositionPanes(
    CRect& rectNew,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectNew`  
 [入力] `hdwp`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="serialize"></a>CPaneDivider::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="showwindow"></a>CPaneDivider::ShowWindow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nCmdShow`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="storerecentdocksiteinfo"></a>CPaneDivider::StoreRecentDockSiteInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void StoreRecentDockSiteInfo(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="storerecenttabrelatedinfo"></a>CPaneDivider::StoreRecentTabRelatedInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void StoreRecentTabRelatedInfo(
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
 [CPaneContainerManager クラス](../../mfc/reference/cpanecontainermanager-class.md)   
 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)   
 [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)   
 [CBasePane クラス](../../mfc/reference/cbasepane-class.md)

