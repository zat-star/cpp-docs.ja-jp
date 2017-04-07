---
title: "あります。Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar::AllowDestroyEmptyTabbedPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanAcceptPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanSetCaptionTextToTabName
- AFXOUTLOOKBAR/CMFCOutlookBar::Create
- AFXOUTLOOKBAR/CMFCOutlookBar::CreateCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::DoesAllowDynInsertBefore
- AFXOUTLOOKBAR/CMFCOutlookBar::FloatTab
- AFXOUTLOOKBAR/CMFCOutlookBar::GetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::GetTabArea
- AFXOUTLOOKBAR/CMFCOutlookBar::IsMode2003
- AFXOUTLOOKBAR/CMFCOutlookBar::OnAfterAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnBeforeAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnScroll
- AFXOUTLOOKBAR/CMFCOutlookBar::RemoveCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::SetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::SetMode2003
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBar class
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
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
ms.openlocfilehash: ff58cf786e4979d64aa2b5d7ad4d1a32b96bec3d
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar クラス
Microsoft Outlook 2000 または Outlook 2003 の **ナビゲーション ウィンドウ** と同じ外観を持つタブ付きペインです。 `CMFCOutlookBar`オブジェクトを含む、 [CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)オブジェクトと一連のタブです。 タブには、いずれかを指定できます[CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)オブジェクトまたは`CWnd`の派生クラスのオブジェクト。 ユーザーに対しては、Outlook バーは一連のボタンおよび表示領域として表示されます。 ユーザーがボタンをクリックすると、対応するコントロールまたはボタン ペインが表示されます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCOutlookBar : public CBaseTabbedPane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCOutlookBar::CMFCOutlookBar`|既定のコンストラクター|  
|`CMFCOutlookBar::~CMFCOutlookBar`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|空のタブ付きペインを破壊することができるかどうかを指定します。 (上書き[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane))。|  
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|別のペインを Outlook バー ペインをドッキングできるかどうかを決定します。 (CDockablePane::CanAcceptPane を上書きします)。|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|タブ付きペインのキャプションがアクティブなタブとして同じテキストを表示するかどうかを決定します。 (上書き[CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname))。|  
|[CMFCOutlookBar::Create](#create)|Outlook バー コントロールを作成します。|  
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|カスタムの Outlook バー タブを作成します。|  
|`CMFCOutlookBar::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|ユーザーが Outlook バーの外側にあるコントロール バーをドッキングするかどうかを決定します。|  
|[CMFCOutlookBar::FloatTab](#floattab)|現在ペインが切り離し可能なタブに存在する場合のみ、そのペインを切り離して表示します。 (上書き[CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab))。|  
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Outlook バーのボタンのテキストのフォントを返します。|  
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Outlook バーのサイズとタブ領域の位置を返します。 (上書き[CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea))。|  
|`CMFCOutlookBar::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCOutlookBar::IsMode2003](#ismode2003)|(「解説」を参照してください) Microsoft Office Outlook 2003 の Outlook バー動作を模倣するかどうかを決定します。|  
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|によって呼び出される[CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab)アニメーションを使用してアクティブなタブが設定された後です。|  
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|によって呼び出される[CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab)タブの前にページがアニメーションを使用してアクティブなタブとして設定します。|  
|[CMFCOutlookBar::OnScroll](#onscroll)|Outlook バーを上または下にスクロールする場合に、フレームワークによって呼び出されます。|  
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|カスタムの Outlook バー タブを削除します。|  
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Outlook バーのボタンのテキストのフォントを設定します。|  
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Outlook バーの動作を模倣する Outlook 2003 (「解説」を参照してください) かどうかを指定します。|  
  
## <a name="remarks"></a>コメント  
 Outlook バーの例は、次を参照してください。、 [OutlookDemo サンプル: MFC OutlookDemo アプリケーション](../../visual-cpp-samples.md)します。  
  
## <a name="implementing-the-outlook-bar"></a>Outlook バーを実装します。  
 アプリケーションで、`CMFCOutlookBar` コントロールを使用するには、次の手順に従います。  
  
1.  `CMFCOutlookBar` オブジェクトをメイン フレーム ウィンドウ クラスに埋め込みます。  
  
 ```  
    class CMainFrame : public CMDIFrameWnd  
 { ...  
    CMFCOutlookBar m_wndOutlookBar;  
    CMFCOutlookBarPane m_wndOutlookPane;  
 ... };  
 ```  
2.  処理するときに、 `WM_CREATE` 、メインフレームの呼び出し内のメッセージ、 [CMFCOutlookBar::Create](#create) Outlook バー タブ コントロールを作成します。  
  
 ```  
    m_wndOutlookBar.Create (_T("Shortcuts"),
    this,
    CRect (0,
    0,
    100,
    100),
    ID_VIEW_OUTLOOKBAR,
    WS_CHILD | WS_VISIBLE | CBRS_LEFT);

 ```  
3.  基になるへのポインターを取得`CMFCOutlookBarTabCtrl`を使用して[CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow)します。  
  
 ```  
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();

 ```  
4.  作成、 [CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)ボタンのある各タブのオブジェクト。  
  
 ```  
    m_wndOutlookPane.Create (&m_wndOutlookBar,
    AFX_DEFAULT_TOOLBAR_STYLE,
    ID_OUTLOOK_PANE_GENERAL,
    AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);
*// make the Outlook pane detachable (enable docking)  
    m_wndOutlookPane.EnableDocking (CBRS_ALIGN_ANY);
*// add buttons  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_MAINFRAME), "About",
    ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON), "Open",
    ID_FILE_OPEN);

 ```  
5.  呼び出す[CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)をそれぞれの新しいタブを追加します。 設定、`bDetachable`パラメーターを`FALSE`非取り外し可能なページを作成します。 または、使用して[CMFCOutlookBarTabCtrl::AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol)取り外し可能なページを追加します。  
  
 ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1,
    TRUE);

 ```  
6.  追加する、 `CWnd`-派生コントロール (たとえば、 [CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md))、タブとコントロールを作成して呼び出し[CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)を Outlook バーに追加します。  
  
> [!NOTE]
>  それぞれに固有のコントロール Id を使用する必要があります[CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)オブジェクトおよび各`CWnd`-派生オブジェクト。  
  
 動的に追加または実行時に新しいページを削除する、 [CMFCOutlookBar::CreateCustomPage](#createcustompage)と[CMFCOutlookBar::RemoveCustomPage](#removecustompage)します。  
  
## <a name="outlook-2003-mode"></a>Outlook 2003 のモード  
 Outlook 2003 モードでは、タブのボタンは、Outlook バー ペインの下部に配置されます。 ボタンを表示する十分な領域がない場合は、これらのウィンドウの下部にあるツールバーのような領域にアイコンとして表示されます。  
  
 使用[CMFCOutlookBar::SetMode2003](#setmode2003) Outlook 2003 モードを有効にします。 使用[CMFCOutlookBarTabCtrl::SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist)を Outlook バーの下に表示されるアイコンを含むビットマップを設定します。 ビットマップのアイコンは、タブ インデックス順する必要があります。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [あります。](../../mfc/reference/cmfcoutlookbar-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxoutlookbar.h  
  
##  <a name="allowdestroyemptytabbedpane"></a>CMFCOutlookBar::AllowDestroyEmptyTabbedPane  
 空のタブ付きペインを破壊することができるかどうかを指定します。  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は空のタブ付きペインを破壊することができます。それ以外の場合、`FALSE`です。 既定の実装を常に`TRUE`します。  
  
### <a name="remarks"></a>コメント  
 空のタブ付きペインを破壊することはできません、framework 非表示になりますが代わりにします。  
  
##  <a name="canacceptpane"></a>CMFCOutlookBar::CanAcceptPane  
 別のペインを Outlook バー ペインをドッキングできるかどうかを決定します。  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 このウィンドウにドッキングされる別のウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`別のペインを Outlook バー ペインをドッキングできる場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 Outlook バーが Outlook 2003 のモードの場合は、ドッキングはサポートされないので、戻り値は`FALSE`です。  
  
 場合、`pBar`パラメーターは`NULL`、このメソッドが戻る`FALSE`します。  
  
 このメソッドが基本メソッドとは動作それ以外の場合、 [CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane)Outlook バーで別の Outlook バー上にドッキングすることも有効にドッキングが有効でない場合でも点が異なります。  
  
##  <a name="cansetcaptiontexttotabname"></a>CMFCOutlookBar::CanSetCaptionTextToTabName  
 タブ付きペインのキャプションがアクティブなタブとして同じテキストを表示するかどうかを決定します。  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`Outlook ウィンドウのキャプション バーが自動的にアクティブなタブのテキストに設定されている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 使用[CBaseTabbedPane::EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname)を有効にするか、この機能を無効にします。  
  
 Outlook 2003 モードでは、この設定は常に有効にします。  
  
##  <a name="create"></a>CMFCOutlookBar::Create  
 Outlook バー コントロールを作成します。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwControlBarStyle=AFX_CBRS_RESIZE,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszCaption`  
 ウィンドウのキャプションを指定します。  
  
 [入力] `pParentWnd`  
 親ウィンドウへのポインターを指定します。 NULL は指定できません。  
  
 [入力] `rect`  
 Outlook バーのサイズと位置 (ピクセル単位) を指定します。  
  
 [入力] `nID`  
 コントロール ID を指定します その他のコントロール、アプリケーションで使用される Id と異なる名前にする必要があります。  
  
 [入力] `dwStyle`  
 目的のコントロール バーのスタイルを指定します。 指定できる値は、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/window-styles.md)します。  
  
 [入力] `dwControlBarStyle`  
 特殊なライブラリで定義されたスタイルを指定します。  
  
 [入力] `pContext`  
 コンテキストを作成します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CMFCOutlookBar`&2; つのステップ内のオブジェクト。 まず、コンス トラクターを呼び出します`Create`、outlook バー コントロールを作成およびそれにアタッチする、`CMFCOutlookBar`オブジェクトです。  
  
 参照してください[CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)によって指定される使用可能なライブラリで定義されたスタイルの一覧については`dwControlBarStyle`です。  
  
### <a name="example"></a>例  
 次の例では、使用して、`Create`のメソッド、`CMFCOutlookBar`クラスです。 このコード スニペットの一部である、 [Outlook の複数のビューのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews&#1;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews&#2;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]  
  
##  <a name="createcustompage"></a>CMFCOutlookBar::CreateCustomPage  
 カスタムの Outlook バー タブを作成します。  
  
```  
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,  
    BOOL bActivatePage=TRUE,  
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,  
    BOOL bEnableTextLabels=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszPageName`  
 ページのラベル。  
  
 [入力] `bActivatePage`  
 場合`TRUE`ページが作成時にアクティブになります。  
  
 [入力] `dwEnabledDocking`  
 ページがデタッチされている場合に有効になっているドッキング辺を指定する cbrs_align _ フラグの組み合わせ。  
  
 [入力] `bEnableTextLabels`  
 場合`TRUE`ページ上に存在するボタンのテキスト ラベルを有効にします。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたページへのポインターまたは`NULL`場合は、作成に失敗しました。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、ユーザーがカスタム Outlook バー ページを作成できるようにします。 アプリケーションごとに最大 100 個のページを作成することができます。 ページのコントロール Id は、一部が 0xF000 から起動します。 カスタムの Outlook バー ページの合計数が 100 を超えた場合、作成に失敗します。  
  
 使用[CMFCOutlookBar::RemoveCustomPage](#removecustompage)カスタム ページを削除します。  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCOutlookBar::DoesAllowDynInsertBefore  
 ユーザーが Outlook バーの外側にあるウィンドウをドッキングするかどうかを指定します。  
  
```  
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、`FALSE` が返されます。  
  
### <a name="remarks"></a>コメント  
 フレームワークによって、`DoesAllowDynInsertBefore`メソッドの動的なペインをドッキングする場所を探すときにします。 関数が返した場合`FALSE`フレームワークは、ウィンドウの外側のエッジの動的ペインのドッキングを許可しません。  
  
 通常、静的な非フローティング コントロールとして Outlook バーを作成します。 この関数を派生クラスでオーバーライドし、返す`TRUE`この動作を変更します。  
  
> [!NOTE]
>  動的ペインをドッキングするときに、ドッキングされた静的ペインの状況を確認するため、できる限り静的ペインの後動的ペインをドッキングする必要があります。  
  
##  <a name="floattab"></a>CMFCOutlookBar::FloatTab  
 ペインをフローティングするにはなります。  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 浮動小数点数には、ウィンドウへのポインター。  
  
 [入力] `nTabID`  
 浮動小数点 タブの&0; から始まるインデックス。  
  
 [入力] `dockMethod`  
 ペインをフローティングの作成に使用する方法を指定します。  詳細については、次を参照してください。 [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)します。  
  
 [入力] `bHide`  
 `TRUE`フローティングする前に、ウィンドウを非表示にするにはそれ以外の場合、`FALSE`です。 このメソッドの基本クラスのバージョンとは異なり、このパラメーターは、既定値がありません。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインをフローティング状態の場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドはのように、 [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)する点を除いて、float を Outlook バー コントロールの最後の残りのタブが有効にしません。  
  
##  <a name="getbuttonsfont"></a>CMFCOutlookBar::GetButtonsFont  
 ページで、Outlook バーのボタン タブのテキストのフォントを返します。  
  
```  
CFont* GetButtonsFont() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ページ ボタン タブ バー Outlook にテキストを表示するために使用されるフォント オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数を使用して、Outlook ページ ボタン タブ上のテキストを表示するために使用するフォントを取得します。 呼び出すことによって、フォントを設定する[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)します。  
  
##  <a name="gettabarea"></a>CMFCOutlookBar::GetTabArea  
 サイズと、Outlook バー上のタブ領域の位置を決定します。  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rectTabAreaTop`  
 関数が戻るときのサイズと位置 (クライアント座標) で、上部タブ領域が含まれます。  
  
 [出力] `rectTabAreaBottom`  
 関数が戻るときのサイズと位置 (クライアント座標) を下部にあるタブ領域が含まれています。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、ターゲット ウィンドウをドッキングの種類を確認するには、このメソッドを呼び出します。 フレームワークでは、ユーザーがターゲット ウィンドウのタブ領域にドッキングするウィンドウをドラッグすることを判断した場合、ターゲット ウィンドウの新しいタブとして最初にウィンドウを追加しようとします。 それ以外の場合、最初のウィンドウを適切なターゲット ウィンドウの辺に固定しようとします。 フレームワークは、その他のドッキング ウィンドウに対応するスライダーを新しいコンテナーを作成します。  
  
 既定の実装`GetTabArea`Outlook バーは、静的である場合は、Outlook バーの全体のクライアント領域を返します、Outlook バーがフローティングことはできません。 それ以外の場合、ページのボタンが Outlook バー コントロールの上下には、領域を返します。  
  
 このメソッドから派生したクラスでオーバーライド`CMFCOutlookBar`この動作を変更します。  
  
##  <a name="ismode2003"></a>CMFCOutlookBar::IsMode2003  
 Microsoft Office Outlook 2003 の Outlook バーの動作を模倣するかどうかを指定します。  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Outlook バーは、Microsoft Office 2003 モードで実行している場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用してこのモードを有効にすることができます[CMFCOutlookBar::SetMode2003](#setmode2003)します。  
  
##  <a name="onafteranimation"></a>CMFCOutlookBar::OnAfterAnimation  
 によって呼び出される[CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab)アニメーションを使用してアクティブなタブが設定された後です。  
  
```  
virtual void OnAfterAnimation(int nPage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nPage`  
 アクティブなようになっているタブ ページの&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 アクティブなタブの設定の視覚的効果は、アニメーションが有効にするかどうかによって異なります。 詳細については、次を参照してください。 [CMFCOutlookBarTabCtrl::EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation)します。  
  
##  <a name="onbeforeanimation"></a>CMFCOutlookBar::OnBeforeAnimation  
 によって呼び出される[CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab)タブの前にページがアニメーションを使用してアクティブなタブとして設定します。  
  
```  
virtual BOOL OnBeforeAnimation(int nPage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nPage`  
 アクティブな設定しようとして、タブ ページの&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`アニメーションを新しいアクティブなタブの設定に使用する場合、または`FALSE`アニメーションを無効にする場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onscroll"></a>CMFCOutlookBar::OnScroll  
 Outlook バーを上または下にスクロールする場合に、フレームワークによって呼び出されます。  
  
```  
virtual void OnScroll(BOOL bDown);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDown`  
 `TRUE`Outlook バーのスクロール ダウンしている場合または`FALSE`場合は、上にスクロールすることができます。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removecustompage"></a>CMFCOutlookBar::RemoveCustomPage  
 カスタムの Outlook バー タブ ページを削除します。  
  
```  
BOOL RemoveCustomPage(
    UINT uiPage,  
    CMFCOutlookBarTabCtrl* pTargetWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiPage`  
 Outlook の親ウィンドウで、ページの&0; から始まるインデックス。  
  
 [入力] `pTargetWnd`  
 Outlook の親ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 カスタムのページが正常に削除されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 カスタム ページを削除するには、この関数を呼び出します。 ページが削除されたときにそのコントロールの ID が有効な Id のプールに返されます。  
  
 ポインターを提供する必要があります[CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)現在削除するページが存在するオブジェクトします。 ユーザーは別の Outlook バーの間取り外し可能なページを移動することができますが、カスタム ページに関する情報を呼び出すの Outlook バー オブジェクト内に存在[CMFCOutlookBar::CreateCustomPage](#createcustompage)します。  
  
 使用[CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) Outlook ウィンドウへのポインターを取得します。  
  
##  <a name="setbuttonsfont"></a>CMFCOutlookBar::SetButtonsFont  
 Outlook バーのボタンのテキストのフォントを設定します。  
  
```  
void SetButtonsFont(
    CFont* pFont,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pFont`  
 新しいフォントを指定します。  
  
 [入力] `bRedraw`  
 場合`TRUE`、Outlook バーが再描画されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、outlook のタブ ページのボタンに表示されるテキストのフォントを設定できます。  
  
##  <a name="setmode2003"></a>CMFCOutlookBar::SetMode2003  
 Outlook 2003 の Outlook バーの動作を模倣するかどうかを指定します。  
  
```  
void SetMode2003(BOOL bMode2003=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bMode2003`  
 TRUE の場合、Office 2003 のモードを有効にします。  
  
### <a name="remarks"></a>コメント  
 有効にするか、Office 2003 のモードを無効にするには、この関数を使用します。 このモードでは、Outlook バーは、カスタム ボタンを含む追加のツールバーにあります。 Outlook バーの動作は、Microsoft Office 2003 Outlook バーの動作に準拠します。  
  
 既定では、このモードは無効です。  
  
> [!NOTE]
>  この関数は、前に呼び出す必要があります[CMFCOutlookBar::Create](#create)します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)

