---
title: "CDockablePane クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockablePane
- AFXDOCKABLEPANE/CDockablePane
- AFXDOCKABLEPANE/CDockablePane::CDockablePane
- AFXDOCKABLEPANE/CDockablePane::AttachToTabWnd
- AFXDOCKABLEPANE/CDockablePane::CalcFixedLayout
- AFXDOCKABLEPANE/CDockablePane::CanAcceptMiniFrame
- AFXDOCKABLEPANE/CDockablePane::CanAcceptPane
- AFXDOCKABLEPANE/CDockablePane::CanAutoHide
- AFXDOCKABLEPANE/CDockablePane::CanBeAttached
- AFXDOCKABLEPANE/CDockablePane::ConvertToTabbedDocument
- AFXDOCKABLEPANE/CDockablePane::CopyState
- AFXDOCKABLEPANE/CDockablePane::Create
- AFXDOCKABLEPANE/CDockablePane::CreateDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::CreateEx
- AFXDOCKABLEPANE/CDockablePane::CreateTabbedPane
- AFXDOCKABLEPANE/CDockablePane::DockPaneContainer
- AFXDOCKABLEPANE/CDockablePane::DockPaneStandard
- AFXDOCKABLEPANE/CDockablePane::DockToRecentPos
- AFXDOCKABLEPANE/CDockablePane::DockToWindow
- AFXDOCKABLEPANE/CDockablePane::EnableAutohideAll
- AFXDOCKABLEPANE/CDockablePane::EnableGripper
- AFXDOCKABLEPANE/CDockablePane::GetAHRestoredRect
- AFXDOCKABLEPANE/CDockablePane::GetAHSlideMode
- AFXDOCKABLEPANE/CDockablePane::GetCaptionHeight
- AFXDOCKABLEPANE/CDockablePane::GetDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::GetDockingStatus
- AFXDOCKABLEPANE/CDockablePane::GetDragSensitivity
- AFXDOCKABLEPANE/CDockablePane::GetLastPercentInPaneContainer
- AFXDOCKABLEPANE/CDockablePane::GetTabArea
- AFXDOCKABLEPANE/CDockablePane::GetTabbedPaneRTC
- AFXDOCKABLEPANE/CDockablePane::HasAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::HitTest
- AFXDOCKABLEPANE/CDockablePane::IsAutohideAllEnabled
- AFXDOCKABLEPANE/CDockablePane::IsAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::IsDocked
- AFXDOCKABLEPANE/CDockablePane::IsHideInAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::IsInFloatingMultiPaneFrameWnd
- AFXDOCKABLEPANE/CDockablePane::IsResizable
- AFXDOCKABLEPANE/CDockablePane::IsTabLocationBottom
- AFXDOCKABLEPANE/CDockablePane::IsTracked
- AFXDOCKABLEPANE/CDockablePane::IsVisible
- AFXDOCKABLEPANE/CDockablePane::OnAfterChangeParent
- AFXDOCKABLEPANE/CDockablePane::OnAfterDockFromMiniFrame
- AFXDOCKABLEPANE/CDockablePane::OnBeforeChangeParent
- AFXDOCKABLEPANE/CDockablePane::OnBeforeFloat
- AFXDOCKABLEPANE/CDockablePane::RemoveFromDefaultPaneDividier
- AFXDOCKABLEPANE/CDockablePane::ReplacePane
- AFXDOCKABLEPANE/CDockablePane::RestoreDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::SetAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::SetAutoHideParents
- AFXDOCKABLEPANE/CDockablePane::SetLastPercentInPaneContainer
- AFXDOCKABLEPANE/CDockablePane::SetRestoredDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::SetTabbedPaneRTC
- AFXDOCKABLEPANE/CDockablePane::ShowPane
- AFXDOCKABLEPANE/CDockablePane::Slide
- AFXDOCKABLEPANE/CDockablePane::ToggleAutoHide
- AFXDOCKABLEPANE/CDockablePane::UndockPane
- AFXDOCKABLEPANE/CDockablePane::CheckAutoHideCondition
- AFXDOCKABLEPANE/CDockablePane::CheckStopSlideCondition
- AFXDOCKABLEPANE/CDockablePane::DrawCaption
- AFXDOCKABLEPANE/CDockablePane::OnPressButtons
- AFXDOCKABLEPANE/CDockablePane::OnSlide
- AFXDOCKABLEPANE/CDockablePane::m_bDisableAnimation
- AFXDOCKABLEPANE/CDockablePane::m_bHideInAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::m_nSlideSteps
dev_langs:
- C++
helpviewer_keywords:
- CDockablePane class
ms.assetid: e2495f4c-765f-48f9-a2e2-e45e47608d91
caps.latest.revision: 34
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: dea1f1ce66c0e9bedbe83109ab62055a4af2ebce
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdockablepane-class"></a>CDockablePane Class
ドッキング サイトにドッキングできる、またはタブ付きペインに含めることができるペインを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDockablePane : public CPane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDockablePane::CDockablePane](#cdockablepane)|`CDockablePane` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDockablePane::AttachToTabWnd](#attachtotabwnd)|別のペインに、ウィンドウにアタッチします。 これは、タブ付きペインを作成します。|  
|[CDockablePane::CalcFixedLayout](#calcfixedlayout)|ペインの四角形のサイズを返します。|  
|[CDockablePane::CanAcceptMiniFrame](#canacceptminiframe)|指定したミニフレームをウィンドウにドッキングできるかどうかを決定します。|  
|[CDockablePane::CanAcceptPane](#canacceptpane)|現在のウィンドウに別のペインをドッキングできるかどうかを決定します。|  
|[CDockablePane::CanAutoHide](#canautohide)|ペインが自動非表示モードをサポートするかどうかを決定します。 (上書き[CBasePane::CanAutoHide](../../mfc/reference/cbasepane-class.md#canautohide))。|  
|[CDockablePane::CanBeAttached](#canbeattached)|現在のウィンドウを別のウィンドウにドッキングできるかどうかを決定します。|  
|[CDockablePane::ConvertToTabbedDocument](#converttotabbeddocument)|1 つまたは複数のドッキング可能ペインを MDI タブ付きドキュメントに変換します。|  
|[CDockablePane::CopyState](#copystate)|ドッキング可能ペインの状態をコピーします。|  
|[CDockablePane::Create](#create)|Windows コントロールを作成し、それをアタッチ、`CDockablePane`オブジェクトです。|  
|[CDockablePane::CreateDefaultPaneDivider](#createdefaultpanedivider)|フレーム ウィンドウにドッキングされているように、ウィンドウの既定の区分線を作成します。|  
|[CDockablePane::CreateEx](#createex)|Windows コントロールを作成し、それをアタッチ、`CDockablePane`オブジェクトです。|  
|[CDockablePane::CreateTabbedPane](#createtabbedpane)|現在のウィンドウからタブ付きペインを作成します。|  
|[CDockablePane::DockPaneContainer](#dockpanecontainer)|ウィンドウに、コンテナーにドッキングします。|  
|[CDockablePane::DockPaneStandard](#dockpanestandard)|アウトライン (標準) のドッキングを使用して、ウィンドウをドッキングします。|  
|`CDockablePane::DockToFrameWindow`|内部的に使用します。 ペインをドッキングするには使用[CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane)または[CDockablePane::DockToWindow](#docktowindow)します。|  
|[CDockablePane::DockToRecentPos](#docktorecentpos)|ウィンドウを格納されている最新のドッキング位置にドッキングします。|  
|[CDockablePane::DockToWindow](#docktowindow)|別のドッキング ペインには、1 つのドッキング ペインをドッキングします。|  
|[CDockablePane::EnableAutohideAll](#enableautohideall)|有効またはと共にコンテナー内の他のペインには、このペインの自動非表示モードを無効にします。|  
|[CDockablePane::EnableGripper](#enablegripper)|キャプション (グリップ) の表示と非表示を切り替えます。|  
|[CDockablePane::GetAHRestoredRect](#getahrestoredrect)|自動非表示モードで表示される場合、ウィンドウの位置を指定します。|  
|[CDockablePane::GetAHSlideMode](#getahslidemode)|ウィンドウの自動非表示スライド モードを取得します。|  
|`CDockablePane::GetAutoHideButton`|内部的に使用します。|  
|`CDockablePane::GetAutoHideToolBar`|内部的に使用します。|  
|[CDockablePane::GetCaptionHeight](#getcaptionheight)|現在のキャプションの高さを返します。|  
|[CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)|既定ペイン分割バー ペインのコンテナーを返します。|  
|[CDockablePane::GetDockingStatus](#getdockingstatus)|ドッキング ペインの機能が提供されているポインターの位置に基づいて決定します。|  
|[CDockablePane::GetDragSensitivity](#getdragsensitivity)|ドッキング ウィンドウのドラッグと小文字の区別を返します。|  
|[CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)|コンテナー内のペインを占有する領域の割合を取得します。|  
|[CDockablePane::GetTabArea](#gettabarea)|ウィンドウのタブ領域を取得します。|  
|[CDockablePane::GetTabbedPaneRTC](#gettabbedpanertc)|現在のウィンドウに別のペインのドッキング時に作成されるタブ付きウィンドウに関するランタイム クラス情報を返します。|  
|[CDockablePane::HasAutoHideMode](#hasautohidemode)|ドッキング ペインを自動的に隠すモードに切り替えることができるかどうかを指定します。|  
|[CDockablePane::HitTest](#hittest)|ユーザーがマウスをクリックしたウィンドウで特定の場所を指定します。|  
|`CDockablePane::IsAccessibilityCompatible`|内部的に使用します。|  
|[CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)|ドッキング ペインと、コンテナー内の他のペインを自動的に隠すモードで配置できるかどうかを示します。|  
|[CDockablePane::IsAutoHideMode](#isautohidemode)|ペインが自動非表示モードになっているかどうかを判断します。|  
|`CDockablePane::IsChangeState`|内部的に使用します。|  
|[CDockablePane::IsDocked](#isdocked)|現在のウィンドウがドッキングされているかどうかを決定します。|  
|[CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode)|これを示すように (または非表示) を呼び出している場合、自動非表示モードになっているウィンドウの動作を決定`ShowPane`します。|  
|[CDockablePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|ウィンドウが複数のウィンドウ フレーム ウィンドウかどうかを指定します。|  
|[CDockablePane::IsResizable](#isresizable)|ウィンドウがサイズ変更可能かどうかを指定します。|  
|[CDockablePane::IsTabLocationBottom](#istablocationbottom)|タブが上部またはウィンドウの下部にあるかどうかを指定します。|  
|[CDockablePane::IsTracked](#istracked)|ユーザーがペインにドラッグしているかどうかを指定します。|  
|[CDockablePane::IsVisible](#isvisible)|現在のウィンドウが表示されているかどうかを決定します。|  
|[CDockablePane::LoadState](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917)|内部的に使用します。|  
|[CDockablePane::OnAfterChangeParent](#onafterchangeparent)|ウィンドウの親が変更されたときに、フレームワークによって呼び出されます。 (上書き[CPane::OnAfterChangeParent](../../mfc/reference/cpane-class.md#onafterchangeparent))。|  
|[CDockablePane::OnAfterDockFromMiniFrame](#onafterdockfromminiframe)|フレーム ウィンドウのフローティング、ドッキング バーをドッキングすると、フレームワークによって呼び出されます。|  
|[CDockablePane::OnBeforeChangeParent](#onbeforechangeparent)|ウィンドウの親を変更するときに、フレームワークによって呼び出されます。 (上書き[CPane::OnBeforeChangeParent](../../mfc/reference/cpane-class.md#onbeforechangeparent))。|  
|[CDockablePane::OnBeforeFloat](#onbeforefloat)|ペインが浮動小数点数に、フレームワークによって呼び出されます。 (上書き[CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat))。|  
|[CDockablePane::RemoveFromDefaultPaneDividier](#removefromdefaultpanedividier)|フレームワークは、ペインのドッキングを解除中にこのメソッドを呼び出します。|  
|[CDockablePane::ReplacePane](#replacepane)|指定したウィンドウで、ウィンドウを置き換えます。|  
|[CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)|フレームワークは、ペインが既定ペイン分割バーを復元する逆シリアル化されるように、このメソッドを呼び出します。|  
|`CDockablePane::SaveState`|内部的に使用します。|  
|`CDockablePane::Serialize`|ウィンドウをシリアル化します。 (`CBasePane::Serialize` をオーバーライドします)。|  
|[CDockablePane::SetAutoHideMode](#setautohidemode)|ドッキング ペインの表示を切り替えると自動的に隠すモードです。|  
|[CDockablePane::SetAutoHideParents](#setautohideparents)|自動的に隠す ボタンをクリックし、ウィンドウの自動的に隠すツールバーを設定します。|  
|`CDockablePane::SetDefaultPaneDivider`|内部的に使用します。|  
|[CDockablePane::SetLastPercentInPaneContainer](#setlastpercentinpanecontainer)|コンテナー内のペインを占有する領域の割合を設定します。|  
|`CDockablePane::SetResizeMode`|内部的に使用します。|  
|[CDockablePane::SetRestoredDefaultPaneDivider](#setrestoreddefaultpanedivider)|復元された既定の分割線を設定します。|  
|[CDockablePane::SetTabbedPaneRTC](#settabbedpanertc)|2 つのウィンドウがドッキング時に作成されるタブ付きウィンドウのランタイム クラス情報を設定します。|  
|[CDockablePane::ShowPane](#showpane)|ペインの表示と非表示を切り替えます。|  
|[CDockablePane::Slide](#slide)|ウィンドウが自動非表示モードの場合にのみを表示するスライド アニメーションを持つペインの表示と非表示を切り替えます。|  
|[CDockablePane::ToggleAutoHide](#toggleautohide)|切り替えを自動的に隠すモードです。 (上書き[CPane::ToggleAutoHide](../../mfc/reference/cpane-class.md#toggleautohide) )。|  
|[CDockablePane::UndockPane](#undockpane)|メイン フレーム ウィンドウまたはミニフレーム ウィンドウのコンテナーのいずれかからウィンドウをドッキング解除します。|  
|`CDockablePane::UnSetAutoHideMode`|内部的に使用します。 自動非表示モードを設定するには使用[CDockablePane::SetAutoHideMode](#setautohidemode)|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDockablePane::CheckAutoHideCondition](#checkautohidecondition)|(自動的に隠すモード) では、ドッキング ペインが非表示かどうかを決定します。|  
|[CDockablePane::CheckStopSlideCondition](#checkstopslidecondition)|スライディング止めるを自動的に隠すドッキング ペインを決定します。|  
|[CDockablePane::DrawCaption](#drawcaption)|ドッキング ペインのキャプション (グリップ) を描画します。|  
|[CDockablePane::OnPressButtons](#onpressbuttons)|ユーザー以外のキャプション ボタンを押したときと呼ばれる、`AFX_HTCLOSE`と`AFX_HTMAXBUTTON`ボタン。|  
|[CDockablePane::OnSlide](#onslide)|ウィンドウが表示または非表示になっているときに、自動非表示スライド効果を表示するためにフレームワークによって呼び出されます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDockablePane::m_bDisableAnimation](#m_bdisableanimation)|ドッキング可能なウィンドウのアニメーションを自動的に隠すが無効になっているかどうかを指定します。|  
|[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)|ウィンドウが自動非表示モードの場合は、ウィンドウの動作を決定します。|  
|[CDockablePane::m_nSlideSteps](#m_nslidesteps)|されているときに、ウィンドウのアニメーションの速度を指定または自動非表示モードで非表示を表示します。|  
  
## <a name="remarks"></a>コメント  
 `CDockablePane`次の機能を実装します。  
  
-   メイン フレーム ウィンドウに、ウィンドウをドッキングします。  
  
-   自動非表示モードには、ウィンドウを切り替えます。  
  
-   ペインをタブ付きウィンドウにアタッチします。  
  
-   ミニフレーム ウィンドウのペインをフローティングします。  
  
-   固定されていないミニフレーム ウィンドウで別のペインに、ウィンドウをドッキングします。  
  
-   ペインのサイズを変更します。  
  
-   読み込みと、ドッキング ペインの状態を保存します。  
  
    > [!NOTE]
    >  状態情報は、Windows レジストリに保存されます。  
  
-   キャプションの有無は、ウィンドウを作成します。 キャプション テキスト ラベルを持つことができ、グラデーションの色で塗りつぶすことができます。  
  
-   ウィンドウの内容を表示するときに、ウィンドウをドラッグします。  
  
-   ドラッグ四角形を表示するときに、ウィンドウをドラッグします。  
  
 アプリケーションでドッキング ペインを使用するからウィンドウ クラスを派生、`CDockablePane`クラスです。 メイン フレーム ウィンドウ オブジェクトや、ウィンドウのインスタンスを制御するウィンドウ オブジェクトには、派生オブジェクトを埋め込むか。 まず、 [CDockablePane::Create](#create)メソッドまたは[CDockablePane::CreateEx](#createex)メソッドを処理するとき、`WM_CREATE`メイン フレーム ウィンドウのメッセージ。 呼び出して、ウィンドウのオブジェクトを最後に、セットアップ[CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)、 [CBasePane::DockPane](../../mfc/reference/cbasepane-class.md#dockpane)、または[CDockablePane::AttachToTabWnd](#attachtotabwnd)します。  
  
## <a name="customization-tips"></a>カスタマイズのヒント  
 次のヒントを適用する`CDockablePane`オブジェクト。  
  
-   呼び出した場合[CDockablePane::AttachToTabWnd](#attachtotabwnd)で&2; つのタブ付き以外、ドッキング可能ペインのタブ付きウィンドウへのポインターが返される、`ppTabbedControlBar`パラメーター。 このパラメーターを使用してタブ付きウィンドウへのタブを追加する続行することができます。  
  
-   によって作成されるタブ付きペインのような[CDockablePane::AttachToTabWnd](#attachtotabwnd)によって決まりますが、`CDockablePane`内のオブジェクト、`pTabControlBarAttachTo`パラメーター。 呼び出すことができます[CDockablePane::SetTabbedPaneRTC](#settabbedpanertc)にタブ付きペインの種類を設定、`CDockablePane`が作成されます。 既定値の型によって決定されます、`dwTabbedStyle`の[CDockablePane::Create](#create)作成する場合、`CDockablePane`です。 場合`dwTabbedStyle`は既定の種類は AFX_CBRS_OUTLOOK_TABS[があります](../../mfc/reference/cmfcoutlookbar-class.md)場合`dwTabbedStyle`は既定の種類は AFX_CBRS_REGULAR_TABS[派生クラス](../../mfc/reference/ctabbedpane-class.md)します。  
  
-   別の&1; つのドッキング可能なペインをドッキングする場合、 [CDockablePane::DockToWindow](#docktowindow)メソッドです。 元のウィンドウ ドッキングされていなければなりませんどこかにこのメソッドを呼び出す前にします。  
  
-   メンバー変数[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)コントロールのドッキング可能ペインの動作は自動でどのように非表示にするモードを呼び出したときに[CDockablePane::ShowPane](#showpane)します。 このメンバー変数に設定されている場合`TRUE`、ドッキング可能ペインと、自動非表示ボタンは表示されません。 それ以外の場合、それらがスライド アウトします。  
  
-   設定して自動的に隠すアニメーションを無効にすることができます、 [CDockablePane::m_bDisableAnimation](#m_bdisableanimation)メンバー変数に`TRUE`します。  
  
## <a name="example"></a>例  
 次の例では、構成、`CDockablePane`オブジェクトのさまざまなメソッドを使用して、`CDockablePane`クラスです。 この例では、自動的に隠すのドッキング可能ペインのすべての機能を有効にする、キャプションまたはグリッパーを有効にする、自動非表示モードを有効にする、ウィンドウを表示、および自動非表示モードになっているウィンドウをアニメーション化する方法を示します。 このコード スニペットの一部である、 [Visual Studio のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&27;](../../mfc/codesnippet/cpp/cdockablepane-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo #&28;](../../mfc/codesnippet/cpp/cdockablepane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxDockablePane.h  
  
##  <a name="attachtotabwnd"></a>CDockablePane::AttachToTabWnd  
 現在のウィンドウをタブ付きペインを作成するターゲット ウィンドウにアタッチします。  
  
```  
virtual CDockablePane* AttachToTabWnd(
    CDockablePane* pTabControlBarAttachTo,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bSetActive= TRUE,  
    CDockablePane** ppTabbedControlBar = NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pTabControlBarAttachTo`  
 現在のウィンドウにアタッチするターゲット ウィンドウを指定します。 ターゲット ウィンドウには、ドッキング可能ペインをする必要があります。  
  
 [入力] `dockMethod`  
 ドッキング方法を指定します。  
  
 [入力] `bSetActive`  
 `TRUE`アタッチ操作後に、タブ付きウィンドウをアクティブにするにはそれ以外の場合、`FALSE`です。  
  
 [出力] `ppTabbedControlBar`  
 アタッチ操作の結果であるタブ付きペインが含まれています。  
  
### <a name="return-value"></a>戻り値  
 タブ付きペインではない場合は、現在ペインへのポインターそれ以外の場合、アタッチ操作の結果であるタブ付きペインへのポインター。 戻り値は`NULL`現在のウィンドウをアタッチできない場合、またはエラーが発生した場合。  
  
### <a name="remarks"></a>コメント  
 1 つのドッキング可能ペインは、このメソッドを使用して別のペインに関連付ける、ときに、以下の処理が行われます。  
  
1.  Framework チェックするかどうかターゲット ウィンドウ`pTabControlBarAttachTo`は、通常ドッキング ペインまたはかどうかから派生[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)します。  
  
2.  ターゲット ウィンドウがタブ付きペインの場合は、フレームワークは、タブとしてに現在のウィンドウを追加します。  
  
3.  ターゲット ウィンドウが標準のドッキング ペインの場合は、フレームワークはタブ付きペインを作成します。  
  
    -   Framework 呼び出し`pTabControlBarAttachTo->CreateTabbedPane`します。 新しいタブ付きウィンドウのスタイルが異なります、`m_pTabbedControlBarRTC`メンバーです。 既定では、このメンバーのランタイム クラスに設定[派生](../../mfc/reference/ctabbedpane-class.md)します。 渡した場合、`AFX_CBRS_OUTLOOK_TABS`スタイルとして、`dwTabbedStyle`パラメーターを[CDockablePane::Create](#create)メソッド、ランタイム クラスのオブジェクトに設定されているのランタイム クラス[があります](../../mfc/reference/cmfcoutlookbar-class.md)します。 このメンバーは、新しいウィンドウのスタイルを変更するには、いつでも変更できます。  
  
    -   フレームワークこのメソッドは、タブ付きペインを作成へのポインターに置き換えられます`pTabControlBarAttachTo`(かどうか、ウィンドウはドッキングまたはフローティング マルチ ミニフレーム ウィンドウの) 新しいタブ付きペインへのポインター。  
  
    -   フレームワークは、追加、`pTabControlBarAttachTo`最初のタブとしてタブ付きペインにウィンドウです。 フレームワークは、2 番目のタブとして、現在のウィンドウを追加します。  
  
4.  現在のウィンドウがから派生している場合`CBaseTabbedPane`、すべてのタブに移動`pTabControlBarAttachTo`され、現在のウィンドウを破棄します。 そのため、必ずこのメソッドを呼び出すときにメソッドが戻るときに現在のウィンドウへのポインターが有効にする場合がありますのでください。  
  
 ドッキング レイアウトを構築する際に&1; つのペインをアタッチする場合は、設定`dockMethod`に`DM_SHOW`します。  
  
 別のペインを添付する前に、最初にウィンドウをドッキングする必要があります。  
  
##  <a name="calcfixedlayout"></a>CDockablePane::CalcFixedLayout  
 ペインの四角形のサイズを返します。  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bStretch`  
 使用しません。  
  
 [入力] `bHorz`  
 使用しません。  
  
### <a name="return-value"></a>戻り値  
 A`CSize`ペインの四角形のサイズを含むオブジェクト。  
  
##  <a name="canacceptminiframe"></a>CDockablePane::CanAcceptMiniFrame  
 指定したミニフレームをウィンドウにドッキングできるかどうかを決定します。  
  
```  
virtual BOOL CanAcceptMiniFrame(CPaneFrameWnd* pMiniFrame) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMiniFrame`  
 ポインター、`CPaneFrameWnd`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合`pMiniFrame`ウィンドウにドッキングされている。 それ以外の場合、`FALSE`です。  
  
##  <a name="canacceptpane"></a>CDockablePane::CanAcceptPane  
 現在のウィンドウに別のペインをドッキングできるかどうかを決定します。  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 現在のウィンドウにドッキングするウィンドウを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このペインに、指定したウィンドウをドッキングできる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、現在のウィンドウ ペインをドッキングする前に、このメソッドを呼び出します。  
  
 この関数を有効にするか、特定のウィンドウをドッキングは無効にする派生クラスでオーバーライドします。  
  
 既定では、このメソッドが戻る`TRUE`場合`pBar`か型がその親`CDockablePane`します。  
  
##  <a name="canautohide"></a>CDockablePane::CanAutoHide  
 かどうかのウィンドウが自動的に隠すを決定します。  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウが自動的に隠す場合です。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 `CDockablePane::CanAutoHide`返します`FALSE`で次のような場合。  
  
-   ウィンドウには、親がありません。  
  
-   ドッキングのマネージャーでは、ウィンドウを自動的に隠すには許可されません。  
  
-   ウィンドウがドッキングされていません。  
  
##  <a name="canbeattached"></a>CDockablePane::CanBeAttached  
 現在のウィンドウを別のウィンドウにドッキングできるかどうかを決定します。  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`別のペインに、またはメイン フレーム ウィンドウにドッキング可能ペインをドッキングできる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは常`TRUE`します。 このメソッドを有効または無効呼び出さずにドッキングする派生クラスでオーバーライド[CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)します。  
  
##  <a name="cdockablepane"></a>CDockablePane::CDockablePane  
 構築して初期化、 [CDockablePane](../../mfc/reference/cdockablepane-class.md)オブジェクトです。  
  
```  
CDockablePane();
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウのドッキング可能なオブジェクトを構築した後で呼び出す[CDockablePane::Create](#create)または[CDockablePane::CreateEx](#createex)を作成します。  
  
##  <a name="converttotabbeddocument"></a>CDockablePane::ConvertToTabbedDocument  
 1 つまたは複数のドッキング可能ペインを MDI タブ付きドキュメントに変換します。  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bActiveTabOnly`  
 変換する場合、 `CTabbedPane`、指定`TRUE`にアクティブなタブのみを変換します。 指定`FALSE`ペイン内のすべてのタブに変換します。  
  
##  <a name="checkautohidecondition"></a>CDockablePane::CheckAutoHideCondition  
 ドッキング ペインで、(自動非表示モードとも呼ばれます) が非表示かどうかを決定します。  
  
```  
virtual BOOL CheckAutoHideCondition();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は非表示にする条件が満たされたとします。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、タイマーを使用して、定期的に自動非表示のドッキング可能なペインを非表示にするかどうかを確認します。 このメソッドを返します`TRUE`と、ウィンドウが非アクティブ、ウィンドウ サイズを変更できませんが、マウス ポインターが、ウィンドウです。  
  
 以前のすべての条件が満たされた場合、フレームワーク[CDockablePane::Slide](#slide)ウィンドウを非表示にします。  
  
##  <a name="checkstopslidecondition"></a>CDockablePane::CheckStopSlideCondition  
 スライディング止める自動非表示のドッキング ペインを決定します。  
  
```  
virtual BOOL CheckStopSlideCondition(BOOL bDirection);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDirection`  
 `TRUE`ウィンドウが表示されている場合`FALSE`のウィンドウが表示されていない場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`停止状態になっている; 場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能ペインは、自動非表示モードに設定されているときに、フレームワークは、ウィンドウを非表示スライド効果を使用します。 フレームワークは、ペインがスライドときに、この関数を呼び出します。 `CheckStopSlideCondition`返します`TRUE`ウィンドウが完全に表示されているとき、またはと完全に非表示にされています。  
  
 カスタムの自動非表示の効果を実装する派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="copystate"></a>CDockablePane::CopyState  
 ドッキング可能ペインの状態をコピーします。  
  
```  
virtual void CopyState(CDockablePane* pOrgBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pOrgBar`  
 ドッキング可能ペインへのポインター。  
  
### <a name="remarks"></a>コメント  
 `CDockablePane::CopyState`状態をコピー`pOrgBar`を次のメソッドを呼び出して現在のウィンドウにします。  
  
- [CPane::CopyState](../../mfc/reference/cpane-class.md#copystate)  
  
- [CDockablePane::GetAHRestoredRect](#getahrestoredrect)  
  
- [CDockablePane::GetAHSlideMode](#getahslidemode)  
  
- [CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)  
  
- [CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)  
  
##  <a name="create"></a>CDockablePane::Create  
 Windows コントロールを作成し、それをアタッチ、 [CDockablePane](../../mfc/reference/cdockablepane-class.md)オブジェクトです。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE,  
    CCreateContext* pContext = NULL);

 
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    CSize sizeDefault,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle = WS_CHILD|WS_VISIBLE|CBRS_TOP|CBRS_HIDE_INPLACE,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszCaption`  
 ウィンドウの名前を指定します。  
  
 [in][out]`pParentWnd`  
 親ウィンドウを指定します。  
  
 [入力] `rect`  
 クライアント座標でサイズと、ウィンドウの位置を指定`pParentWnd`します。  
  
 [入力] `bHasGripper`  
 `TRUE`キャプション付きのウィンドウを作成するにはそれ以外の場合、`FALSE`です。  
  
 [入力] `nID`  
 子ウィンドウの ID を指定します。 この値は、このドッキング ウィンドウのドッキング状態を保存する場合は、一意である必要があります。  
  
 [入力] `dwStyle`  
 ウィンドウのスタイル属性を指定します。  
  
 [入力] `dwTabbedStyle`  
 ユーザーは、このペインのキャプションのペインをドラッグしたときに作成されるタブ付きウィンドウのタブ付きスタイルを指定します。  
  
 [入力] `dwControlBarStyle`  
 追加のスタイル属性を指定します。  
  
 [in][out]`pContext`  
 ウィンドウの作成のコンテキストを指定します。  
  
 [入力] `lpszWindowName`  
 ウィンドウの名前を指定します。  
  
 [入力] `sizeDefault`  
 ウィンドウのサイズを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング可能ペインが正常に作成された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ ペインを作成し、それにアタッチ、`CDockablePane`オブジェクトです。  
  
 場合、`dwStyle`ウィンドウ スタイルが、`CBRS_FLOAT_MULTI`フラグ、ミニフレーム ウィンドウをミニフレーム ウィンドウの他のペインをフローティングできます。 既定では、ドッキング ペインだけをフローティングできる個別にします。  
  
 場合、`dwTabbedStyle`パラメーターには、`AFX_CBRS_OUTLOOK_TABS`フラグが指定されて、このウィンドウを使用する別のペインが関連付けられている場合、ペインを Outlook のようなタブ付きペインを作成、 [CDockablePane::AttachToTabWnd](#attachtotabwnd)メソッドです。 既定では、ドッキング可能ペインの作成の種類の正規のタブ付きペイン[派生](../../mfc/reference/ctabbedpane-class.md)します。  
  
##  <a name="createdefaultpanedivider"></a>CDockablePane::CreateDefaultPaneDivider  
 フレーム ウィンドウにドッキングされているように、ウィンドウの既定の区分線を作成します。  
  
```  
static CPaneDivider* __stdcall CreateDefaultPaneDivider(
    DWORD dwAlignment,  
    CWnd* pParent,  
    CRuntimeClass* pSliderRTC = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 ペインをドッキングするメインのフレームの辺を指定します。 場合`dwAlignment`が含まれています、`CBRS_ALIGN_LEFT`または`CBRS_ALIGN_RIGHT`フラグは、このメソッドを作成、垂直 ( `CPaneDivider::SS_VERT`) 区分線の水平方向が、このメソッドによって作成される場合は、( `CPaneDivider::SS_HORZ`) 区分線。  
  
 [入力] `pParent`  
 親のフレームへのポインター。  
  
 [入力] `pSliderRTC`  
 使用しません。  
  
### <a name="return-value"></a>戻り値  
 このメソッドは、新しく作成した区分線にポインターを返しますまたは`NULL`区分線の作成に失敗した場合。  
  
### <a name="remarks"></a>コメント  
 `dwAlignment`次の値のいずれかを指定できます。  
  
|値|説明|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|ウィンドウ フレーム ウィンドウのクライアント領域の上部にドッキングします。|  
|`CBRS_ALIGN_BOTTOM`|ウィンドウ フレーム ウィンドウのクライアント領域の下部にドッキングします。|  
|`CBRS_ALIGN_LEFT`|ウィンドウ フレーム ウィンドウのクライアント領域の左側にドッキングします。|  
|`CBRS_ALIGN_RIGHT`|ウィンドウ フレーム ウィンドウのクライアント領域の右側にドッキングします。|  
  
##  <a name="createex"></a>CDockablePane::CreateEx  
 Windows コントロールを作成し、それをアタッチ、 [CDockablePane](../../mfc/reference/cdockablepane-class.md)オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwStyleEx`  
 新しいウィンドウの拡張スタイル属性を指定します。  
  
 [入力] `lpszCaption`  
 ウィンドウの名前を指定します。  
  
 [in][out]`pParentWnd`  
 親ウィンドウを指定します。  
  
 [入力] `rect`  
 クライアント座標でサイズと、ウィンドウの位置を指定`pParentWnd`します。  
  
 [入力] `bHasGripper`  
 `TRUE`キャプション付きのウィンドウを作成するにはそれ以外の場合、`FALSE`です。  
  
 [入力] `nID`  
 子ウィンドウの ID を指定します。 この値は、このドッキング ペインのドッキング状態を保存する場合は、一意である必要があります。  
  
 [入力] `dwStyle`  
 ウィンドウのスタイル属性を指定します。  
  
 [入力] `dwTabbedStyle`  
 ユーザーは、このペインのキャプションのペインをドラッグしたときに作成されるタブ付きウィンドウのタブ付きスタイルを指定します。  
  
 [入力] `dwControlBarStyle`  
 追加のスタイル属性を指定します。  
  
 [in][out]`pContext`  
 ウィンドウの作成のコンテキストを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング可能ペインが正常に作成された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ ペインを作成し、それにアタッチ、`CDockablePane`オブジェクトです。  
  
 場合、`dwStyle`ウィンドウ スタイルが、`CBRS_FLOAT_MULTI`フラグ、ミニフレーム ウィンドウをミニフレーム ウィンドウの他のペインをフローティングできます。 既定では、ドッキング ペインだけをフローティングできる個別にします。  
  
 場合、`dwTabbedStyle`パラメーターには、`AFX_CBRS_OUTLOOK_TABS`フラグが指定されて、このウィンドウを使用する別のペインが関連付けられている場合、ペインを Outlook のようなタブ付きペインを作成、 [CDockablePane::AttachToTabWnd](#attachtotabwnd)メソッドです。 既定では、ドッキング可能ペインの作成の種類の正規のタブ付きペイン[派生](../../mfc/reference/ctabbedpane-class.md)します。  
  
##  <a name="createtabbedpane"></a>CDockablePane::CreateTabbedPane  
 現在のウィンドウからタブ付きペインを作成します。  
  
```  
virtual CTabbedPane* CreateTabbedPane();
```  
  
### <a name="return-value"></a>戻り値  
 新しいタブ付きペインまたは`NULL`作成操作が失敗した場合。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、このペインを置換するタブ付きペインを作成するときに、このメソッドを呼び出します。 詳細については、次を参照してください。 [CDockablePane::AttachToTabWnd](#attachtotabwnd)します。  
  
 どのタブ付きペインをカスタマイズする派生クラスでこのメソッドが作成され、初期化をオーバーライドします。  
  
 格納されているランタイム クラス情報に従って、タブ付きペインを作成、`m_pTabbedControlBarRTC`によって初期化されるメンバー、 [CDockablePane::CreateEx](#createex)メソッドです。  
  
##  <a name="dockpanecontainer"></a>CDockablePane::DockPaneContainer  
 ウィンドウに、コンテナーにドッキングします。  
  
```  
virtual BOOL DockPaneContainer(
    CPaneContainerManager& barContainerManager,  
    DWORD dwAlignment,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `barContainerManager`  
 ドッキングされるコンテナーのコンテナー マネージャーへの参照。  
  
 [入力] `dwAlignment`  
 `DWORD`コンテナーのドッキング ペインの横を指定します。  
  
 [入力] `dockMethod`  
 使用しません。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`コンテナーが正常に、ウィンドウにドッキングされている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 `dwAlignment`次の値のいずれかを指定できます。  
  
|値|説明|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|コンテナーは、ウィンドウの上部にドッキングします。|  
|`CBRS_ALIGN_BOTTOM`|コンテナーは、ウィンドウの下部にドッキングします。|  
|`CBRS_ALIGN_LEFT`|コンテナーは、ウィンドウの左側にドッキングします。|  
|`CBRS_ALIGN_RIGHT`|コンテナーは、ウィンドウの右側にドッキングします。|  
  
##  <a name="dockpanestandard"></a>CDockablePane::DockPaneStandard  
 アウトライン (標準) のドッキングを使用して、ウィンドウをドッキングします。  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bWasDocked`  
 この値が含まれる、メソッドが戻るとき`TRUE`含まれている場合は、ウィンドウは、正常にドッキングされている以外の場合に、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 タブ付きウィンドウに、ウィンドウがドッキングされている場合、またはタブ付きウィンドウがドッキングの結果として作成された場合は、このメソッドは、タブ付きウィンドウへのポインターを返します。 このメソッドが戻るかどうかは、ウィンドウにはそれ以外の場合を正常にドッキング、`this`ポインター。 ドッキングが失敗したかどうか、このメソッドが戻る`NULL`します。  
  
##  <a name="docktorecentpos"></a>CDockablePane::DockToRecentPos  
 ストアドのドッキング位置に、ウィンドウをドッキングします。  
  
```  
BOOL CDockablePane::DockToRecentPos();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウが正常にドッキングされている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能ペインに最新のドッキング情報を格納する、 [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md)オブジェクトです。  
  
##  <a name="docktowindow"></a>CDockablePane::DockToWindow  
 別のドッキング ペインには、1 つのドッキング ペインをドッキングします。  
  
```  
virtual BOOL DockToWindow(
    CDockablePane* pTargetWindow,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pTargetWindow`  
 このペインをドッキングする、ドッキング可能ウィンドウを指定します。  
  
 [入力] `dwAlignment`  
 ペインのドッキングの配置を指定します。 CBRS_ALIGN_LEFT、CBRS_ALIGN_TOP、CBRS_ALIGN_RIGHT、CBRS_ALIGN_BOTTOM または CBRS_ALIGN_ANY のいずれかを指定することがあります。 (Afxres.h 内で定義)。  
  
 [入力] `lpRect`  
 ペインのドッキングする四角形を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウが正常にドッキングされている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 指定された配置された別のペインに&1; つのペインをドッキングするには、このメソッドを呼び出す`dwAlignment`します。  
  
##  <a name="drawcaption"></a>CDockablePane::DrawCaption  
 ドッキング ペインのキャプション ("グリッパー"とも呼ばれます) を描画します。  
  
```  
virtual void DrawCaption(
    CDC* pDC,  
    CRect rectCaption);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 描画に使用されるデバイス コンテキストを表します。  
  
 [入力] `rectCaption`  
 ペインのキャプションの外接する四角形を指定します。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、ドッキング可能ペインのキャプションを描画するには、このメソッドを呼び出します。  
  
 キャプションの外観をカスタマイズする派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="enableautohideall"></a>CDockablePane::EnableAutohideAll  
 有効またはこのペイン、およびコンテナー内の他のペインの自動非表示モードを無効にします。  
  
```  
void EnableAutohideAll(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`自動非表示のドッキング可能ペインのすべての機能を有効にするにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ユーザーが保持して、`Ctrl`キーや暗証番号 (pin) ボタンをクリックして自動的に隠すモード、同じコンテナー内の他のすべてのペインに、ウィンドウを切り替えるには、自動非表示モードに切り替わりますもクリックします。  
  
 このメソッドを呼び出します`bEnable`に設定`FALSE`特定のペインのこの機能を無効にします。  
  
##  <a name="enablegripper"></a>CDockablePane::EnableGripper  
 ("グリッパー"とも呼ばれます) のキャプションの表示と非表示を切り替えます。  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`キャプションを有効にするにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 これらがないために、フレームワークは、ドッキング可能ペインを作成するとき、 **WS_STYLE**指定されている場合でも、ウィンドウ スタイル。 つまり、ペインのキャプションは、フレームワークによって制御される非クライアント領域もこの領域は、標準のウィンドウ キャプションによって異なります。  
  
 表示またはキャプションをいつでも非表示にできます。 フレームワークでは、タブ付きウィンドウまたはミニフレーム ウィンドウで、ウィンドウがフローティング状態になった、タブとペインが追加されたときに、キャプションが表示されません。  
  
##  <a name="getahrestoredrect"></a>CDockablePane::GetAHRestoredRect  
 自動非表示モードのときにウィンドウの位置を指定します。  
  
```  
CRect GetAHRestoredRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CRect`自動非表示モードにあるときに、ウィンドウの位置を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getahslidemode"></a>CDockablePane::GetAHSlideMode  
 ウィンドウの自動非表示スライド モードを取得します。  
  
```  
virtual UINT GetAHSlideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`UINT`ペインの自動非表示スライド モードを指定します。 戻り値は、いずれかの`AFX_AHSM_MOVE`または`AFX_AHSM_STRETCH`、実装を使用してのみが、`AFX_AHSM_MOVE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcaptionheight"></a>CDockablePane::GetCaptionHeight  
 現在のキャプションのピクセルで高さを返します。  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 (ピクセル単位)、キャプションの高さ。  
  
### <a name="remarks"></a>コメント  
 キャプションは非表示の場合、キャプションの高さは 0、 [CDockablePane::EnableGripper](#enablegripper)メソッド、または、ウィンドウに、キャプションがあるない場合。  
  
##  <a name="getdefaultpanedivider"></a>CDockablePane::GetDefaultPaneDivider  
 既定ペイン分割バー ペインのコンテナーを返します。  
  
```  
CPaneDivider* GetDefaultPaneDivider() const;  
```  
  
### <a name="return-value"></a>戻り値  
 有効な[CPaneDivider](../../mfc/reference/cpanedivider-class.md)ドッキング可能ペインがメイン フレーム ウィンドウにドッキングされている場合は、オブジェクトまたは`NULL`がフローティングかドッキング可能なウィンドウがドッキングされていない場合。  
  
### <a name="remarks"></a>コメント  
 ペイン分割バーの詳細については、次を参照してください。 [CPaneDivider クラス](../../mfc/reference/cpanedivider-class.md)します。  
  
##  <a name="getdockingstatus"></a>CDockablePane::GetDockingStatus  
 ドッキング ペインの機能が提供されているポインターの位置に基づいて決定します。  
  
```  
virtual AFX_CS_STATUS GetDockingStatus(
    CPoint pt,  
    int nSensitivity);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pt`  
 画面座標でポインターの位置。  
  
 [入力] `nSensitivity`  
 距離 (ピクセル単位) 四角形の端からポインターがドッキング可能にするされます。  
  
### <a name="return-value"></a>戻り値  
 次のステータス値のいずれかです。  
  
|`AFX_CS_STATUS` の値|説明|  
|---------------------------|-------------|  
|`CS_NOTHING`|ポインターがドッキング サイト上でないです。 フレームワークは、ペインをドッキングしていません。|  
|`CS_DOCK_IMMEDIATELY`|マウス ポインターが上にあるドッキング サイト イミディ エイト モード (ウィンドウを使用して、`DT_IMMEDIATE`ドッキング モード)。 フレームワークでは、すぐに、ウィンドウをドッキングします。|  
|`CS_DELAY_DOCK`|ポインターとは別のドッキング ペインまたはメイン フレームの端は、ドッキング サイト上です。 フレームワークは、時間が経過したら、ウィンドウをドッキングします。 この待機時間の詳細については「解説」セクションを参照してください。|  
|`CS_DELAY_DOCK_TO_TAB`|マウス ポインターが、タブ付きウィンドウにドッキングするウィンドウをドッキング サイト上にあります。 これは、タブ付きペインのタブ領域上、または別のドッキング ペインのキャプション上、ポインターがある場合に発生します。|  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、浮動ペインのドッキングを処理するには、このメソッドを呼び出します。  
  
 フローティング ツールバーのドッキング ペインを使用する、`DT_IMMEDIATE`モードをドッキングするには、フレームワークでは遅延ドッキング コマンドをドッキングを実行する前に、親フレームのクライアント領域から、ウィンドウを移動するユーザーを有効にします。 遅延の長さの単位はミリ秒とによって制御されます、 [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock)データ メンバー. 既定値の[CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) 200 です。 この動作のドッキングの動作をエミュレートする[!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)]2007 です。  
  
 ドッキング状態を遅延のため (`CS_DELAY_DOCK`と`CS_DELAY_DOCK_TO_TAB`)、フレームワークは、ユーザーがマウス ボタンを離すまでのドッキングを実行しません。 ペインを使用している場合、`DT_STANDARD`モードをドッキングするには、フレームワーク、四角形に表示ドッキング場所です。 ペインを使用している場合、`DT_SMART`モードをドッキングするには、フレームワークによって表示スマート ドッキング マーカーと半透明の四角形、ドッキング場所にあります。 ウィンドウのドッキング モードを指定するには、呼び出し、 [CBasePane::SetDockingMode](../../mfc/reference/cbasepane-class.md#setdockingmode)メソッドです。 スマート ドッキングの詳細については、次を参照してください。 [CDockingManager::GetSmartDockingParams](../../mfc/reference/cdockingmanager-class.md#getsmartdockingparams)します。  
  
##  <a name="getdragsensitivity"></a>CDockablePane::GetDragSensitivity  
 ドッキング ウィンドウのドラッグと小文字の区別を返します。  
  
```  
static const CSize& GetDragSensitivity();
```  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)幅と高さ (ピクセル単位)、ドラッグ ポイントを中心とする四角形を格納しているオブジェクト。 ドラッグ操作は、マウス ポインターがこの四角形の外側に移動するまでは開始されません。  
  
##  <a name="getlastpercentinpanecontainer"></a>CDockablePane::GetLastPercentInPaneContainer  
 コンテナーのペインを占有する領域の割合を取得 ( [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md))。  
  
```  
int GetLastPercentInPaneContainer() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `int`コンテナー内のウィンドウを占有する領域の割合を指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コンテナーには、そのレイアウトが調整される場合に使用されます。  
  
##  <a name="gettabarea"></a>CDockablePane::GetTabArea  
 ウィンドウのタブ領域を取得します。  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectTabAreaTop`  
 `GetTabArea`タブが、ウィンドウの上部にある場合は、タブ領域でこの変数を設定します。 タブがウィンドウの下部にある場合は、この変数は、空の四角形が入力されます。  
  
 [入力] `rectTabAreaBottom`  
 `GetTabArea`タブがウィンドウの下部にある場合は、タブ領域でこの変数を設定します。 タブ、ウィンドウの上部にある場合は、この変数は、空の四角形が入力されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドから派生したクラスでのみ使用`CDockablePane`タブがあるとします。 詳細については、次を参照してください。 [CTabbedPane::GetTabArea](../../mfc/reference/ctabbedpane-class.md#gettabarea)と[CMFCOutlookBar::GetTabArea](../../mfc/reference/cmfcoutlookbar-class.md#gettabarea)します。  
  
##  <a name="gettabbedpanertc"></a>CDockablePane::GetTabbedPaneRTC  
 現在のウィンドウに別のペインのドッキング時に作成されるタブ付きウィンドウに関するランタイム クラス情報を返します。  
  
```  
CRuntimeClass* GetTabbedPaneRTC() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドッキング可能ペインのランタイム クラス情報。  
  
### <a name="remarks"></a>コメント  
 動的に作成されたタブ付きペインのランタイム クラス情報を取得するには、このメソッドを呼び出します。 これは、ユーザーが別のペインのキャプションに&1; つのペインをドラッグまたはを呼び出す場合に発生することができます、 [CDockablePane::AttachToTabWnd](#attachtotabwnd)メソッドをプログラムによって&2; つのドッキング可能ペインからタブ付きペインを作成します。  
  
 ランタイム クラス情報を設定するには呼び出すことによって、 [CDockablePane::SetTabbedPaneRTC](#settabbedpanertc)メソッドです。  
  
##  <a name="hasautohidemode"></a>CDockablePane::HasAutoHideMode  
 ドッキング ペインを自動的に隠すモードに切り替えることができるかどうかを指定します。  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング可能ペインは、自動非表示モードに切り替えることができる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 特定のドッキング可能なウィンドウの自動非表示モードを無効にする派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="hittest"></a>CDockablePane::HitTest  
 ユーザーがマウスをクリックしたウィンドウで、場所を指定します。  
  
```  
virtual int HitTest(
    CPoint point,  
    BOOL bDetectCaption = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 テストする点を指定します。  
  
 [入力] `bDetectCaption`  
 `TRUE`場合`HTCAPTION`かどうか、ポイントは、ペインのキャプションに返す必要がある場合は、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの値です。  
  
- `HTNOWHERE`場合`point`ドッキング可能なペインに表示されていません。  
  
- `HTCLIENT`場合`point`ドッキング可能なウィンドウのクライアント領域にします。  
  
- `HTCAPTION`場合`point`ドッキング可能ペインのキャプション領域にします。  
  
- `AFX_HTCLOSE`場合`point`閉じるボタンができます。  
  
- `HTMAXBUTTON`場合`point`は暗証番号 (pin) ボタンをクリックします。  
  
##  <a name="isautohideallenabled"></a>CDockablePane::IsAutohideAllEnabled  
 ドッキング ペインと、コンテナー内の他のペインが自動非表示モードに切り替えることができるかどうかを示します。  
  
```  
virtual BOOL IsAutohideAllEnabled() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング可能ペインと、コンテナー内の他のペインは、自動非表示モードに切り替えることができる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ユーザーが保持しているときに、ドッキングの暗証番号 (pin) ボタンをクリックして自動非表示モードを有効、 **Ctrl**キー  
  
 有効にするか、この動作を無効にする、 [CDockablePane::EnableAutohideAll](#enableautohideall)メソッドです。  
  
##  <a name="isautohidemode"></a>CDockablePane::IsAutoHideMode  
 ペインが自動非表示モードになっているかどうかを判断します。  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング可能なウィンドウが自動的に隠す モードである場合それ以外の場合、`FALSE`です。  
  
##  <a name="isdocked"></a>CDockablePane::IsDocked  
 現在のウィンドウがドッキングされているかどうかを決定します。  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング可能ペインがミニフレーム ウィンドウに属していないか、別のペインを持つミニフレーム ウィンドウでフローティング状態ができます。 `FALSE`場合は、ウィンドウはミニフレーム ウィンドウの子であり、ミニフレーム ウィンドウに属する他のペインではありません。  
  
### <a name="remarks"></a>コメント  
 メイン フレーム ウィンドウに、ウィンドウがドッキングされているかどうかを確認するのには、呼び出す[CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)します。 メソッドが NULL ポインターを返す場合は、メイン フレーム ウィンドウに、ウィンドウがドッキングされています。  
  
##  <a name="ishideinautohidemode"></a>CDockablePane::IsHideInAutoHideMode  
 これを示すように (または非表示) を呼び出している場合、自動非表示モードになっているウィンドウの動作を決定[CDockablePane::ShowPane](#showpane)します。  
  
```  
virtual BOOL IsHideInAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`自動非表示モードの場合、ドッキング可能ペインを非表示にする場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能ペインは、自動非表示モードでは、動作が異なるを呼び出すと`ShowPane`ウィンドウを表示または非表示にします。 この動作は、静的なメンバーによって制御されます[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)します。 このメンバーは場合`TRUE`、ドッキング可能ペインおよび関連する自動的に隠すツールバーや [自動的に隠す] ボタンを非表示またはを呼び出すと`ShowPane`です。 それ以外の場合、ドッキング可能ペインがアクティブ化または非アクティブ化し、その関連自動的に隠すツールバーまたは自動的に隠す ボタンは常に表示します。  
  
 各ペインの既定の動作を変更する派生クラスでは、このメソッドをオーバーライドします。  
  
 `m_bHideInAutoHideMode` の既定値は `FALSE` です。  
  
##  <a name="isinfloatingmultipaneframewnd"></a>CDockablePane::IsInFloatingMultiPaneFrameWnd  
 ウィンドウが複数ペインのフレーム ウィンドウかどうかを指定 ( [CMultiPaneFrameWnd クラス](../../mfc/reference/cmultipaneframewnd-class.md))。  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`複数ペインのフレーム ウィンドウには、ペインは場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isresizable"></a>CDockablePane::IsResizable  
 ウィンドウがサイズ変更可能かどうかを指定します。  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウがサイズを変更できる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 既定では、ドッキング可能ペインのサイズは変更できます。 サイズ変更を防ぐためには、派生クラスでは、このメソッドをオーバーライドし、返す`FALSE`します。 注意してください、`FALSE`値が発生したエラーにつながる`ASSERT`で[CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane)します。 使用[CDockingManager::AddPane](../../mfc/reference/cdockingmanager-class.md#addpane)代わりに親フレーム内のペインをドッキングします。  
  
 ウィンドウ サイズを変更することはできませんがどちらも float も自動非表示モードを常に親フレームの外側にあります。  
  
##  <a name="istablocationbottom"></a>CDockablePane::IsTabLocationBottom  
 タブが上部またはウィンドウの下部にあるかどうかを指定します。  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`タブが、ウィンドウの下部にある場合`FALSE`タブが、ウィンドウの上部にある場合。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [CTabbedPane::IsTabLocationBottom](../../mfc/reference/ctabbedpane-class.md#istablocationbottom)します。  
  
##  <a name="istracked"></a>CDockablePane::IsTracked  
 ウィンドウは、ユーザーが移動されるかどうかを指定します。  
  
```  
BOOL IsTracked() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウは移動される場合それ以外の場合、`FALSE`です。  
  
##  <a name="isvisible"></a>CDockablePane::IsVisible  
 現在のウィンドウが表示されているかどうかを決定します。  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドッキング可能ペインを表示する場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能ペインが表示されているかどうかを判断するには、このメソッドを呼び出します。 このメソッドを呼び出す代わりに使用することができます[CWnd::IsWindowVisible](../../mfc/reference/cwnd-class.md#iswindowvisible)のためのテストや、`WS_VISIBLE`スタイル。 返される表示状態は、自動非表示モードを有効または無効にするかどうかとの値によって異なります、 [CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode)プロパティです。  
  
 ドッキング可能なウィンドウが自動的に隠す モードの場合と`IsHideInAutoHideMode`返します`FALSE`可視性の状態は常に`FALSE`します。  
  
 ドッキング可能なウィンドウが自動的に隠す モードの場合と`IsHideInAutoHideMode`返します`TRUE`表示状態は、関連する自動的に隠すツールバーの表示状態に依存します。  
  
 表示/非表示状態の判断基準、ドッキング可能なペインが自動非表示モードでない場合、 [CBasePane::IsVisible](../../mfc/reference/cbasepane-class.md#isvisible)メソッドです。  
  
##  <a name="m_bdisableanimation"></a>CDockablePane::m_bDisableAnimation  
 ドッキング可能なウィンドウのアニメーションを自動的に隠す が無効になっているかどうかを指定します。  
  
```  
AFX_IMPORT_DATA static BOOL m_bDisableAnimation;  
```  
  
##  <a name="m_bhideinautohidemode"></a>CDockablePane::m_bHideInAutoHideMode  
 ウィンドウが自動非表示モードの場合は、ウィンドウの動作を決定します。  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideInAutoHideMode;  
```  
  
### <a name="remarks"></a>コメント  
 この値は、アプリケーション内のすべてのドッキング ペインに影響します。  
  
 このメンバーを設定する場合は、 `TRUE`、ドッキング可能ペインを非表示またはを呼び出すと、関連する自動的に隠すツールバーとボタンで示された[CDockablePane::ShowPane](#showpane)します。  
  
 このメンバーを設定する場合は、 `FALSE`、ドッキング可能ペインがアクティブ化またはを呼び出すときに非アクティブ化[CDockablePane::ShowPane](#showpane)します。  
  
##  <a name="m_nslidesteps"></a>CDockablePane::m_nSlideSteps  
 自動非表示モードにあるときは、ウィンドウのアニメーションの速度を指定します。  
  
```  
AFX_IMPORT_DATA static int m_nSlideSteps;  
```  
  
### <a name="remarks"></a>コメント  
 アニメーション効果を高速化するには、この値を小さきます。 低速のアニメーション効果では、この値を大ききます。  
  
##  <a name="onafterchangeparent"></a>CDockablePane::OnAfterChangeParent  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndOldParent`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onafterdockfromminiframe"></a>CDockablePane::OnAfterDockFromMiniFrame  
 フレーム ウィンドウのフローティング、ドッキング バーをドッキングすると、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterDockFromMiniFrame();
```  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは何もしません。  
  
##  <a name="onbeforechangeparent"></a>CDockablePane::OnBeforeChangeParent  
 フレームワークは、ウィンドウの親を変更する前に、このメソッドを呼び出します。  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndNewParent`  
 新しい親ウィンドウへのポインター。  
  
 [入力] `bDelay`  
 `BOOL`ウィンドウがドッキングされていない場合のドッキング レイアウトの再計算を延期するかどうかを指定します。 詳細については、次を参照してください。 [CDockablePane::UndockPane](#undockpane)します。  
  
### <a name="remarks"></a>コメント  
 ペインのドッキングし、を新しい親がドッキングを許可していない場合、このメソッドには、ウィンドウがドッキング解除します。  
  
 ウィンドウはタブ付きドキュメントに変換される、このメソッドは、最近のドッキング位置を格納します。 フレームワークでは、最近のドッキング位置を使用して、ドッキングされた状態に戻す変換されるときに、ウィンドウの位置を復元します。  
  
##  <a name="onbeforefloat"></a>CDockablePane::OnBeforeFloat  
 フレームワークは、フローティング状態に遷移のペインの前にこのメソッドを呼び出します。  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectFloat`  
 フローティング状態にあるときは、ウィンドウのサイズと位置を指定します。  
  
 [入力] `dockMethod`  
 ドッキング方法を指定します。 参照してください[CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane)使用可能な値の一覧にします。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ウィンドウをフローティング状態にできることができます。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドはペインが浮動小数点数に、フレームワークによって呼び出されます。 ペインをフローティングする前に、どのような処理を実行する場合、派生クラスでは、このメソッドをオーバーライドすることができます。  
  
##  <a name="onpressbuttons"></a>CDockablePane::OnPressButtons  
 ユーザー以外のキャプション ボタンを押したときと呼ばれる、`AFX_HTCLOSE`と`AFX_HTMAXBUTTON`ボタン。  
  
```  
virtual void OnPressButtons(UINT nHit);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nHit`  
 このパラメーターは使用されません。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能ペインのキャプションにカスタム ボタンを追加する場合は、ユーザーがボタンを押したときに通知を受信するには、このメソッドをオーバーライドします。  
  
##  <a name="onslide"></a>CDockablePane::OnSlide  
 自動非表示モードにあるときに、ウィンドウをアニメーション化するために、フレームワークによって呼び出されます。  
  
```  
virtual void OnSlide(BOOL bSlideOut);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSlideOut`  
 `TRUE`ウィンドウを表示するには`FALSE`ウィンドウを非表示にします。  
  
### <a name="remarks"></a>コメント  
 カスタムの自動非表示の効果を実装する派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="removefromdefaultpanedividier"></a>CDockablePane::RemoveFromDefaultPaneDividier  
 フレームワークは、ペインのドッキングを解除中にこのメソッドを呼び出します。  
  
```  
void RemoveFromDefaultPaneDividier();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、既定の分割線を設定`NULL`し、コンテナーから、ウィンドウを削除します。  
  
##  <a name="replacepane"></a>CDockablePane::ReplacePane  
 指定したウィンドウで、ウィンドウを置き換えます。  
  
```  
BOOL ReplacePane(
    CDockablePane* pBarToReplaceWith,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bRegisterWithFrame = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBarToReplaceWith`  
 ドッキング可能ペインへのポインター。  
  
 [入力] `dockMethod`  
 使用しません。  
  
 [入力] `bRegisterWithFrame`  
 場合`TRUE`、新規作成 ウィンドウは、親の古いウィンドウのドッキング マネージャーに登録されます。 新規作成 ウィンドウは、古いウィンドウ ドッキング マネージャーによって管理されているウィンドウの一覧でのインデックスに挿入されます。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`交換作業が正常に終了した場合それ以外の場合、`FALSE`です。  
  
##  <a name="restoredefaultpanedivider"></a>CDockablePane::RestoreDefaultPaneDivider  
 ペインが逆シリアル化されるときに、フレームワークは、既定ペイン分割バーを復元するには、このメソッドを呼び出します。  
  
```  
void RestoreDefaultPaneDivider();
```  
  
### <a name="remarks"></a>コメント  
 元に戻した既定ペイン分割バーでは、存在する場合、現在の既定ペイン分割バーが置き換えられます。  
  
##  <a name="setautohidemode"></a>CDockablePane::SetAutoHideMode  
 ドッキング ペインの表示を切り替えると自動的に隠すモードです。  
  
```  
virtual CMFCAutoHideBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bMode`  
 `TRUE`自動非表示モードを有効にするには`FALSE`標準ドッキング モードを有効にします。  
  
 [入力] `dwAlignment`  
 作成する、自動的に隠す ウィンドウの配置を指定します。  
  
 [in][out]`pCurrAutoHideBar`  
 現在の自動的に隠すツールバーへのポインター。 できる`NULL`です。  
  
 [入力] `bUseTimer`  
 自動非表示モード、ユーザーが、ウィンドウを切り替えるときに自動的に隠す効果を使用するか、すぐに、ウィンドウを非表示にするかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 自動非表示モードへの切り替えによって作成され、自動的に隠すツールバーまたは`NULL`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、自動非表示モードまたは標準ドッキング モードには、ドッキング可能ペインを切り替えるには、暗証番号 (pin) ボタンをクリックすると、このメソッドを呼び出します。  
  
 プログラムを使用して、自動非表示モードにドッキング可能ペインを切り替えるには、このメソッドを呼び出します。 メイン フレーム ウィンドウに、ウィンドウをドッキングする必要があります ( [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)への有効なポインターを返す必要があります、 [CPaneDivider](../../mfc/reference/cpanedivider-class.md))。  
  
##  <a name="setautohideparents"></a>CDockablePane::SetAutoHideParents  
 自動的に隠す ボタンをクリックし、ウィンドウの自動的に隠すツールバーを設定します。  
  
```  
void SetAutoHideParents(
    CMFCAutoHideBar* pToolBar,  
    CMFCAutoHideButton* pBtn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pToolBar`  
 自動的に隠すツールバーへのポインター。  
  
 [入力] `pBtn`  
 自動的に隠すボタンへのポインター。  
  
##  <a name="setlastpercentinpanecontainer"></a>CDockablePane::SetLastPercentInPaneContainer  
 コンテナーのペインを占有する領域の割合を設定します。  
  
```  
void SetLastPercentInPaneContainer(int n);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `n`  
 `int`コンテナー内のウィンドウを占有する領域の割合を指定します。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、レイアウトを再計算時に、新しい値を使用するウィンドウを調整します。  
  
##  <a name="setrestoreddefaultpanedivider"></a>CDockablePane::SetRestoredDefaultPaneDivider  
 復元された既定の分割線を設定します。  
  
```  
void SetRestoredDefaultPaneDivider(HWND hRestoredSlider);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hRestoredSlider`  
 ペイン分割バー (スライダー) へのハンドル。  
  
### <a name="remarks"></a>コメント  
 ペインが逆シリアル化されるときに、元に戻した既定ペインの区分線が取得されます。 詳細については、次を参照してください。 [CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)します。  
  
##  <a name="settabbedpanertc"></a>CDockablePane::SetTabbedPaneRTC  
 2 つのウィンドウがドッキング時に作成されるタブ付きウィンドウのランタイム クラス情報を設定します。  
  
```  
void SetTabbedPaneRTC(CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pRTC`  
 タブ付きペインのランタイム クラス情報。  
  
### <a name="remarks"></a>コメント  
 動的に作成されたタブ付きペインのランタイム クラス情報を設定するには、このメソッドを呼び出します。 これは、ユーザーが別のペインのキャプションに&1; つのペインをドラッグまたはを呼び出す場合に発生することができます、 [CDockablePane::AttachToTabWnd](#attachtotabwnd)メソッドをプログラムによって&2; つのドッキング可能ペインからタブ付きペインを作成します。  
  
 既定のランタイム クラスの設定」の手順に従って、`dwTabbedStyle`のパラメーター [CDockablePane::Create](#create)と[CDockablePane::CreateEx](#createex)します。 新しいタブ付きペインをカスタマイズするには、クラスを次のいずれかからクラスを派生します。  
  
- [CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)  
  
- [派生クラス](../../mfc/reference/ctabbedpane-class.md)  
  
- [あります](../../mfc/reference/cmfcoutlookbar-class.md)します。  
  
 次に、そのランタイム クラス情報へのポインターがこのメソッドを呼び出します。  
  
##  <a name="showpane"></a>CDockablePane::ShowPane  
 ペインの表示と非表示を切り替えます。  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
 `TRUE`ウィンドウを表示するには`FALSE`ウィンドウを非表示にします。  
  
 [入力] `bDelay`  
 `TRUE`後で、ドッキング レイアウトを調整するには`FALSE`をすぐにドッキング レイアウトを調整します。  
  
 [入力] `bActivate`  
 `TRUE`表示されたときにウィンドウをアクティブにするにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 代わりにこのメソッドを呼び出して、[また](../../mfc/reference/cwnd-class.md#showwindow)のドッキング可能ペインの表示と非表示とします。  
  
##  <a name="slide"></a>CDockablePane::Slide  
 自動非表示モードになっているウィンドウをアニメーション化します。  
  
```  
virtual void Slide(
    BOOL bSlideOut,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSlideOut`  
 `TRUE`ウィンドウを表示するには`FALSE`ウィンドウを非表示にします。  
  
 [入力] `bUseTimer`  
 `TRUE`自動非表示の効果を持つペインの表示と非表示`FALSE`またはすぐに、ウィンドウを非表示にします。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、自動非表示モードになっているウィンドウをアニメーション化するには、このメソッドを呼び出します。  
  
 このメソッドを使用して、`CDockablePane::m_nSlideDefaultTimeOut`スライド効果のタイムアウトを決定する値。 タイムアウトの既定値は 1 です。 自動的に隠すアルゴリズムをカスタマイズする場合は、タイムアウトを変更するには、このメンバーを変更します。  
  
##  <a name="toggleautohide"></a>CDockablePane::ToggleAutoHide  
 表示されている間、常にウィンドウと自動非表示モードを切り替えます。  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出して、ウィンドウの自動非表示モードを切り替えます[CDockablePane::SetAutoHideMode](#setautohidemode)します。  
  
##  <a name="undockpane"></a>CDockablePane::UndockPane  
 メイン フレーム ウィンドウまたはミニフレーム ウィンドウのコンテナーのいずれかからウィンドウをドッキング解除します。  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDelay`  
 `TRUE`後で、ドッキング レイアウトを計算するには`FALSE`をドッキング レイアウトをすぐに再計算します。  
  
### <a name="remarks"></a>コメント  
 メイン フレーム ウィンドウまたはマルチ ミニフレーム ウィンドウのコンテナー (その他のペインを含む単一のミニフレーム ウィンドウのフローティング ウィンドウ) から、ウィンドウのドッキングを解除するには、このメソッドを呼び出します。  
  
 実行されていない、外部の操作を実行する前に、ペインをドッキング解除する必要があります、 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)します。 たとえばに移動するプログラムを使用して&1; つの場所から別のウィンドウのドッキングを解除する必要があります。  
  
 フレームワークは破棄される前に自動的にウィンドウをドッキング解除します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPane クラス](../../mfc/reference/cpane-class.md)

