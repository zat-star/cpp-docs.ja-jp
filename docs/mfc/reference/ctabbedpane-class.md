---
title: "派生クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTabbedPane
- AFXTABBEDPANE/CTabbedPane
- AFXTABBEDPANE/CTabbedPane::DetachPane
- AFXTABBEDPANE/CTabbedPane::EnableTabAutoColor
- AFXTABBEDPANE/CTabbedPane::FloatTab
- AFXTABBEDPANE/CTabbedPane::GetTabArea
- AFXTABBEDPANE/CTabbedPane::GetTabWnd
- AFXTABBEDPANE/CTabbedPane::HasAutoHideMode
- AFXTABBEDPANE/CTabbedPane::IsTabLocationBottom
- AFXTABBEDPANE/CTabbedPane::ResetTabs
- AFXTABBEDPANE/CTabbedPane::SetTabAutoColors
- AFXTABBEDPANE/CTabbedPane::m_bTabsAlwaysTop
- AFXTABBEDPANE/CTabbedPane::m_pTabWndRTC
dev_langs:
- C++
helpviewer_keywords:
- CTabbedPane class
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
caps.latest.revision: 27
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
ms.openlocfilehash: 70377d6be8ef4ec957c7270e501022107d4b093c
ms.lasthandoff: 02/24/2017

---
# <a name="ctabbedpane-class"></a>派生クラス
切り離し可能なタブを持つペインの機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CTabbedPane : public CBaseTabbedPane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CTabbedPane::CTabbedPane`|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTabbedPane::DetachPane](#detachpane)|(上書き[CBaseTabbedPane::DetachPane](../../mfc/reference/cbasetabbedpane-class.md#detachpane))。|  
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|タブの色の自動設定を有効または無効にします。|  
|[CTabbedPane::FloatTab](#floattab)|現在ペインが切り離し可能なタブに存在する場合のみ、そのペインを切り離して表示します。 (上書き[CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab))。|  
|[CTabbedPane::GetTabArea](#gettabarea)|タブ付きウィンドウ内のタブ領域のサイズと位置を返します。|  
|[CTabbedPane::GetTabWnd](#gettabwnd)||  
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|タブ付きペインを AutoHide モードに切り替えられるかどうかを判断します。 (上書き[CBaseTabbedPane::HasAutoHideMode](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode))。|  
|[CTabbedPane::IsTabLocationBottom](#istablocationbottom)|タブがウィンドウの下部にあるかどうかを判断します。|  
|[CTabbedPane::ResetTabs](#resettabs)|すべてのタブ付きペインを既定の状態にリセットします。|  
|[CTabbedPane::SetTabAutoColors](#settabautocolors)|色の自動設定機能が有効になっているときに使用できるカスタム色の一覧を設定します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CTabbedPane::m_bTabsAlwaysTop](#m_btabsalwaystop)|アプリケーション内のタブの既定の場所。|  
|[CTabbedPane::m_pTabWndRTC](#m_ptabwndrtc)|カスタムの `CMFCTabCtrl` から派生したオブジェクトに関するランタイム クラス情報。|  
  
## <a name="remarks"></a>コメント  
 2 つ目のペインのキャプションをポイントして、ユーザーがあるペインを別のペインにアタッチすると、フレームワークにより自動的にこのクラスのインスタンスが作成されます。 -1 の ID を持つフレームワークにより作成される、すべてのタブ付きペイン。  
  
 Outlook スタイルのタブではなく通常のタブを指定するには、渡す、`AFX_CBRS_REGULAR_TABS`にスタイルを設定、 [CDockablePane::CreateEx](../../mfc/reference/cdockablepane-class.md#createex)メソッドです。  
  
 切り離し可能なタブを持つタブ付きペインを作成すると、フレームワークによってペインが自動的に破棄される可能性があるため、ポインターを格納しないでください。 タブ付きペインへのポインターを取得するには、`CBasePane::GetParentTabbedPane` メソッドを呼び出します。  
  
## <a name="example"></a>例  
 この例では `CTabbedPane` オブジェクトを作成します。 次に、 [CBaseTabbedPane::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab)をその他のタブをアタッチします。  
  
```  
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);

if (!pTabbededBar->Create (_T(""),
    this,
    CRect (0,
    0,
    200,
    200),  
    TRUE, 
 (UINT) -1,  
    WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |  
    WS_CLIPCHILDREN | CBRS_LEFT |    
    CBRS_FLOAT_MULTI)) 
{  
    TRACE0("Failed to create Solution Explorer bar\n");

    return FALSE;      // fail to create  
}  
 
pTabbededBar->AddTab (&m_wndClassView);
pTabbededBar->AddTab (&m_wndResourceView);

pTabbededBar->AddTab (&m_wndFileView);
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);

DockPane(pTabbededBar);
```  
  
## <a name="example"></a>例  
 タブ付きコントロール バー オブジェクトを作成する別の方法を使用して[CDockablePane::AttachToTabWnd](../../mfc/reference/cdockablepane-class.md#attachtotabwnd)します。 `AttachToTabWnd`メソッドは、タブ付きペインを設定したランタイム クラス情報を使用してオブジェクトを動的に作成[CDockablePane::SetTabbedPaneRTC](../../mfc/reference/cdockablepane-class.md#settabbedpanertc)します。  
  
 この例では、タブ付きペインを動的に作成し、2 つのタブをアタッチし、2 番目のタブを切り離し不可能にします。  
  
```  
DockPane(&m_wndClassView);

CTabbedPane* pTabbedBar = NULL;  
m_wndResourceView.AttachToTabWnd (&m_wndClassView,
    DM_SHOW,
    TRUE,  
 (CDockablePane**) &pTabbedBar);

m_wndFileView.AttachToTabWnd (pTabbedBar,
    DM_SHOW,
    TRUE,  
 (CDockablePane**) &pTabbedBar);

pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1,
    FALSE);
```  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [派生](../../mfc/reference/ctabbedpane-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxTabbedPane.h  
  
##  <a name="detachpane"></a>CTabbedPane::DetachPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DetachPane(
    CWnd* pBar,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `bHide`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enabletabautocolor"></a>CTabbedPane::EnableTabAutoColor  
 タブの色の自動設定を有効または無効にします。  
  
```  
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`タブの自動色分け表示を有効にするにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 有効にする、またはアプリケーション内のすべてのタブ付きペインでタブの自動的な色分けを無効にするには、この静的メソッドを使用します。 この機能を有効にすると、各タブは、独自の色で塗りつぶします。 呼び出すことによって、タブに色を使用する色の一覧を入手できます、 [CMFCBaseTabCtrl::GetAutoColors](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors)メソッドです。  
  
 タブに対して呼び出すことによって使用される色の一覧を指定する[CTabbedPane::SetTabAutoColors](#settabautocolors)します。  
  
 既定では、このオプションは無効です。  
  
##  <a name="floattab"></a>CTabbedPane::FloatTab  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `nTabID`  
 [入力] `dockMethod`  
 [入力] `bHide`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettabarea"></a>CTabbedPane::GetTabArea  
 タブ付きウィンドウに、サイズとタブ領域の位置を返します。  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rectTabAreaTop`  
 サイズと上部タブ領域の画面座標での位置が含まれています。  
  
 [出力] `rectTabAreaBottom`  
 サイズと下部にあるタブ領域の画面座標での位置が含まれています。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、ユーザーがドラッグされるペインをドッキングする方法を決定するには、このメソッドを呼び出します。 ユーザーは、ターゲット ウィンドウのタブ領域に、ウィンドウをドラッグ、フレームワークはターゲット ウィンドウの新しいタブとして追加しようとします。 それ以外の場合では&2; つのペインを分離するペインの区分線にウィンドウの新しいコンテナーを作成する [ターゲット] ウィンドウの横に、ウィンドウをドッキングしようとします。  
  
 このメソッドをオーバーライドして、 `CTabbedPane`-この動作を変更するクラスを派生します。  
  
##  <a name="gettabwnd"></a>CTabbedPane::GetTabWnd  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCTabCtrl* GetTabWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hasautohidemode"></a>CTabbedPane::HasAutoHideMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="istablocationbottom"></a>CTabbedPane::IsTabLocationBottom  
 タブがウィンドウの下部にあるかどうかを判断します。  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`タブ領域は、タブ付きウィンドウの下部にある場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_btabsalwaystop"></a>CTabbedPane::m_bTabsAlwaysTop  
 アプリケーション内のタブの既定の場所。  
  
```  
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;  
```  
  
### <a name="remarks"></a>コメント  
 この静的メンバーを設定`TRUE`タブ付きペインの上部に表示されるアプリケーションのすべての項目を強制的にします。  
  
 タブ付きウィンドウが作成される前に、この値を設定する必要があります。  
  
 既定値は `FALSE` です。  
  
##  <a name="m_ptabwndrtc"></a>CTabbedPane::m_pTabWndRTC  
 カスタムの `CMFCTabCtrl` から派生したオブジェクトに関するランタイム クラス情報。  
  
```  
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;  
```  
  
### <a name="remarks"></a>コメント  
 この静的メンバー変数のランタイム クラス情報へのポインターに設定、`CMFCTabCtrl`のタブ付きペイン内のカスタム タブ付きウィンドウを使用している場合は、オブジェクトを派生します。  
  
##  <a name="resettabs"></a>CTabbedPane::ResetTabs  
 すべてのタブ付きペインを既定の状態にリセットします。  
  
```  
static void ResetTabs();
```  
  
### <a name="remarks"></a>コメント  
 すべてのタブ付きペインは既定の状態を元に戻すには、このメソッドを呼び出します。 呼び出されると、このメソッドは、境界線のサイズとすべてのタブ付きペインの自動カラーの状態をリセットします。  
  
##  <a name="settabautocolors"></a>CTabbedPane::SetTabAutoColors  
 自動カラー機能が有効になっているときに使用されるカスタムの色の一覧を設定します。  
  
```  
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `arColors`  
 設定する色の配列が含まれています。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、自動カラー機能が有効になっているときに使用される色の一覧をカスタマイズできます。 これは静的関数であり、アプリケーションのすべてのタブ付きペインに影響を与えます。  
  
 使用[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)有効または自動カラー機能を無効にします。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)   
 [CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)   
 [あります。](../../mfc/reference/cmfcoutlookbar-class.md)

