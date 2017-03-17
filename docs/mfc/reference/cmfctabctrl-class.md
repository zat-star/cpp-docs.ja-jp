---
title: "CMFCTabCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl::ActivateMDITab
- AFXTABCTRL/CMFCTabCtrl::AllowDestroyEmptyTabbedPane
- AFXTABCTRL/CMFCTabCtrl::AutoSizeWindow
- AFXTABCTRL/CMFCTabCtrl::CalcRectEdit
- AFXTABCTRL/CMFCTabCtrl::Create
- AFXTABCTRL/CMFCTabCtrl::EnableActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::EnableInPlaceEdit
- AFXTABCTRL/CMFCTabCtrl::EnableTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::EnsureVisible
- AFXTABCTRL/CMFCTabCtrl::GetDocumentIcon
- AFXTABCTRL/CMFCTabCtrl::GetFirstVisibleTabNum
- AFXTABCTRL/CMFCTabCtrl::GetResizeMode
- AFXTABCTRL/CMFCTabCtrl::GetScrollBar
- AFXTABCTRL/CMFCTabCtrl::GetTabArea
- AFXTABCTRL/CMFCTabCtrl::GetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::GetTabsHeight
- AFXTABCTRL/CMFCTabCtrl::GetTabsRect
- AFXTABCTRL/CMFCTabCtrl::GetWndArea
- AFXTABCTRL/CMFCTabCtrl::HideActiveWindowHorzScrollBar
- AFXTABCTRL/CMFCTabCtrl::HideInactiveWindow
- AFXTABCTRL/CMFCTabCtrl::HideNoTabs
- AFXTABCTRL/CMFCTabCtrl::HideSingleTab
- AFXTABCTRL/CMFCTabCtrl::IsActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::IsDrawFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatTab
- AFXTABCTRL/CMFCTabCtrl::IsLeftRightRounded
- AFXTABCTRL/CMFCTabCtrl::IsMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsOneNoteStyle
- AFXTABCTRL/CMFCTabCtrl::IsSharedScroll
- AFXTABCTRL/CMFCTabCtrl::IsTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::IsVS2005Style
- AFXTABCTRL/CMFCTabCtrl::ModifyTabStyle
- AFXTABCTRL/CMFCTabCtrl::OnDragEnter
- AFXTABCTRL/CMFCTabCtrl::OnDragOver
- AFXTABCTRL/CMFCTabCtrl::OnShowTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::SetActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::SetActiveTab
- AFXTABCTRL/CMFCTabCtrl::SetActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::SetDrawFrame
- AFXTABCTRL/CMFCTabCtrl::SetFlatFrame
- AFXTABCTRL/CMFCTabCtrl::SetImageList
- AFXTABCTRL/CMFCTabCtrl::SetResizeMode
- AFXTABCTRL/CMFCTabCtrl::SetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::StopResize
- AFXTABCTRL/CMFCTabCtrl::SynchronizeScrollBar
- AFXTABCTRL/CMFCTabCtrl::m_bEnableActivate
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabCtrl::SwapTabs method
- CMFCTabCtrl constructor
- CMFCTabCtrl::MoveTab method
- CMFCTabCtrl::GetTabFromPoint method
- CMFCTabCtrl::PreTranslateMessage method
- CMFCTabCtrl::RecalcLayout method
- CMFCTabCtrl class
- CMFCTabCtrl::IsPtInTabArea method
ms.assetid: d441385d-2c72-4203-96fa-deae2273da35
caps.latest.revision: 33
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
ms.openlocfilehash: 595ff7fbcd55f3b756ce650e02b6247b898d7629
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctabctrl-class"></a>CMFCTabCtrl Class
`CMFCTabCtrl`クラスには、タブ コントロールの機能が用意されています。 タブ コントロールは、上または下にフラットまたは&3;D のタブを持つ、ドッキング可能なウィンドウを表示します。 タブにはテキストとイメージを表示でき、アクティブな状態のときに色を変更することもできます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCTabCtrl::CMFCTabCtrl`|既定のコンストラクター|  
|`CMFCTabCtrl::~CMFCTabCtrl`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCTabCtrl::ActivateMDITab](#activatemditab)|現在のタブ コントロールの指定したタブを表示し、そのタブにフォーカスを設定します。|  
|[CMFCTabCtrl::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)||  
|[CMFCTabCtrl::AutoSizeWindow](#autosizewindow)|フレームワークがときに、タブ コントロールの変更のユーザー インターフェイス要素のタブ コントロール ウィンドウのすべてのクライアント領域のサイズを変更するかどうかを指定します。|  
|[CMFCTabCtrl::CalcRectEdit](#calcrectedit)|指定したタブ領域のサイズを縮小します。 (`CMFCBaseTabCtrl::CalcRectEdit` をオーバーライドします)。|  
|[CMFCTabCtrl::Create](#create)|タブ コントロールを作成し、それをアタッチ、`CMFCTabCtrl`オブジェクトです。|  
|`CMFCTabCtrl::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](#enableactivetabclosebutton)|[閉じる] ボタンの表示と非表示を切り替えます ( **X**) アクティブなタブにします。|  
|[CMFCTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|有効またはラベルの編集可能なタブを無効にします。 (上書き[CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit))。|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu)|タブ付きウィンドウのメニューを開く ボタンをウィンドウのタブをスクロールする&2; つのボタンに置き換えます。|  
|[CMFCTabCtrl::EnsureVisible](#ensurevisible)|タブが表示されるようにします。|  
|[CMFCTabCtrl::GetDocumentIcon](#getdocumenticon)|タブ付きウィンドウのポップアップ メニューのタブに関連付けられているシンボルを取得します。|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](#getfirstvisibletabnum)|現在のタブ コントロールに表示されている最初のタブのインデックスを取得します。|  
|[CMFCTabCtrl::GetResizeMode](#getresizemode)|現在のタブ コントロールのサイズを変更できる方法を指定する値を取得します。|  
|[CMFCTabCtrl::GetScrollBar](#getscrollbar)|タブ コントロールに関連付けられているスクロール バー オブジェクトへのポインターを取得します。|  
|[CMFCTabCtrl::GetTabArea](#gettabarea)|上部またはタブ コントロールの下部にあるタブ ラベル領域に外接する四角形を取得します。 (上書き[CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea))。|  
|`CMFCTabCtrl::GetTabFromPoint`|指定したポイントを含むタブを取得します。 (上書き[CMFCBaseTabCtrl::GetTabFromPoint](../../mfc/reference/cmfcbasetabctrl-class.md#gettabfrompoint))。|  
|[CMFCTabCtrl::GetTabMaxWidth](#gettabmaxwidth)|タブの最大幅を取得します。|  
|[CMFCTabCtrl::GetTabsHeight](#gettabsheight)|現在のタブ コントロールのタブ領域の高さを取得します。|  
|[CMFCTabCtrl::GetTabsRect](#gettabsrect)|現在のタブ コントロールのタブ領域に外接する四角形を取得します。 (上書き[CMFCBaseTabCtrl::GetTabsRect](../../mfc/reference/cmfcbasetabctrl-class.md#gettabsrect))。|  
|`CMFCTabCtrl::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCTabCtrl::GetWndArea](#getwndarea)|現在のタブ コントロールのクライアント領域の境界を取得します。|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar)|アクティブなウィンドウの存在する場合は、水平スクロール バーを非表示にします。|  
|[CMFCTabCtrl::HideInactiveWindow](#hideinactivewindow)|フレームワークは、非アクティブなタブ コントロール ウィンドウを表示するかどうかを指定します。|  
|[CMFCTabCtrl::HideNoTabs](#hidenotabs)|有効または表示されているタブがない場合、タブ領域の描画を無効にします。|  
|[CMFCTabCtrl::HideSingleTab](#hidesingletab)|有効または&1; つのタブ付きウィンドウがある場合は、タブを描画を無効にします。 (上書き[CMFCBaseTabCtrl::HideSingleTab](../../mfc/reference/cmfcbasetabctrl-class.md#hidesingletab))。|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](#isactiveinmditabgroup)|タブ コントロールの現在のタブがマルチ ドキュメント インターフェイスのタブ グループのアクティブなタブであるかどうかを示します。|  
|[CMFCTabCtrl::IsActiveTabBoldFont](#isactivetabboldfont)|太字のフォントを使用して、アクティブなタブのテキストを表示するかどうかを示します。|  
|[CMFCTabCtrl::IsActiveTabCloseButton](#isactivetabclosebutton)|示すかどうか、閉じるボタン ( **X**) がアクティブなタブまたはタブ領域の右上隅に表示されます。|  
|[CMFCTabCtrl::IsDrawFrame](#isdrawframe)|タブ付きウィンドウが埋め込みペインの周囲のフレームの四角形を描画するかどうかを示します。|  
|[CMFCTabCtrl::IsFlatFrame](#isflatframe)|タブ領域の周りにフレームをフラットまたは 3D にするかどうかを示します。|  
|[CMFCTabCtrl::IsFlatTab](#isflattab)|現在のタブ コントロールのタブの外観がフラットかどうかを示します。|  
|[CMFCTabCtrl::IsLeftRightRounded](#isleftrightrounded)|現在のタブ コントロールのタブの右側にある左右の外観が丸められるかどうかを示します。|  
|[CMFCTabCtrl::IsMDITabGroup](#ismditabgroup)|マルチ ドキュメント インターフェイス ウィンドウのクライアント領域の現在のタブ コントロールが含まれているかどうかを示します。|  
|[CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle)|Microsoft OneNote のスタイルで現在のタブ コントロールを表示するかどうかを示します。|  
|`CMFCTabCtrl::IsPtInTabArea`|かどうか、ポイントは、タブ領域の内部を決定します。 (上書き[CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea))。|  
|[CMFCTabCtrl::IsSharedScroll](#issharedscroll)|現在のタブ コントロールがグループとしてのタブをスクロールできるスクロール バーを持つかどうかを示します。|  
|[CMFCTabCtrl::IsTabDocumentsMenu](#istabdocumentsmenu)|タブ コントロールはスクロール ボタンまたはタブ付きウィンドウのメニューを表示するボタンを表示するかどうかを示します。|  
|[CMFCTabCtrl::IsVS2005Style](#isvs2005style)|Visual Studio .NET 2005 のスタイルでのタブを表示するかどうかを示します。|  
|[CMFCTabCtrl::ModifyTabStyle](#modifytabstyle)|現在のタブ コントロールのタブの外観を指定します。|  
|`CMFCTabCtrl::MoveTab`|タブを別のタブ位置に移動します。 (上書き[CMFCBaseTabCtrl::MoveTab](../../mfc/reference/cmfcbasetabctrl-class.md#movetab))。|  
|[CMFCTabCtrl::OnDragEnter](#ondragenter)|カーソルが最初に、タブ コントロール ウィンドウにドラッグされたときに、フレームワークによって呼び出されます。|  
|[CMFCTabCtrl::OnDragOver](#ondragover)|マウスをドロップ ターゲットのウィンドウに移動するドラッグ操作中に、フレームワークが呼び出します。 (上書き[CMFCBaseTabCtrl::OnDragOver](../../mfc/reference/cmfcbasetabctrl-class.md#ondragover))。|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](#onshowtabdocumentsmenu)|ユーザーがタブを選択し、選択されているタブは、アクティブなタブまで待機する、タブ付きウィンドウのポップアップ メニューを表示します。|  
|`CMFCTabCtrl::PreTranslateMessage`|ウィンドウのメッセージの変換にディスパッチされる前に、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数です。 (上書き[CMFCBaseTabCtrl::PreTranslateMessage](../../mfc/reference/cmfcbasetabctrl-class.md#pretranslatemessage))。|  
|`CMFCTabCtrl::RecalcLayout`|タブ コントロールの内部のレイアウトを再計算します。 (上書き[CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout))。|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](#setactiveinmditabgroup)|マルチ ドキュメント インターフェイスのタブ グループのアクティブなタブとして、タブ コントロールの現在のタブを設定します。|  
|[CMFCTabCtrl::SetActiveTab](#setactivetab)|タブをアクティブにします。 (上書き[CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab))。|  
|[CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont)|有効またはアクティブなタブでの太字のフォントの使用を無効にします。|  
|[CMFCTabCtrl::SetDrawFrame](#setdrawframe)|有効または埋め込みバーの周囲におけるフレームの四角形を無効にします。|  
|[CMFCTabCtrl::SetFlatFrame](#setflatframe)|タブ領域の周りにフラットまたは 3D のフレームを描画するかどうかを指定します。|  
|[CMFCTabCtrl::SetImageList](#setimagelist)|イメージ リストを指定します。 (上書き[CMFCBaseTabCtrl::SetImageList](../../mfc/reference/cmfcbasetabctrl-class.md#setimagelist))。|  
|[CMFCTabCtrl::SetResizeMode](#setresizemode)|現在のタブ コントロールのサイズを変更できる方法を指定し、コントロールを再表示します。|  
|[CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth)|タブ付きウィンドウでタブの最大幅を指定します。|  
|[CMFCTabCtrl::StopResize](#stopresize)|タブ コントロールの現在のサイズ変更操作を終了します。|  
|`CMFCTabCtrl::SwapTabs`|タブのペアを交換します。 (上書き[CMFCBaseTabCtrl::SwapTabs](../../mfc/reference/cmfcbasetabctrl-class.md#swaptabs))。|  
|[CMFCTabCtrl::SynchronizeScrollBar](#synchronizescrollbar)|フラット タブを表示するタブ コントロールの水平スクロール バーを描画します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCTabCtrl::m_bEnableActivate](#m_benableactivate)|アクティブなビューが新しいタブが挿入され、有効になっているときに、フォーカスを失うを防ぎます。|  
  
## <a name="remarks"></a>コメント  
 `CMFCTabCtrl`クラスでサポートします。  
  
-   3 D、平らな、およびフラット付き共有の水平スクロール バー コントロールのスタイル タブします。  
  
-   タブの上部またはウィンドウの下部にあります。  
  
-   テキスト、画像、またはテキストおよび画像が表示されるタブ。  
  
-   色を変更する、タブがアクティブなタブ。  
  
-   調整可能なタブの境界線のサイズ変更します。  
  
-   切り離し可能なタブ付きウィンドウです。  
  
 `CMFCTabCtrl`  ダイアログ ボックスでは、クラスを使用できるドッキングを使用するアプリケーションのようなバーを制御するためのものでは、[!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)]と[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]です。 詳細については、次を参照してください。 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)します。  
  
 アプリケーションでのタブ コントロールのドッキングをサイズ変更、追加するこれらの手順に従います。  
  
1.  インスタンスを作成[派生クラス](../../mfc/reference/ctabbedpane-class.md)します。  
  
2.  呼び出す[CDockablePane::Create](../../mfc/reference/cdockablepane-class.md#create)します。  
  
3.  使用[CBaseTabbedPane::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab)または[CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab)新しいタブを追加します。  
  
4.  呼び出す[CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)現在のドッキング タブ コントロールがメイン フレーム ウィンドウにドッキングできるようにします。  
  
5.  呼び出す[CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane)をメインフレームにタブ付きウィンドウをドッキングします。  
  
 タブ付きウィンドウとしてドッキング コントロール バーを作成する方法の例は、次を参照してください。[派生クラス](../../mfc/reference/ctabbedpane-class.md)します。 使用する`CMFCTabCtrl`ドッキング以外のコントロールとして作成、`CMFCTabCtrl`オブジェクトし、呼び出す[CMFCTabCtrl::Create](#create)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCTabCtrl`を構成するクラス、`CMFCTabCtrl`オブジェクトです。 この例では、タブを追加、アクティブなタブに [閉じる] ボタンを表示、編集可能なタブのラベルを有効にする、およびタブ付きウィンドウ ラベルのポップアップ メニューを表示する方法について説明します。 この例は、[状態コレクションのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_StateCollection&#1;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection&#3;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_2.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtabctrl.h  
  
##  <a name="activatemditab"></a>CMFCTabCtrl::ActivateMDITab  
 現在のタブ コントロールの指定したタブを表示し、そのタブにフォーカスを設定します。  
  
```  
void ActivateMDITab(int nTab = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nTab`  
 表示、または現在アクティブなタブを指定する場合は-1 タブの&0; から始まるインデックス。  
  
##  <a name="allowdestroyemptytabbedpane"></a>CMFCTabCtrl::AllowDestroyEmptyTabbedPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE`。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="autosizewindow"></a>CMFCTabCtrl::AutoSizeWindow  
 フレームワークがときに、タブ コントロールの変更のユーザー インターフェイス要素のタブ コントロール ウィンドウのすべてのクライアント領域のサイズを変更するかどうかを指定します。  
  
```  
void AutoSizeWindow(BOOL bAutoSize = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bAutoSize`  
 `TRUE`タブ コントロール ウィンドウを自動的にサイズを変更するそれ以外の場合、`FALSE`です。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="create"></a>CMFCTabCtrl::Create  
 タブ コントロールを作成し、それをアタッチ、`CMFCTabCtrl`オブジェクトです。  
  
```  
BOOL Create(
    Style style,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    Location location=LOCATION_BOTTOM,  
    BOOL bCloseBtn=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `style`  
 タブ コントロールのスタイル。 詳細については、「解説」を参照してください。  
  
 [入力] `rect`  
 タブ コントロールに外接する四角形。  
  
 [入力] `pParentWnd`  
 親ウィンドウへのポインター。 `NULL` にすることはできません。  
  
 [入力] `nID`  
 タブ コントロールの ID です。  
  
 [入力] `location`  
 タブの位置。 既定値は `LOCATION_BOTTOM` です。 詳細については、「解説」を参照してください。  
  
 [入力] `bCloseBtn`  
 `TRUE`[;] タブで [閉じる] ボタンを表示するにはそれ以外の場合、`FALSE`です。 既定値は `FALSE` です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`、それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 次の表に、指定できる値、`style`パラメーター。  
  
|スタイル|説明|  
|-----------|-----------------|  
|STYLE_3D|3 次元の外観をタブ コントロールを作成します。|  
|STYLE_FLAT|フラット タブをタブ コントロールを作成します。|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|フラット タブ、および親ウィンドウによってクリップされている場合、タブをスクロールできるスクロール バーで、タブ コントロールを作成します。|  
|STYLE_3D_ONENOTE|Microsoft OneNote のスタイルでは、タブ コントロールを作成します。|  
|STYLE_3D_VS2005|Microsoft Visual Studio 2005 のスタイルでは、タブ コントロールを作成します。|  
|STYLE_3D_ROUNDED|Microsoft Visual Studio 2005 のスタイルの丸められたタブをタブ コントロールを作成します。|  
|STYLE_3D_ROUNDED_SCROLL|角の丸いタブと Microsoft Visual Studio 2005 のスタイルでスクロール ボタンを含むタブ コントロールを作成します。|  
  
 次の表に指定できる値の一覧、`location`パラメーター。  
  
|場所|説明|  
|--------------|-----------------|  
|LOCATION_BOTTOM|タブは、タブ コントロールの下部にあります。|  
|LOCATION_TOP|タブは、タブ コントロールの上部にあります。|  
  
### <a name="example"></a>例  
 次の例では、使用して、`Create`メソッドで、`CMFCTabCtrl`クラスです。 この例は、[状態コレクションのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_StateCollection&#1;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection&#2;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_3.cpp)]  
  
##  <a name="calcrectedit"></a>CMFCTabCtrl::CalcRectEdit  
 指定したタブ領域のサイズを縮小します。  
  
```  
virtual void CalcRectEdit(CRect& rectEdit);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectEdit`  
 タブの領域を指定する四角形。  
  
### <a name="remarks"></a>コメント  
 タブのラベルを変更することによってこのメソッドが呼び出されます。 このメソッドは、現在タブ高さを&30; 分で指定された四角形の左側および右側を縮小し、1 単位の上下を縮小します。  
  
##  <a name="enableactivetabclosebutton"></a>CMFCTabCtrl::EnableActiveTabCloseButton  
 [閉じる] ボタンの表示と非表示を切り替えます ( **X**) アクティブなタブにします。  
  
```  
void EnableActiveTabCloseButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`アクティブなタブに [閉じる] ボタンを表示するには`FALSE`タブ領域の右上隅にある閉じるボタンを表示します。 既定値は `TRUE` です。  
  
##  <a name="enableinplaceedit"></a>CMFCTabCtrl::EnableInPlaceEdit  
 有効またはラベルの編集可能なタブを無効にします。  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`編集可能なタブのラベルを有効にするには`FALSE`編集可能なタブのラベルを無効にします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enabletabdocumentsmenu"></a>CMFCTabCtrl::EnableTabDocumentsMenu  
 ウィンドウのタブをスクロールする&2; つのボタンを使用するユーザー インターフェイスとタブ付きウィンドウのポップアップ メニューを表示するインターフェイス間で切り替えます。  
  
```  
void EnableTabDocumentsMenu(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`タブ付きウィンドウ ラベルのポップアップ メニューを表示するには`FALSE`前方または後方スクロール ボタンを表示します。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
 ユーザーには、タブのラベルがクリックすると、フレームワークに対応するタブ付きウィンドウが表示されます。 タブ ラベルが表示されている場合の位置を変更することがなく、タブ付きウィンドウが開きます。 ユーザーが、ポップアップ メニューからドキュメントを選択し、対応するタブ付きウィンドウが画面外には、タブ付きウィンドウには、最初のタブになります。  
  
##  <a name="ensurevisible"></a>CMFCTabCtrl::EnsureVisible  
 タブが表示されるようにします。  
  
```  
virtual BOOL EnsureVisible(int iTab);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iTab`  
 タブの&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`成功した場合`FALSE`場合、`iTab`パラメーターのインデックスが無効です。  
  
### <a name="remarks"></a>コメント  
 指定したタブが表示されることを保証するために、このメソッドを使用します。 必要な場合、タブ コントロールにスクロールします。  
  
##  <a name="getdocumenticon"></a>CMFCTabCtrl::GetDocumentIcon  
 タブ付きウィンドウのポップアップ メニューのタブに関連付けられているイメージを取得します。  
  
```  
static HICON __stdcall GetDocumentIcon(UINT nCmdID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nCmdID`  
 タブ付きウィンドウのポップアップ メニューのタブのコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 ビットマップ イメージのハンドル。  
  
##  <a name="getfirstvisibletabnum"></a>CMFCTabCtrl::GetFirstVisibleTabNum  
 現在のタブ コントロールに表示されている最初のタブのインデックスを取得します。  
  
```  
virtual int GetFirstVisibleTabNum() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タブ コントロールのタブの&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 Microsoft OneNote のスタイルでタブ コントロールが表示された場合のみ、このメソッドを使用します。 使用して、 [CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle)スタイルを決定する方法です。  
  
##  <a name="getresizemode"></a>CMFCTabCtrl::GetResizeMode  
 現在のタブ コントロールのサイズを変更できる方法を指定する値を取得します。  
  
```  
ResizeMode GetResizeMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 いずれか、`CMFCTabCtrl::ResizeMode`タブ コントロールのサイズを変更できる方法を指定する列挙値。 使用可能な値の一覧は、の「解説」セクションを参照してください、 [CMFCTabCtrl::SetResizeMode](#setresizemode)メソッドです。  
  
##  <a name="getscrollbar"></a>CMFCTabCtrl::GetScrollBar  
 タブ コントロールに関連付けられているスクロール バー オブジェクトへのポインターを取得します。  
  
```  
CScrollBar* GetScrollBar();
```  
  
### <a name="return-value"></a>戻り値  
 スクロール バー オブジェクトへのポインターまたは`NULL`タブ コントロールを使用して作成されていない場合、`STYLE_FLAT_SHARED_HORZ_SCROLL`スタイル。  
  
### <a name="remarks"></a>コメント  
 タブ コントロールの埋め込みのスクロール バーにアクセスするのにには、このメソッドを使用します。 タブ コントロールがある場合のみ、スクロール バー オブジェクトが作成された、`STYLE_FLAT_SHARED_HORZ_SCROLL`スタイル。  
  
##  <a name="gettabarea"></a>CMFCTabCtrl::GetTabArea  
 上部またはタブ コントロールの下部にあるタブ ラベル領域に外接する四角形を取得します。  
  
```  
void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rectTabAreaTop`  
 このメソッドが戻るとき、このリファレンスには、上部タブ ラベル領域に外接する四角形が含まれています。 四角形は、クライアント座標でです。 この参照は、タブ コントロールの上部にあるタブ ラベル領域が存在しない場合は空です。  
  
 [出力] `rectTabAreaBottom`  
 このメソッドが戻るとき、このリファレンスには、下部にあるタブ ラベル領域に外接する四角形が含まれています。 四角形は、クライアント座標でです。 この参照は、タブ コントロールの下部にあるタブ ラベル領域が存在しない場合は空です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、サイズおよびタブ付きウィンドウ内のタブ領域の位置を決定します。  
  
##  <a name="gettabmaxwidth"></a>CMFCTabCtrl::GetTabMaxWidth  
 タブの最大幅を取得します。  
  
```  
int GetTabMaxWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位でのタブの最大幅。 戻り値が 0 の場合、タブ幅を制限することはありません。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth)タブの最大幅を設定します。  
  
##  <a name="gettabsheight"></a>CMFCTabCtrl::GetTabsHeight  
 現在のタブ コントロールのタブ領域の高さを取得します。  
  
```  
virtual int GetTabsHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 いずれかのタブが表示されている、または場合は&0; タブが表示されていない場合は、タブ領域の高さ。  
  
##  <a name="gettabsrect"></a>CMFCTabCtrl::GetTabsRect  
 現在のタブ コントロールのタブ領域に外接する四角形を取得します。  
  
```  
virtual void GetTabsRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rect`  
 このメソッドが戻るとき、`rect`パラメーターには、タブ領域に外接する四角形が含まれています。  
  
##  <a name="getwndarea"></a>CMFCTabCtrl::GetWndArea  
 現在のタブ コントロールのクライアント領域の境界を取得します。  
  
```  
void GetWndArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `rect`  
 このメソッドが戻るとき、このパラメーターには、現在のタブ コントロールの外接する四角形が含まれています。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hideactivewindowhorzscrollbar"></a>CMFCTabCtrl::HideActiveWindowHorzScrollBar  
 アクティブなウィンドウに存在する場合は、水平スクロール バーを非表示にします。  
  
```  
void HideActiveWindowHorzScrollBar();
```  
  
### <a name="remarks"></a>コメント  
 タブ コントロールがユーザー コントロールのタブ ページに切り替えたときに点滅しないようにするのにには、このメソッドを使用します。  
  
##  <a name="hideinactivewindow"></a>CMFCTabCtrl::HideInactiveWindow  
 フレームワークは非アクティブなタブ コントロール ウィンドウを表示するかどうかを指定します。  
  
```  
void HideInactiveWindow(BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bHide`  
 `TRUE`は、非アクティブなウィンドウを表示しないように`FALSE`非アクティブなウィンドウを表示します。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hidenotabs"></a>CMFCTabCtrl::HideNoTabs  
 有効または表示されているタブがない場合は、タブ領域の描画を無効にします。  
  
```  
void HideNoTabs(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bHide`  
 `TRUE`タブ領域の描画を有効にするには`FALSE`描画を無効にします。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hidesingletab"></a>CMFCTabCtrl::HideSingleTab  
 有効または&1; つのタブ付きウィンドウがある場合は、タブの描画を無効にします。  
  
```  
virtual void HideSingleTab(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bHide`  
 `TRUE`1 つのタブ付きウィンドウのタブを描画しません。`FALSE`を&1; つのタブを描画します。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isactiveinmditabgroup"></a>CMFCTabCtrl::IsActiveInMDITabGroup  
 タブ コントロールの現在のタブがマルチ ドキュメント インターフェイスのタブ グループのアクティブなタブであるかどうかを示します。  
  
```  
BOOL IsActiveInMDITabGroup() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`タブ コントロールの現在のタブがアクティブなタブで、MDI のタブ グループである場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 いずれかの垂直または水平タブ グループに複数のドキュメント ウィンドウを整理し、1 つのタブ グループから別のドキュメントを簡単に移動できます。  
  
##  <a name="isactivetabboldfont"></a>CMFCTabCtrl::IsActiveTabBoldFont  
 太字のフォントを使用して、アクティブなタブのテキストを表示するかどうかを示します。  
  
```  
BOOL IsActiveTabBoldFont() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`アクティブなタブが太字のフォントで表示されている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont)アクティブなタブのフォントを変更する方法です。  
  
##  <a name="isactivetabclosebutton"></a>CMFCTabCtrl::IsActiveTabCloseButton  
 示すかどうか閉じるボタン ( **X**) が、アクティブなタブまたはタブ領域の右上隅に表示されます。  
  
```  
virtual BOOL IsActiveTabCloseButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`[閉じる] ボタンがアクティブなタブに表示されている場合`FALSE`タブ領域の右上隅にある閉じるボタンが表示されている場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isdrawframe"></a>CMFCTabCtrl::IsDrawFrame  
 タブ付きウィンドウが埋め込みペインの周囲のフレームの四角形を描画するかどうかを示します。  
  
```  
BOOL IsDrawFrame() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フレームの四角形が描画された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCTabCtrl::SetDrawFrame](#setdrawframe)メソッドを有効または無効のフレームの四角形を描画します。  
  
##  <a name="isflatframe"></a>CMFCTabCtrl::IsFlatFrame  
 タブ領域の周りにフレームをフラットまたは 3D にするかどうかを示します。  
  
```  
BOOL IsFlatFrame() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`タブ領域を囲むフレームがフラットな場合`FALSE`フレームが&3; 次元の場合。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCTabCtrl::SetFlatFrame](#setflatframe)メソッドで、フレームの描画方法を変更します。  
  
##  <a name="isflattab"></a>CMFCTabCtrl::IsFlatTab  
 現在のタブ コントロールのタブの外観がフラットかどうかを示します。  
  
```  
virtual BOOL IsFlatTab() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`現在のタブ コントロールのタブの外観がフラットな場合それ以外の場合、`FALSE`です。  
  
##  <a name="isleftrightrounded"></a>CMFCTabCtrl::IsLeftRightRounded  
 現在のタブ コントロールのタブの右側にある左右の外観が丸められるかどうかを示します。  
  
```  
virtual BOOL IsLeftRightRounded() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、それぞれのタブの両側は丸められます。それ以外の場合、`FALSE`です。  
  
##  <a name="ismditabgroup"></a>CMFCTabCtrl::IsMDITabGroup  
 マルチ ドキュメント インターフェイス ウィンドウのクライアント領域の現在のタブ コントロールが含まれているかどうかを示します。  
  
```  
virtual BOOL IsMDITabGroup() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`現在のタブ コントロールが MDI クライアント領域のウィンドウ; の場合それ以外の場合、`FALSE`です。  
  
##  <a name="isonenotestyle"></a>CMFCTabCtrl::IsOneNoteStyle  
 Microsoft OneNote のスタイルで現在のタブ コントロールを表示するかどうかを示します。  
  
```  
virtual BOOL IsOneNoteStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`タブ コントロールが Microsoft OneNote; の形式で表示された場合それ以外の場合、`FALSE`です。  
  
##  <a name="issharedscroll"></a>CMFCTabCtrl::IsSharedScroll  
 現在のタブ コントロールがグループとしてのタブをスクロールできるスクロール バーを持つかどうかを示します。  
  
```  
BOOL IsSharedScroll() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`タブ コントロールに、共有のスクロール バーがある場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドが戻る`TRUE`場合、`style`のパラメーター、 [CMFCTabCtrl::Create](#create)メソッドは STYLE_FLAT_SHARED_HORZ_SCROLL です。  
  
##  <a name="istabdocumentsmenu"></a>CMFCTabCtrl::IsTabDocumentsMenu  
 タブ コントロールはスクロール ボタンまたはタブ付きウィンドウのメニューを表示するボタンを表示するかどうかを示します。  
  
```  
BOOL IsTabDocumentsMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`タブ付きウィンドウ ラベルのポップアップ メニューを使用してタブ付きウィンドウをスクロールする場合`FALSE`場合は前方または後方スクロール ボタンを使用してタブ付きウィンドウをスクロールします。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu)タブ付きウィンドウをスクロールしてメソッドを指定します。  
  
##  <a name="isvs2005style"></a>CMFCTabCtrl::IsVS2005Style  
 Visual Studio 2005 のスタイルを使用してタブを描画するかどうかを示します。  
  
```  
virtual BOOL IsVS2005Style() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`Visual Studio 2005 でのスタイルを使用してタブが描画される場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 使用して、`style`のパラメーター、 [CMFCTabCtrl::Create](#create)タブを描画する方法を指定します。  
  
##  <a name="m_benableactivate"></a>CMFCTabCtrl::m_bEnableActivate  
 アクティブなビューが新しいタブが挿入され、有効になっているときに、フォーカスを失うを防ぎます。  
  
```  
static BOOL m_bEnableActivate;  
```  
  
### <a name="remarks"></a>コメント  
 通常、フォーカスは新しいタブ付きウィンドウによって取得されます、タブが挿入され、アクティブになったとき。 設定、`CMFCTabCtrl::m_bEnableActivate`メンバー変数に`FALSE`元のフォーカスを保持します。 既定値は `TRUE` です。  
  
##  <a name="modifytabstyle"></a>CMFCTabCtrl::ModifyTabStyle  
 現在のタブ コントロールのタブの外観を指定します。  
  
```  
BOOL ModifyTabStyle(Style style);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `style`  
 タブ コントロールの外観を指定する列挙値の&1; つ。 詳細については、「解説」表を参照してください。  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE`。  
  
### <a name="remarks"></a>コメント  
 値、`style`パラメーターは、次のいずれかを指定できます`CMFCTabCtrl::Style`列挙体です。  
  
|名前|説明|  
|----------|-----------------|  
|STYLE_3D|角が丸い&3;d の四角形のタブが表示されます。|  
|STYLE_3D_ONENOTE|1 つの側が垂直、斜めのどちらを持ち、角が丸い&3;d のタブが表示されます。|  
|STYLE_3D_ROUNDED|辺の傾斜があり、角を丸くを&3;d のタブが表示されます。|  
|STYLE_3D_ROUNDED_SCROLL|辺の傾斜があり、角を丸くを&3;d のタブが表示されます。 同時に表示できる数以上のタブがある場合、フレームワークは、ドロップダウン矢印とアクティブにするタブのメニューを表示します。|  
|STYLE_3D_SCROLLED|3d の四角形のタブが表示されます。 同時に表示できる数以上のタブがある場合、フレームワークは、ドロップダウン矢印とアクティブにするタブのメニューを表示します。|  
|STYLE_3D_VS2005|、3 d では、1 つの傾斜面と垂直の辺を&1; つに設定されているタブが丸められます。|  
|STYLE_FLAT|左辺と右辺が斜めになった&2; 次元のタブが表示されます。|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|2 次元のタブが表示されます。 同時に表示できる数以上のタブがある場合、フレームワークは、タブ領域の末尾にあるスクロール バーの矢印を表示します。|  
  
##  <a name="ondragenter"></a>CMFCTabCtrl::OnDragEnter  
 カーソルが最初に現在のタブ コントロールのウィンドウに入ったとき、ドラッグ アンド ドロップ操作中に、フレームワークが呼び出します。  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDataObject`  
 ユーザーがドラッグしたデータを格納するデータ オブジェクトへのポインター。  
  
 [入力] `dwKeyState`  
 修飾子キーの状態を格納します。 このパラメーターは、次の値のビットごとの組み合わせ (OR): `MK_CONTROL`、 `MK_SHIFT`、 `MK_ALT`、 `MK_LBUTTON`、 `MK_MBUTTON`、および`MK_RBUTTON`です。 詳細については、次を参照してください。、**メッセージ パラメーター**の[マウス入力に関する](http://msdn.microsoft.com/library/windows/desktop/ms645601)します。  
  
 [入力] `point`  
 クライアント座標でのカーソルの現在の場所が含まれています。  
  
### <a name="return-value"></a>戻り値  
 常に`DROPEFFECT_NONE`、つまり、ドロップ先がデータを受け入れることはできません。  
  
### <a name="remarks"></a>コメント  
 ドラッグ アンド ドロップ操作をサポートするのにには、このメソッドを使用します。 カスタム動作を実装するには、このメソッドをオーバーライドします。  
  
 既定では、このメソッドのみを呼び出して`CMFCTabCtrl::OnDragOver`、これは常に返します`DROPEFFECT_NONE`します。  
  
##  <a name="ondragover"></a>CMFCTabCtrl::OnDragOver  
 マウスをドロップ ターゲットのウィンドウに移動するドラッグ操作中に、フレームワークが呼び出します。  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDataObject`  
 ポインター、 [COleDataObject](../../mfc/reference/coledataobject-class.md)がドロップ先の上にドラッグされているオブジェクト。  
  
 [入力] `dwKeyState`  
 状態のビットごとの組み合わせである修飾子キー (または) `MK_CONTROL`、 `MK_SHIFT`、 `MK_ALT`、 `MK_LBUTTON`、 `MK_MBUTTON`、および`MK_RBUTTON`です。 詳細については、「メッセージ Parameters」を参照してください[マウス入力に関する](http://msdn.microsoft.com/library/windows/desktop/ms645601)します。  
  
 [入力] `point`  
 現在のマウスの位置。  
  
### <a name="return-value"></a>戻り値  
 常に `DROPEFFECT_NONE`。  
  
### <a name="remarks"></a>コメント  
 このメソッドをカスタム実装をオーバーライドします。 詳細については、次を参照してください。、[直前](../../mfc/reference/cview-class.md#ondragover)メソッドです。  
  
##  <a name="onshowtabdocumentsmenu"></a>CMFCTabCtrl::OnShowTabDocumentsMenu  
 ユーザーがタブを選択し、選択されているタブは、アクティブなタブまで待機する、タブ付きウィンドウのポップアップ メニューを表示します。  
  
```  
virtual void OnShowTabDocumentsMenu(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 ポップアップ メニューを表示する場所の座標です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setactiveinmditabgroup"></a>CMFCTabCtrl::SetActiveInMDITabGroup  
 マルチ ドキュメント インターフェイスのタブ グループのアクティブなタブとして、タブ コントロールの現在のタブを設定します。  
  
```  
void SetActiveInMDITabGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bActive`  
 `TRUE`現在のタブにアクティブなタブを作成するには`FALSE`現在のタブを非アクティブにします。  
  
### <a name="remarks"></a>コメント  
 いずれかの垂直または水平タブ グループに複数のドキュメント ウィンドウを整理し、1 つのタブ グループから別のドキュメントを簡単に移動できます。  
  
##  <a name="setactivetab"></a>CMFCTabCtrl::SetActiveTab  
 タブをアクティブにします。  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iTab`  
 アクティブ化するタブの&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`指定したタブがアクティブであるに行われた場合`FALSE`場合は、指定した`iTab`パラメーターの値が無効です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは送信しません、`AFX_WM_CHANGE_ACTIVE_TAB`タブ コントロールの親ウィンドウに通知します。  
  
 `SetActiveTab`メソッドを自動的に呼び出して、 [CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar)画面が点滅していることを防ぐためのメソッドです。  
  
##  <a name="setactivetabboldfont"></a>CMFCTabCtrl::SetActiveTabBoldFont  
 有効またはアクティブなタブでの太字のフォントの使用を無効にします。  
  
```  
void SetActiveTabBoldFont(BOOL bIsBold=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bIsBold`  
 `TRUE`太字のフォントを使用して、アクティブなタブのラベルを表示するには`FALSE`標準のフォントを使用して、ラベルを表示します。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setdrawframe"></a>CMFCTabCtrl::SetDrawFrame  
 埋め込まれたバーの周囲にフレームの四角形を描画するかどうかを指定します。  
  
```  
void SetDrawFrame(BOOL bDraw=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDraw`  
 `TRUE`埋め込みバー; の周囲のフレームの四角形を表示するにはそれ以外の場合、`FALSE`です。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setflatframe"></a>CMFCTabCtrl::SetFlatFrame  
 タブ領域の周りにフラットまたは 3D のフレームを描画するかどうかを指定します。  
  
```  
void SetFlatFrame(
    BOOL bFlat=TRUE,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bFlat`  
 `TRUE`タブ周辺フラット (2 D) フレームを描画するには`FALSE`を&3; 次元 (3 D) フレームを描画します。 既定値は `TRUE` です。  
  
 [入力] `bRepaint`  
 `TRUE`ウィンドウを直ちに再描画するにはそれ以外の場合、`FALSE`です。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setimagelist"></a>CMFCTabCtrl::SetImageList  
 イメージ リストを指定します。  
  
```  
virtual BOOL SetImageList(
    UINT uiID,  
    int cx=15,  
    COLORREF clrTransp=RGB(255, 0, 255));  
  
virtual BOOL SetImageList(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiID`  
 イメージ リストを含むビットマップ リソースの ID。  
  
 [入力] `cx`  
 各イメージには、ピクセルの幅。 既定値は 15 です。  
  
 [入力] `clrTransp`  
 透明な画像の色。 この色であるイメージの部分は透明になります。 既定値は、マゼンタ、RGB(255,0,255) です。  
  
 [入力] `hImageList`  
 読み込み済みのイメージ リストへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合。 `FALSE`タブ コントロールのフラット スタイルを使用して作成する場合、または最初のメソッドのオーバー ロードで指定されているビットマップを読み込むことができません、`uiID`パラメーター。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、タブ コントロールのイメージ リストを設定できます。 タブ ラベルの横には、イメージ リストのイメージが表示されます。 このメソッドでは、タブのサイズが、イメージとテキストの両方を含めるように、タブの高さが再計算します。  
  
 使用して、 [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)を表示するイメージのインデックスを指定するタブ コントロールによって継承されるメソッドです。  
  
##  <a name="setresizemode"></a>CMFCTabCtrl::SetResizeMode  
 現在のタブ コントロールのサイズを変更できる方法を指定し、コントロールを再表示します。  
  
```  
void SetResizeMode(ResizeMode resizeMode);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `resizeMode`  
 いずれか、`CMFCTabCtrl::ResizeMode`タブ コントロールのサイズを変更できる方法を指定する列挙値。 使用可能な値の一覧は、「解説」表を参照してください。  
  
### <a name="remarks"></a>コメント  
 `resizeMode`パラメーターは、次のいずれかを指定できます`ResizeMode`列挙値。  
  
|名前|説明|  
|----------|-----------------|  
|RESIZE_NO|タブ コントロールのサイズを変更できません。|  
|RESIZE_VERT|縦方向にしない、垂直方向に、タブ コントロールのサイズを変更できます。|  
|RESIZE_HORIZ|縦方向にしないが、水平方向に、タブ コントロールのサイズを変更できます。|  
  
##  <a name="settabmaxwidth"></a>CMFCTabCtrl::SetTabMaxWidth  
 タブ付きウィンドウでタブの最大幅を指定します。  
  
```  
void SetTabMaxWidth(int nTabMaxWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nTabMaxWidth`  
 タブの最大幅 (ピクセル単位)。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、各タブにタブ付きウィンドウの幅を制限できます。 このメソッドは、タブのラベルが非常に長い場合に便利です。 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)クラスのコンス トラクターは、実際には、幅が無制限であることを意味する 0 のタブの最大幅を初期化します。  
  
##  <a name="stopresize"></a>CMFCTabCtrl::StopResize  
 タブ コントロールの現在のサイズ変更操作を終了します。  
  
```  
void StopResize(BOOL bCancel);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bCancel`  
 `TRUE`現在のサイズ変更操作を破棄するには`FALSE`現在を完了するには、操作をサイズ変更します。 いずれの場合は、フレームワークは、サイズの四角形の描画を停止します。  
  
##  <a name="synchronizescrollbar"></a>CMFCTabCtrl::SynchronizeScrollBar  
 フラット タブを表示するタブ コントロールの水平スクロール バーを描画します。  
  
```  
BOOL SynchronizeScrollBar(SCROLLINFO* pScrollInfo = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `pScrollInfo`  
 ポインター、 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537)構造または`NULL`です。 このパラメーターがない場合、このメソッドが戻るとき`NULL`、構造体には、スクロール バーのすべてのパラメーターが含まれています。 既定値は `NULL` です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、フラットなタブを表示するタブ コントロールのみに影響します。 スクロール バーは、すべてのタブを同時に影響します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)   
 [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)

