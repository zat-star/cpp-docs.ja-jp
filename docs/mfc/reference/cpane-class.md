---
title: "CPane クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPane
- AFXPANE/CPane
- AFXPANE/CPane::AdjustSizeImmediate
- AFXPANE/CPane::AllocElements
- AFXPANE/CPane::AllowShowOnPaneMenu
- AFXPANE/CPane::CalcAvailableSize
- AFXPANE/CPane::CalcInsideRect
- AFXPANE/CPane::CalcRecentDockedRect
- AFXPANE/CPane::CalcSize
- AFXPANE/CPane::CanBeDocked
- AFXPANE/CPane::CanBeTabbedDocument
- AFXPANE/CPane::ConvertToTabbedDocument
- AFXPANE/CPane::CopyState
- AFXPANE/CPane::Create
- AFXPANE/CPane::CreateDefaultMiniframe
- AFXPANE/CPane::CreateEx
- AFXPANE/CPane::DockByMouse
- AFXPANE/CPane::DockPane
- AFXPANE/CPane::DockPaneStandard
- AFXPANE/CPane::DockToFrameWindow
- AFXPANE/CPane::DoesAllowSiblingBars
- AFXPANE/CPane::FloatPane
- AFXPANE/CPane::GetAvailableExpandSize
- AFXPANE/CPane::GetAvailableStretchSize
- AFXPANE/CPane::GetBorders
- AFXPANE/CPane::GetClientHotSpot
- AFXPANE/CPane::GetDockSiteRow
- AFXPANE/CPane::GetExclusiveRowMode
- AFXPANE/CPane::GetHotSpot
- AFXPANE/CPane::GetMinSize
- AFXPANE/CPane::GetPaneName
- AFXPANE/CPane::GetVirtualRect
- AFXPANE/CPane::IsChangeState
- AFXPANE/CPane::IsDragMode
- AFXPANE/CPane::IsInFloatingMultiPaneFrameWnd
- AFXPANE/CPane::IsLeftOf
- AFXPANE/CPane::IsResizable
- AFXPANE/CPane::IsTabbed
- AFXPANE/CPane::LoadState
- AFXPANE/CPane::MoveByAlignment
- AFXPANE/CPane::MovePane
- AFXPANE/CPane::OnAfterChangeParent
- AFXPANE/CPane::OnBeforeChangeParent
- AFXPANE/CPane::OnPressCloseButton
- AFXPANE/CPane::OnShowControlBarMenu
- AFXPANE/CPane::OnShowControlBarMenu
- AFXPANE/CPane::RecalcLayout
- AFXPANE/CPane::SaveState
- AFXPANE/CPane::SetActiveInGroup
- AFXPANE/CPane::SetBorders
- AFXPANE/CPane::SetClientHotSpot
- AFXPANE/CPane::SetDockState
- AFXPANE/CPane::SetExclusiveRowMode
- AFXPANE/CPane::SetMiniFrameRTC
- AFXPANE/CPane::SetMinSize
- AFXPANE/CPane::SetVirtualRect
- AFXPANE/CPane::StretchPaneDeferWndPos
- AFXPANE/CPane::ToggleAutoHide
- AFXPANE/CPane::UndockPane
- AFXPANE/CPane::UpdateVirtualRect
- AFXPANE/CPane::OnAfterDock
- AFXPANE/CPane::OnAfterFloat
- AFXPANE/CPane::OnBeforeDock
- AFXPANE/CPane::OnBeforeFloat
- AFXPANE/CPane::m_bHandleMinSize
- AFXPANE/CPane::m_recentDockInfo
dev_langs:
- C++
helpviewer_keywords:
- CPane class
ms.assetid: 5c651a64-3c79-4d94-9676-45f6402a6bc5
caps.latest.revision: 30
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
ms.openlocfilehash: 586133277aa4a9d89ca15cdd496a1ca7e4232632
ms.lasthandoff: 02/24/2017

---
# <a name="cpane-class"></a>CPane Class
`CPane`クラスの拡張版であるは、 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)します。 既存の MFC プロジェクトをアップグレードする場合は、出現するすべてを置き換える`CControlBar`と`CPane`です。  
  
## <a name="syntax"></a>構文  
  
```  
class CPane : public CBasePane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CPane::~CPane`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPane::AdjustSizeImmediate](#adjustsizeimmediate)|すぐに、ウィンドウのレイアウトを再計算します。|  
|[CPane::AllocElements](#allocelements)|内部使用のためには、ストレージを割り当てます。|  
|[CPane::AllowShowOnPaneMenu](#allowshowonpanemenu)|アプリケーションのウィンドウのランタイムによって生成される一覧で、ウィンドウが表示されているかどうかを指定します。|  
|[CPane::CalcAvailableSize](#calcavailablesize)|指定した四角形と現在のウィンドウの四角形のサイズの差を計算します。|  
|[CPane::CalcInsideRect](#calcinsiderect)|内部の計算の枠線とグリッパーを考慮して、ウィンドウの四角形。|  
|[CPane::CalcRecentDockedRect](#calcrecentdockedrect)|ドッキングされた最近の四角形を計算します。|  
|[CPane::CalcSize](#calcsize)|ウィンドウのサイズを計算します。|  
|[CPane::CanBeDocked](#canbedocked)|指定された基本ペインで、ペインをドッキングできるかどうかを決定します。|  
|[CPane::CanBeTabbedDocument](#canbetabbeddocument)|ペインをタブ付きドキュメントに変換できるかどうかを決定します。|  
|[CPane::ConvertToTabbedDocument](#converttotabbeddocument)|ドッキング可能ペインをタブ付きドキュメントに変換します。|  
|[CPane::CopyState](#copystate)|ペインの状態をコピーします。 (上書き[CBasePane::CopyState](../../mfc/reference/cbasepane-class.md#copystate))。|  
|[CPane::Create](#create)|コントロール バーを作成し、それをアタッチ、`CPane`オブジェクトです。|  
|[CPane::CreateDefaultMiniframe](#createdefaultminiframe)|浮動ペインのミニフレーム ウィンドウを作成します。|  
|[CPane::CreateEx](#createex)|コントロール バーを作成し、それをアタッチ、`CPane`オブジェクトです。|  
|`CPane::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CPane::DockByMouse](#dockbymouse)|メソッドをドッキング マウスを使用して、ウィンドウをドッキングします。|  
|[CPane::DockPane](#dockpane)|基本ペインをフローティング ウィンドウをドッキングします。|  
|[CPane::DockPaneStandard](#dockpanestandard)|アウトライン (標準) のドッキングを使用して、ウィンドウをドッキングします。|  
|[CPane::DockToFrameWindow](#docktoframewindow)|フレームにドッキング可能ペインをドッキングします。 (`CBasePane::DockToFrameWindow` をオーバーライドします)。|  
|[CPane::DoesAllowSiblingBars](#doesallowsiblingbars)|現在のウィンドウがドッキングされている同じ行の別のペインをドッキングするかどうかを示します。|  
|[CPane::FloatPane](#floatpane)|ペインをフローティング状態です。|  
|[CPane::GetAvailableExpandSize](#getavailableexpandsize)|(ピクセル単位) のウィンドウを拡張できる、金額を返します。|  
|[CPane::GetAvailableStretchSize](#getavailablestretchsize)|ウィンドウが縮小可能 (ピクセル単位) には、金額を返します。|  
|[CPane::GetBorders](#getborders)|ウィンドウの境界線の幅を返します。|  
|[CPane::GetClientHotSpot](#getclienthotspot)|返します。、*ホット スポット*ペインのです。|  
|[CPane::GetDockSiteRow](#getdocksiterow)|ウィンドウがドッキングされているドッキング行を返します。|  
|[CPane::GetExclusiveRowMode](#getexclusiverowmode)|ウィンドウが排他行モードであるかどうかを判断します。|  
|[CPane::GetHotSpot](#gethotspot)|根本的に格納されているホット スポットを返す`CMFCDragFrameImpl`オブジェクトです。|  
|[CPane::GetMinSize](#getminsize)|最小のウィンドウのサイズを取得します。|  
|[CPane::GetPaneName](#getpanename)|ウィンドウのタイトルを取得します。|  
|`CPane::GetResizeStep`|内部的に使用します。|  
|`CPane::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CPane::GetVirtualRect](#getvirtualrect)|取得、*仮想の長方形*ウィンドウのです。|  
|[CPane::IsChangeState](#ischangestate)|このメソッドが、基準にして他のウィンドウ ドッキング行ミニフレーム ウィンドウのウィンドウの位置を分析し、返しますが、適切なウィンドウが移動されている`AFX_CS_STATUS`値。|  
|[CPane::IsDragMode](#isdragmode)|ウィンドウがドラッグされているかどうかを指定します。|  
|[CPane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|ウィンドウが複数のウィンドウ フレーム ウィンドウかどうかを指定します。 (`CBasePane::IsInFloatingMultiPaneFrameWnd` をオーバーライドします)。|  
|[CPane::IsLeftOf](#isleftof)|(または上) に、ウィンドウを残すかどうかを決定する指定された四角形。|  
|[CPane::IsResizable](#isresizable)|ウィンドウのサイズを変更できるかどうかを決定します。 (上書き[CBasePane::IsResizable](../../mfc/reference/cbasepane-class.md#isresizable))。|  
|[CPane::IsTabbed](#istabbed)|タブ付きウィンドウのタブ コントロールに、ウィンドウが挿入されたかどうかを決定します。 (上書き[CBasePane::IsTabbed](../../mfc/reference/cbasepane-class.md#istabbed))。|  
|[CPane::LoadState](#loadstate)|レジストリから、ウィンドウの状態を読み込みます。 (上書き[CBasePane::LoadState](../../mfc/reference/cbasepane-class.md#loadstate))。|  
|[CPane::MoveByAlignment](#movebyalignment)|指定した量によっては、ペインと仮想の四角形を移動します。|  
|[CPane::MovePane](#movepane)|指定された四角形のウィンドウに移動します。|  
|[CPane::OnAfterChangeParent](#onafterchangeparent)|ウィンドウの親が変更されたときに、フレームワークによって呼び出されます。|  
|[CPane::OnBeforeChangeParent](#onbeforechangeparent)|ウィンドウの親を変更するときに、フレームワークによって呼び出されます。|  
|[CPane::OnPressCloseButton](#onpressclosebutton)|ペインのキャプションにある閉じるボタンを選択すると、フレームワークによって呼び出されます。|  
|`CPane::OnProcessDblClk`|内部的に使用します。|  
|[CPane::OnShowControlBarMenu](#onshowcontrolbarmenu)|特殊ウィンドウ メニューが表示されるときにフレームワークによって呼び出されます。|  
|[CPane::OnShowControlBarMenu](#onshowcontrolbarmenu)|特殊ウィンドウ メニューが表示されるときにフレームワークによって呼び出されます。|  
|`CPane::PrepareToDock`|内部的に使用します。|  
|[CPane::RecalcLayout](#recalclayout)|ウィンドウのレイアウト情報を再計算します。 (上書き[CBasePane::RecalcLayout](../../mfc/reference/cbasepane-class.md#recalclayout))。|  
|[CPane::SaveState](#savestate)|ウィンドウの状態をレジストリに保存します。 (上書き[CBasePane::SaveState](../../mfc/reference/cbasepane-class.md#savestate))。|  
|[CPane::SetActiveInGroup](#setactiveingroup)|アクティブ ウィンドウのフラグを設定します。|  
|[CPane::SetBorders](#setborders)|ウィンドウの境界線の値を設定します。|  
|[CPane::SetClientHotSpot](#setclienthotspot)|ペインのホット スポットを設定します。|  
|[CPane::SetDockState](#setdockstate)|ドッキング ペインの状態情報を復元します。|  
|[CPane::SetExclusiveRowMode](#setexclusiverowmode)|有効または排他行モードを無効にします。|  
|[CPane::SetMiniFrameRTC](#setminiframertc)|既定のミニフレーム ウィンドウのランタイム クラス情報を設定します。|  
|[CPane::SetMinSize](#setminsize)|ウィンドウのサイズの下限を設定します。|  
|[CPane::SetVirtualRect](#setvirtualrect)|セット、*仮想の長方形*ウィンドウのです。|  
|[CPane::StretchPaneDeferWndPos](#stretchpanedeferwndpos)|垂直方向または水平方向にドッキング スタイルに基づいて、ウィンドウを拡大します。|  
|[CPane::ToggleAutoHide](#toggleautohide)|切り替えを自動的に隠すモードです。|  
|[CPane::UndockPane](#undockpane)|ドッキング サイト、既定のスライダーまたはミニフレーム ウィンドウの現在のドッキング位置から、ウィンドウを削除します。 (上書き[CBasePane::UndockPane](../../mfc/reference/cbasepane-class.md#undockpane))。|  
|[CPane::UpdateVirtualRect](#updatevirtualrect)|仮想の四角形を更新します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPane::OnAfterDock](#onafterdock)|ペインをドッキングするときに、フレームワークによって呼び出されます。|  
|[CPane::OnAfterFloat](#onafterfloat)|ウィンドウがフローティング状態になるときに、フレームワークによって呼び出されます。|  
|[CPane::OnBeforeDock](#onbeforedock)|ウィンドウがドッキングされるときに、フレームワークによって呼び出されます。|  
|[CPane::OnBeforeFloat](#onbeforefloat)|ウィンドウがフローティングするときに、フレームワークによって呼び出されます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPane::m_bHandleMinSize](#m_bhandleminsize)|ペインの最小サイズの一貫した処理を有効にします。|  
|[CPane::m_recentDockInfo](#m_recentdockinfo)|最新のドッキング情報が含まれています。|  
  
## <a name="remarks"></a>コメント  
 通常、`CPane`オブジェクトは直接インスタンス化されません。 ドッキング機能を持つウィンドウを必要とする場合からオブジェクトを派生させる[CDockablePane](../../mfc/reference/cdockablepane-class.md)します。 ツールバー機能を必要とする場合からオブジェクトを派生させる[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)します。  
  
 クラスを派生する場合`CPane`にドッキングできる、 [CDockSite](../../mfc/reference/cdocksite-class.md)辺におよび、 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxPane.h  
  
##  <a name="adjustsizeimmediate"></a>CPane::AdjustSizeImmediate  
 すぐに、ウィンドウのレイアウトを再計算します。  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bRecalcLayout`  
 `TRUE`ペインのレイアウトを自動的に再計算するにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのレイアウトを動的に変更するときに、このメソッドを呼び出します。 たとえば、ツール バー ボタンを表示または非表示をするときに、このメソッドを呼び出す可能性があります。  
  
##  <a name="allocelements"></a>CPane::AllocElements  
 内部使用のためには、ストレージを割り当てます。  
  
```  
BOOL AllocElements(
    int nElements,  
    int cbElement);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nElements`  
 記憶域の割り当てが必要な要素の数。  
  
 [入力] `cbElement`  
 要素のバイト単位のサイズ。  
  
### <a name="return-value"></a>戻り値  
 `FALSE`メモリの割り当てが失敗するとします。それ以外の場合、`TRUE`です。  
  
##  <a name="allowshowonpanemenu"></a>CPane::AllowShowOnPaneMenu  
 アプリケーションのウィンドウのランタイムによって生成される一覧で、ウィンドウが表示されているかどうかを指定します。  
  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`は、リストで、ウィンドウが表示されている場合それ以外の場合、`FALSE`です。 基本実装を常に`TRUE`します。  
  
### <a name="remarks"></a>コメント  
 AppWizard で生成されたアプリケーションには、それに含まれるウィンドウを一覧表示するメニュー オプションが含まれています。 このメソッドは、一覧で、ウィンドウが表示されているかどうかを判断します。  
  
##  <a name="calcavailablesize"></a>CPane::CalcAvailableSize  
 指定した四角形と現在のウィンドウの四角形のサイズの差を計算します。  
  
```  
virtual CSize CalcAvailableSize(CRect rectRequired);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectRequired`  
 必要な四角形。  
  
### <a name="return-value"></a>戻り値  
 幅と高さの間の違い`rectRequired`と現在のウィンドウの四角形。  
  
##  <a name="calcinsiderect"></a>CPane::CalcInsideRect  
 内部の計算の四角形の枠線とグリッパーを含むペインです。  
  
```  
void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rect`  
 サイズとウィンドウのクライアント領域のオフセットが含まれています。  
  
 [入力] `bHorz`  
 `TRUE`ウィンドウが水平方向に指向場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのレイアウトを再計算する必要があるときに、このメソッドはフレームワークによって呼び出されます。 `rect`サイズとウィンドウのクライアント領域のオフセットでパラメーターが渡されます。 これには、境界線とグリッパーが含まれます。  
  
##  <a name="calcrecentdockedrect"></a>CPane::CalcRecentDockedRect  
 ドッキングされた最近の四角形を計算します。  
  
```  
void CalcRecentDockedRect();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、更新[CPane::m_recentDockInfo](#m_recentdockinfo)します。  
  
##  <a name="calcsize"></a>CPane::CalcSize  
 ウィンドウのサイズを計算します。  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bVertDock`  
 `TRUE`場合は、ペインは垂直方向にドッキングされている`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 このメソッドの既定の実装のサイズが返されます (0, 0)。  
  
### <a name="remarks"></a>コメント  
 派生クラスでは、このメソッドをオーバーライドする必要があります。  
  
##  <a name="canbedocked"></a>CPane::CanBeDocked  
 指定された基本ペインで、ペインをドッキングできるかどうかを判断します。  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockBar`  
 このペインをドッキング ペインを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このウィンドウは、指定のドッキング ウィンドウにドッキングできる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 通常このメソッドは指定のドッキング ペインで、ペインをドッキングできるかどうかを判断するためにフレームワークによって呼び出されます。 ウィンドウをドッキングできるかどうかを評価するメソッド ペインの現在を確認するのには、ドッキング配置を有効になります。  
  
 呼び出して、フレーム ウィンドウのさまざまな側面にドッキングを有効にした[CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)します。  
  
##  <a name="canbetabbeddocument"></a>CPane::CanBeTabbedDocument  
 ペインをタブ付きドキュメントに変換できるかどうかを判断します。  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウはタブ付きドキュメントに変換できる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 派生クラスでは、このメソッドをオーバーライドし、返す`FALSE`ウィンドウはタブ付きドキュメントに変換されないようにする場合。 タブ付きドキュメントは、ウィンドウの位置をメニューには表示されません。  
  
##  <a name="converttotabbeddocument"></a>CPane::ConvertToTabbedDocument  
 ドッキング可能ペインをタブ付きドキュメントに変換します。  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bActiveTabOnly`  
 は使用されません`CPane::ConvertToTabbedDocument`します。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能ペインだけは、タブ付きドキュメントに変換できます。 詳細については、次を参照してください。 [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument)します。  
  
##  <a name="copystate"></a>CPane::CopyState  
 ペインの状態をコピーします。  
  
```  
virtual void CopyState(CPane* pOrgBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pOrgBar`  
 ペインへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドの状態をコピーする`pOrgBar`現在のウィンドウにします。  
  
##  <a name="create"></a>CPane::Create  
 コントロール バーを作成し、それをアタッチ、 [CPane](../../mfc/reference/cpane-class.md)オブジェクトです。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszClassName`  
 Windows クラスの名前を指定します。  
  
 [入力] `dwStyle`  
 ウィンドウのスタイル属性を指定します。 詳細については、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/window-styles.md)します。  
  
 [入力] `rect`  
 初期サイズと位置の指定、`pParentWnd`クライアント座標でのウィンドウです。  
  
 [in][out]`pParentWnd`  
 このウィンドウの親ウィンドウを指定します。  
  
 [入力] `nID`  
 ペインの ID を指定します。  
  
 [入力] `dwControlBarStyle`  
 ウィンドウのスタイルを指定します。 詳細については、次を参照してください。 [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)します。  
  
 [in][out]`pContext`  
 ウィンドウの作成のコンテキストを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインが正常に作成された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Windows のウィンドウを作成し、それにアタッチ、`CPane`オブジェクトです。  
  
 明示的に初期化されない場合[CPane::m_recentDockInfo](#m_recentdockinfo)を呼び出す前に`Create`、パラメーター`rect`浮動小数点型、または、ウィンドウをドッキングするときに四角形として使用されます。  
  
##  <a name="createdefaultminiframe"></a>CPane::CreateDefaultMiniframe  
 浮動ペインのミニフレーム ウィンドウを作成します。  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectInitial`  
 初期サイズと、ミニフレーム ウィンドウを作成するの画面座標での位置を指定します。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたミニフレーム ウィンドウです。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ペインがフローティング状態になったミニフレーム ウィンドウを作成するためにフレームワークによって呼び出されます。 ミニフレーム ウィンドウは、型にできます[CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)または型の[CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md)します。 ウィンドウがある場合、マルチ ミニフレーム ウィンドウが作成された、`AFX_CBRS_FLOAT_MULTI`スタイル。  
  
 ミニフレーム ウィンドウのランタイム クラス情報は、`CPane::m_pMiniFrameRTC`メンバーです。 派生クラスを使用すると、カスタマイズされたミニフレーム ウィンドウを作成するのに場合は、このメンバーを設定します。  
  
##  <a name="createex"></a>CPane::CreateEx  
 コントロール バーを作成し、それをアタッチ、 [CPane](../../mfc/reference/cpane-class.md)オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwStyleEx`  
 拡張ウィンドウ スタイル属性を指定します。 詳細については、次を参照してください。[拡張ウィンドウ スタイル](../../mfc/reference/extended-window-styles.md)します。  
  
 [入力] `lpszClassName`  
 Windows クラスの名前を指定します。  
  
 [入力] `dwStyle`  
 ウィンドウのスタイル属性を指定します。 詳細については、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/window-styles.md)します。  
  
 [入力] `rect`  
 初期サイズと位置の指定、`pParentWnd`クライアント座標でのウィンドウです。  
  
 [in][out]`pParentWnd`  
 このウィンドウの親ウィンドウを指定します。  
  
 [入力] `nID`  
 ペインの ID を指定します。  
  
 [入力] `dwControlBarStyle`  
 ウィンドウのスタイルを指定します。 詳細については、次を参照してください。 [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)します。  
  
 [in][out]`pContext`  
 ウィンドウの作成のコンテキストを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインが正常に作成された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Windows のウィンドウを作成し、それにアタッチ、`CPane`オブジェクトです。  
  
 明示的に初期化されない場合[CPane::m_recentDockInfo](#m_recentdockinfo)を呼び出す前に`CreateEx`、パラメーター`rect`浮動小数点型、または、ウィンドウをドッキングするときに四角形として使用されます。  
  
##  <a name="dockbymouse"></a>CPane::DockByMouse  
 マウスを使用して、ウィンドウをドッキングします。  
  
```  
virtual BOOL DockByMouse(CBasePane* pDockBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockBar`  
 このペインをドッキングするには、基本ウィンドウを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウが正常にドッキングされている場合それ以外の場合、`FALSE`です。  
  
##  <a name="dockpane"></a>CPane::DockPane  
 基本ペインをフローティング ウィンドウをドッキングします。  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pDockBar`  
 このペインをドッキングする基本ペインを指定します。  
  
 [入力] `lpRect`  
 このウィンドウがドッキングされる基本ペイン上の四角形を指定します。  
  
 [入力] `dockMethod`  
 ドッキングを使用する方法を指定します。 使用可能なオプションは次のとおりです。  
  
|オプション|説明|  
|------------|-----------------|  
|`DM_UNKNOWN`|フレームワークは、ドッキングの方法が不明の場合、このオプションを使用します。 ウィンドウでは、直前の浮動小数点の位置は保存されません。 最近の浮動小数点の位置を格納するのに必要はありませんとプログラムを使用してペインをドッキングするのには、このオプションを使用することもできます。|  
|`DM_MOUSE`|内部的に使用します。|  
|`DM_DBL_CLICK`|このオプションはグリッパーがダブルクリックされたときに使用されます。 最新のドッキング位置に、ウィンドウの位置を変更します。 ダブルクリックして、ウィンドウがドッキング解除、ウィンドウの位置が、最新の浮動小数点の位置にして変わります。|  
|`DM_SHOW`|このオプションは、プログラムを使用して、ウィンドウをドッキングするのには使用できます。 ウィンドウでは、直前の浮動小数点位置を格納します。|  
|`DM_RECT`|指定された領域で、ウィンドウがドッキングされている`lpRect`します。|  
|`DM_STANDARD`|このオプションを使用するときに、フレームワークは移動中に、アウトライン フレームとして、ウィンドウを描画します。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウが正常にドッキングされている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定されている基本ペインにウィンドウをドッキングする、`pDockBar`パラメーター。 呼び出してドッキングを可能にする必要があります最初[CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)します。  
  
##  <a name="dockpanestandard"></a>CPane::DockPaneStandard  
 アウトライン (標準) のドッキングを使用して、ウィンドウをドッキングします。  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bWasDocked`  
 `TRUE`ウィンドウがドッキングされた正常; 場合それ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 このメソッドは常に返します、`this`ポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドから派生したペインに対してのみ使用、 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)します。 詳細については、次を参照してください。 [CDockablePane::DockPaneStandard](../../mfc/reference/cdockablepane-class.md#dockpanestandard)します。  
  
##  <a name="docktoframewindow"></a>CPane::DockToFrameWindow  
 フレームにドッキング可能ペインをドッキングします。  
  
```  
virtual BOOL DockToFrameWindow(
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL,  
    DWORD dwDockFlags = DT_DOCK_LAST,  
    CBasePane* pRelativeBar = NULL,  
    int nRelativeIndex = -1,  
    BOOL bOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 ウィンドウをドッキングする親フレームの側です。  
  
 [入力] `lpRect`  
 指定したサイズです。  
  
 [入力] `dwDockFlags`  
 無視されます。  
  
 [入力] `pRelativeBar`  
 無視されます。  
  
 [入力] `nRelativeIndex`  
 無視されます。  
  
 [入力] `bOuterEdge`  
 場合`TRUE`で指定されている側にドッキング可能なその他のペインが`dwAlignment`、他のウィンドウの外側のウィンドウがドッキングされている親フレームの端に近い場所にします。 場合`FALSE`ウィンドウがクライアント領域の中央に近いドッキングされています。  
  
### <a name="return-value"></a>戻り値  
 `FALSE`場合ペイン分割バー ( [CPaneDivider クラス](../../mfc/reference/cpanedivider-class.md)) 作成以外にすることはできません`TRUE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="doesallowsiblingbars"></a>CPane::DoesAllowSiblingBars  
 現在のウィンドウがドッキングされている同じ行の別のペインをドッキングするかどうかを示します。  
  
```  
virtual BOOL DoesAllowSiblingBars() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このペインは自体と同じ行に別のウィンドウにドッキングできる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 有効にするか、呼び出すことによってこの動作を無効にする[CPane::SetExclusiveRowMode](#setexclusiverowmode)します。  
  
 既定では、ツールバーが排他行モードを無効にあり、メニュー バーが排他行モードを有効にします。  
  
##  <a name="floatpane"></a>CPane::FloatPane  
 ペインをフローティング状態です。  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod = DM_UNKNOWN,  
    bool bShow = true);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectFloat`  
 ときに移動、ウィンドウがフローティング状態の画面座標で、場所を指定します。  
  
 [入力] `dockMethod`  
 ドッキングのウィンドウがフローティング状態のときに使用する方法を指定します。 使用可能な値の一覧は、次を参照してください。 [CPane::DockPane](#dockpane)します。  
  
 [入力] `bShow`  
 `TRUE`フローティング状態になったときにウィンドウを表示するにはそれ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウが正常にフローティングする場合、またはために、ウィンドウをフローティングすることはできません[CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat)返します`FALSE`。 そうしないと、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 指定された位置にあるペインをフローティングするには、このメソッドを呼び出して、`rectFloat`パラメーター。 このメソッドは、ウィンドウの親ミニフレーム ウィンドウを自動的に作成されます。  
  
##  <a name="getavailableexpandsize"></a>CPane::GetAvailableExpandSize  
 (ピクセル単位) のウィンドウを拡張できる、金額を返します。  
  
```  
virtual int GetAvailableExpandSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 戻り値が使用可能な幅; には、ウィンドウが水平方向にドッキングされている場合それ以外の場合、戻り値は、使用可能な高さです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getavailablestretchsize"></a>CPane::GetAvailableStretchSize  
 ウィンドウが縮小可能 (ピクセル単位) には、金額を返します。  
  
```  
virtual int GetAvailableStretchSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが縮小可能 (ピクセル単位) の量。 使用可能な幅の量が、ウィンドウが水平方向にドッキングされている場合それ以外の場合、使用可能な高さになります。  
  
### <a name="remarks"></a>コメント  
 利用可能な拡張のサイズが最小のウィンドウのサイズを差し引いて計算されます ( [CPane::GetMinSize](#getminsize)) 現在のサイズから ( [CWnd::GetWindowRect](../../mfc/reference/cwnd-class.md#getwindowrect))。  
  
##  <a name="getborders"></a>CPane::GetBorders  
 ウィンドウの境界線の幅を返します。  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md)ペインの各辺のピクセルで、現在の幅を格納しているオブジェクト。 たとえばの値、`left`のメンバー、`CRect`オブジェクトは、左罫線の幅。  
  
### <a name="remarks"></a>コメント  
 境界線のサイズを設定するには、呼び出す[CPane::SetBorders](#setborders)します。  
  
##  <a name="getclienthotspot"></a>CPane::GetClientHotSpot  
 返します。、*ホット スポット*ペインのです。  
  
```  
CPoint GetClientHotSpot() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 *ホット スポット*[ウィンドウ] を選択し、ウィンドウの移動を保持するポイントです。 ドッキング位置から、ウィンドウを移動すると、滑らかなアニメーションのホット スポットが使用します。  
  
##  <a name="getdocksiterow"></a>CPane::GetDockSiteRow  
 ドッキング ステーションの行を返します ( [CDockingPanesRow クラス](../../mfc/reference/cdockingpanesrow-class.md)) で、ウィンドウがドッキングされています。  
  
```  
CDockingPanesRow* GetDockSiteRow() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A `CDockingPanesRow`* のウィンドウがドッキングされているドッキング行を指すまたは`NULL`のウィンドウがドッキングされていない場合。  
  
##  <a name="getexclusiverowmode"></a>CPane::GetExclusiveRowMode  
 かどうか、ウィンドウが排他行モードを決定します。  
  
```  
virtual BOOL GetExclusiveRowMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウが排他行モードである場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 排他行モードの詳細については、次を参照してください。 [CPane::SetExclusiveRowMode](#setexclusiverowmode)します。  
  
##  <a name="gethotspot"></a>CPane::GetHotSpot  
 根本的に格納されているホット スポットを返す`CMFCDragFrameImpl`オブジェクトです。  
  
```  
CPoint GetHotSpot() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 `CPane`クラスが含まれています、`CMFCDragFrameImpl`オブジェクト、`m_dragFrameImpl`つまり、標準ドッキング モードで、ウィンドウを動かしたときに表示される四角形の描画を担当します。 ホット スポットを使用すると、ユーザーが、ウィンドウを移動すると、現在のマウスの位置を基準とした、四角形を描画します。  
  
##  <a name="getminsize"></a>CPane::GetMinSize  
 最小のウィンドウのサイズを取得します。  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `size`  
 A`CSize`は最小サイズで塗りつぶされたオブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpanename"></a>CPane::GetPaneName  
 ウィンドウのタイトルを取得します。  
  
```  
virtual void GetPaneName(CString& strName) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `strName`  
 A`CString`キャプション名を格納するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのタイトルは、ウィンドウがドッキングまたはフローティング キャプション領域に表示されます。 ウィンドウがタブ付きグループの一部である場合は、見出し領域で、タイトルが表示されます。 タイトルが表示のウィンドウが自動非表示モードの場合、`CMFCAutoHideButton`です。  
  
##  <a name="getvirtualrect"></a>CPane::GetVirtualRect  
 取得、*仮想の長方形*ウィンドウのです。  
  
```  
void GetVirtualRect(CRect& rectVirtual) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rectVirtual`  
 A`CRect`仮想の長方形で塗りつぶされているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ウィンドウを移動すると、フレームワークは、仮想の四角形の中のウィンドウの元の位置を格納します。 フレームワークは、ウィンドウの元の位置を復元するのに仮想の四角形を使用できます。  
  
 プログラムを使用してウィンドウを移動する場合を除き、仮想四角形に関連するメソッドを呼び出す必要はありません。  
  
##  <a name="ischangestate"></a>CPane::IsChangeState  
 ウィンドウを移動、このメソッドのうち他のウィンドウ、ドッキング行およびミニフレーム ウィンドウの相対位置を分析し、適切なを返します`AFX_CS_STATUS`値。  
  
```  
virtual AFX_CS_STATUS IsChangeState(
    int nOffset,  
    CBasePane** ppTargetBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 ドッキング感度を指定します。 たとえば、内で移動するウィンドウ`nOffset`ドッキング行からのピクセルがドッキングされます。  
  
 [入力] `ppTargetBar`  
 メソッドが戻るとき`ppTargetBar`を現在のウィンドウのドッキング、オブジェクトへのポインターが含まれていますか`NULL`ドッキングが発生しない場合。  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの`AFX_CS_STATUS`値。  
  
|値|説明|  
|-----------|-----------------|  
|`CS_NOTHING`|ウィンドウは、ドッキング サイトに近くなっていません。 フレームワークは、ペインをドッキングしていません。|  
|`CS_DOCK_IMMEDIATELY`|ドッキング サイト上のペインは、`DT_IMMEDIATE`スタイルを有効にします。 フレームワークでは、すぐに、ウィンドウをドッキングします。|  
|`CS_DELAY_DOCK`|ウィンドウでは、別のドッキング ペインまたはメイン フレームの端のいずれかであるドッキング サイト上です。 移動を離したときに、フレームワークは、ウィンドウをドッキングします。|  
|`CS_DELAY_DOCK_TO_TAB`|ウィンドウでは、タブ付きウィンドウにドッキングするウィンドウをドッキング サイト上です。 これは、ウィンドウが、別のドッキング ペインのキャプションまたはタブ付きペインのタブ領域上に発生します。 移動を離したときに、フレームワークは、ウィンドウをドッキングします。|  
  
##  <a name="isdragmode"></a>CPane::IsDragMode  
 ウィンドウが移動されているかどうかを指定します。  
  
```  
virtual BOOL IsDragMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウは移動される場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isinfloatingmultipaneframewnd"></a>CPane::IsInFloatingMultiPaneFrameWnd  
 ウィンドウが複数ペインのフレーム ウィンドウかどうかを指定 ( [CMultiPaneFrameWnd クラス](../../mfc/reference/cmultipaneframewnd-class.md))。  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`複数ペインのフレーム ウィンドウには、ペインは場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 複数ペインのフレーム ウィンドウのドッキング可能なウィンドウだけができます。 したがって、`CPane::IsInFloatingMultiPaneFrameWnd`は常に返します`FALSE`します。  
  
##  <a name="isleftof"></a>CPane::IsLeftOf  
 (または上) に、ウィンドウを残すかどうかを決定する指定された四角形。  
  
```  
bool IsLeftOf(
    CRect rect,  
    bool bWindowRect = true) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 A`CRect`比較のために使用されるオブジェクト。  
  
 [入力] `bWindowRect`  
 場合`TRUE`、`rect`場合に、画面座標を格納すると想定`FALSE`、`rect`クライアント座標を持つと見なされます。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ウィンドウが水平方向にドッキングされている場合の位置を残すかどうかチェック`rect`します。 それ以外の場合、このメソッドをチェックするかどうかの場所は、上記`rect`します。  
  
##  <a name="isresizable"></a>CPane::IsResizable  
 ウィンドウがサイズ変更可能かどうかを指定します。  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウがサイズを変更できる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 基本`CPane`オブジェクトのサイズは変更されません。  
  
 ドッキングのマネージャーでは、サイズ変更可能なフラグを使用して、ウィンドウのレイアウトを調べます。 非サイズ変更可能なウィンドウが、親フレームの外側のエッジにある常になります。  
  
 非サイズ変更可能なウィンドウはドッキング コンテナー内に配置できません。  
  
##  <a name="istabbed"></a>CPane::IsTabbed  
 ペインをタブ付きウィンドウのタブ コントロールに挿入されているかどうかを決定します。  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ウィンドウがタブ付きです。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 タブ付きの状態は、浮動小数点から個別に扱われます、ドッキングされている、および状態を自動的に隠す。  
  
##  <a name="loadstate"></a>CPane::LoadState  
 レジストリから、ウィンドウの状態を読み込みます。  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 プロファイルの名前。  
  
 [入力] `nIndex`  
 プロファイルのインデックス。  
  
 [入力] `uiID`  
 ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインの状態が正常に読み込まれている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、レジストリからペインの状態を読み込むには、このメソッドを呼び出します。 によって保存された追加情報をロードする派生クラスでオーバーライド[CPane::SaveState](#savestate)します。  
  
 このメソッドをオーバーライドする場合も、基本メソッドの呼び出しを返す`FALSE`基本メソッドを返す場合`FALSE`します。  
  
##  <a name="m_bhandleminsize"></a>CPane::m_bHandleMinSize  
 ウィンドウの最小サイズの一貫した処理を有効にします。  
  
```  
AFX_IMPORT_DATA static BOOL m_bHandleMinSize;  
```  
  
### <a name="remarks"></a>コメント  
 場合は、アプリケーション内の&1; つまたは複数のドッキング ペインをオーバーライド`GetMinSize`、アプリケーションが呼び出す場合、または`SetMinSize`、この静的メンバーを設定することも`TRUE`ウィンドウのサイズを調整する方法を一貫して処理するためにフレームワークを有効にするためにします。  
  
 この値設定されている場合`TRUE`、伸縮せず、すべてのペインのサイズは、その最小サイズより小さく必要があるされます。 フレームワークは、ペインのサイズのウィンドウ領域を使用するためこの値が設定されている場合、ドッキング ペイン ウィンドウ領域のサイズを変更しないで`TRUE`します。  
  
##  <a name="m_recentdockinfo"></a>CPane::m_recentDockInfo  
 最新のドッキング情報が含まれています。  
  
```  
CRecentDockSiteInfo m_recentDockInfo;  
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、このメンバーのペインの最新のドッキング状態情報を格納します。  
  
##  <a name="movebyalignment"></a>CPane::MoveByAlignment  
 指定した量によっては、ペインと仮想の四角形を移動します。  
  
```  
BOOL MoveByAlignment(
    DWORD dwAlignment,  
    int nOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 ペインの配置を指定します。  
  
 [入力] `nOffset`  
 (ピクセル単位) のウィンドウと仮想の長方形を移動する量。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 `dwAlignment`次の値のいずれかを指定できます。  
  
|値|説明|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|フレーム ウィンドウのクライアント領域の上部にドッキングするウィンドウを使用できます。|  
|`CBRS_ALIGN_BOTTOM`|フレーム ウィンドウのクライアント領域の下部にドッキング ペインを使用できます。|  
|`CBRS_ALIGN_LEFT`|フレーム ウィンドウのクライアント領域の左側にドッキング ペインを使用できます。|  
|`CBRS_ALIGN_RIGHT`|フレーム ウィンドウのクライアント領域の右側にドッキング ペインを使用できます。|  
|`CBRS_ALIGN_ANY`|フレーム ウィンドウのクライアント領域の任意の辺にドッキング ペインを使用できます。|  
  
 場合`dwAlignment`を含む、`CBRS_ALIGN_LEFT`または`CBRS_ALIGN_RIGHT`フラグ、ペイン、および仮想の四角形は移動水平方向にしない場合は場合、`dwAlignment`が含まれています、`CBRS_ALIGN_TOP`または`CBRS_ALIGN_BOTTOM`フラグ、ペイン、および仮想の四角形を垂直方向に移動します。  
  
##  <a name="movepane"></a>CPane::MovePane  
 指定された四角形のウィンドウに移動します。  
  
```  
virtual CSize MovePane(
    CRect rectNew,  
    BOOL bForceMove,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectNew`  
 ペインの新しい四角形を指定します。  
  
 [入力] `bForceMove`  
 場合`TRUE`、このメソッドは許可されているウィンドウの最小サイズを無視 ( [CPane::GetMinSize](#getminsize))、それ以外のウィンドウは、必要に応じて調整、最小サイズが少なくともことを確認します。  
  
 [入力] `hdwp`  
 使用しません。  
  
### <a name="return-value"></a>戻り値  
 A`CSize`新旧の四角形の間の幅と高さの相違点を格納しているオブジェクト (四角形の古い – `rectNew`)。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ドッキング可能ペインに対してのみ使用されます。  
  
##  <a name="onafterchangeparent"></a>CPane::OnAfterChangeParent  
 ウィンドウの親が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pWndOldParent`  
 ペインの以前の親ウィンドウです。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ドッキングまたはフローティング操作により、ウィンドウの親が変更されたときに、framework によって呼び出されます。  
  
##  <a name="onafterdock"></a>CPane::OnAfterDock  
 ペインをドッキングするときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterDock(
    CBasePane* pBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 このパラメーターは使用されません。  
  
 [入力] `lpRect`  
 このパラメーターは使用されません。  
  
 [入力] `dockMethod`  
 このパラメーターは使用されません。  
  
##  <a name="onafterfloat"></a>CPane::OnAfterFloat  
 ウィンドウがフローティング状態になった後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterFloat();
```  
  
### <a name="remarks"></a>コメント  
 ペインがフローティング状態になった後にどのような処理を実行する場合は、派生クラスでは、このメソッドをオーバーライドすることができます。  
  
##  <a name="onbeforechangeparent"></a>CPane::OnBeforeChangeParent  
 ウィンドウの親を変更するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pWndNewParent`  
 新しい親ウィンドウを指定します。  
  
 [入力] `bDelay`  
 `TRUE`ドッキングのグローバルのレイアウト調整を遅延するにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドはフレームワークによって、ウィンドウの親が、ウィンドウの中のための変更とドッキングまたはドッキング解除します。  
  
 既定では、ウィンドウが登録されていないドッキング ペインを呼び出すことによって`CDockSite::RemovePane`します。  
  
##  <a name="onbeforedock"></a>CPane::OnBeforeDock  
 ウィンドウをドッキングするときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnBeforeDock(
    CBasePane** ppDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`ppDockBar`  
 このペインをドッキング ウィンドウを指定します。  
  
 [入力] `lpRect`  
 ドッキングする四角形を指定します。  
  
 [入力] `dockMethod`  
 ドッキング方法を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインをドッキングする場合。 関数が返した場合`FALSE`、ドッキングの操作は中止されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ウィンドウがドッキングされるときに、framework によって呼び出されます。 ペインが最後にドッキングする前に、どのような処理を実行する場合は、派生クラスでは、このメソッドをオーバーライドすることができます。  
  
##  <a name="onbeforefloat"></a>CPane::OnBeforeFloat  
 ペインが浮動小数点数に、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectFloat`  
 フローティング状態にあるときは、ウィンドウのサイズと位置を指定します。  
  
 [入力] `dockMethod`  
 ウィンドウのドッキング方法を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ウィンドウをフローティング状態にできることができます。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドはペインが浮動小数点数に、フレームワークによって呼び出されます。 ペインが最後に寄せて配置前に、どのような処理を実行する場合、派生クラスでは、このメソッドをオーバーライドすることができます。  
  
##  <a name="onpressclosebutton"></a>CPane::OnPressCloseButton  
 ユーザーがペインのキャプションの [閉じる] ボタンを押したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnPressCloseButton();
```  
  
### <a name="remarks"></a>コメント  
 押されたときに、このメソッドがフレームワークによって呼び出されます、**閉じる**ペインのキャプションのボタンをクリックします。 に関する通知を受信する、**閉じる**イベント、派生クラスでは、このメソッドをオーバーライドすることができます。  
  
##  <a name="onshowcontrolbarmenu"></a>CPane::OnShowControlBarMenu  
 特殊ウィンドウ メニューが表示されるときにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnShowControlBarMenu(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 メニューの場所を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メニューを表示する場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 メニューには、つまり、ウィンドウの動作を指定するためのいくつかの項目が含まれます:**フローティング**、**ドッキング**、**自動的に隠す**、および**を非表示に**します。 呼び出してすべてのペインのこのメニューを有効にすることができます[CDockingManager::EnableDockSiteMenu](../../mfc/reference/cdockingmanager-class.md#enabledocksitemenu)します。  
  
##  <a name="recalclayout"></a>CPane::RecalcLayout  
 ウィンドウのレイアウト情報を再計算します。  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウがドッキングされている場合、このメソッドは、ウィンドウの現在のサイズにそのサイズを設定ペインの仮想の四角形を更新します。  
  
 ウィンドウがフローティング状態の場合、このメソッドは、ミニ フレームのサイズをウィンドウのサイズを調整する親ミニフレームを通知します。 フレームワークにより、ミニフレームが少なくともウィンドウのサイズが許容される最小 ( [CPane::GetMinSize](#getminsize))、必要に応じて、ミニフレームのサイズを変更します。  
  
##  <a name="savestate"></a>CPane::SaveState  
 ウィンドウの状態をレジストリに保存します。  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 プロファイルの名前。  
  
 [入力] `nIndex`  
 プロファイルのインデックス。  
  
 [入力] `uiID`  
 ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`状態が正常に保存されている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ペインの状態をレジストリに保存するときに、このメソッドを呼び出します。 オーバーライド`SaveState`追加情報を格納する派生クラスでします。  
  
 このメソッドをオーバーライドする場合も、基本メソッドの呼び出しを返す`FALSE`基本メソッドを返す場合`FALSE`します。  
  
##  <a name="setactiveingroup"></a>CPane::SetActiveInGroup  
 アクティブ ウィンドウのフラグを設定します。  
  
```  
virtual void SetActiveInGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bActive`  
 A`BOOL`ウィンドウをアクティブとしてにフラグが付いているかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能なウィンドウが表示されるか、自動的に隠すボタンが選択されて、対応するを自動的に隠す ウィンドウがアクティブとしてマークされます。  
  
 ウィンドウに関連付けられているを自動的に隠す ボタンの外観は、2 つの要因に基づいています。 ペインがアクティブな場合は、`static``BOOL``CMFCAutoHideButton::m_bOverlappingTabs`は`TRUE`フレームワークは、およびラベルのアイコンとして自動的に隠す ボタンを表示します。 非アクティブなウィンドウでは、フレームワークによって自動的に隠す アイコンのみが表示されます。  
  
 場合`CMFCAutoHideButton::m_bOverlappingTabs`は`FALSE`、または、ウィンドウがグループにない場合は、フレームワークがおよびラベルのアイコンとして関連付けを自動的に隠す ボタンを表示します。  
  
##  <a name="setborders"></a>CPane::SetBorders  
 ウィンドウの境界線の値を設定します。  
  
```  
void SetBorders(
    int cxLeft = 0,  
    int cyTop = 0,  
    int cxRight = 0,  
    int cyBottom = 0);  
  
void SetBorders(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `cxLeft`  
 ウィンドウの左端のピクセル単位の幅を指定します。  
  
 [入力] `cyTop`  
 (ピクセル単位) ウィンドウの上罫線の幅を指定します。  
  
 [入力] `cxRight`  
 (ピクセル単位) ウィンドウの右罫線の幅を指定します。  
  
 [入力] `cyBottom`  
 (ピクセル単位) ウィンドウの下罫線の幅を指定します。  
  
 [入力] `lpRect`  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md) (ピクセル単位) の各ウィンドウの境界線の幅を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ウィンドウの境界線のサイズを設定するには、この関数を呼び出します。  
  
##  <a name="setclienthotspot"></a>CPane::SetClientHotSpot  
 セット、*ホット スポット*ペインのです。  
  
```  
void SetClientHotSpot(const CPoint& ptNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ptNew`  
 A`CPoint`新しいホット スポットを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 *ホット スポット*[ウィンドウ] を選択し、ウィンドウの移動を保持するポイントです。 ウィンドウがドッキング位置からドラッグされたときにホット スポットの滑らかなアニメーションです。  
  
##  <a name="setdockstate"></a>CPane::SetDockState  
 ドッキング ペインの状態情報を復元します。  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockManager`  
 メイン フレーム ウィンドウのドッキング マネージャーへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ペインのドッキング状態情報を最新の復元に、フレームワークによって呼び出されます。 ペインの最近のドッキング状態情報を格納する[CPane::m_recentDockInfo](#m_recentdockinfo)します。 詳細については、次を参照してください。、 [CRecentDockSiteInfo クラス](../../mfc/reference/crecentdocksiteinfo-class.md)します。  
  
 外部ソースからウィンドウの情報を読み込むときに、ドッキング状態を設定するには、このメソッドを呼び出すこともできます。  
  
##  <a name="setexclusiverowmode"></a>CPane::SetExclusiveRowMode  
 有効または排他行モードを無効にします。  
  
```  
virtual void SetExclusiveRowMode(BOOL bExclusive = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bExclusive`  
 `TRUE`排他的行モードを有効にするにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 有効または排他行モードを無効にするには、このメソッドを呼び出します。 ペインは、排他行モードに同じ行を他のツールバーと共有できません。  
  
 既定では、すべてのツールバーが排他行モードを無効にあり、メニュー バーが排他行モードを有効にします。  
  
##  <a name="setminsize"></a>CPane::SetMinSize  
 ウィンドウのサイズの下限を設定します。  
  
```  
void SetMinSize(const CSize& size);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `size`  
 A`CSize`最小のウィンドウのサイズを格納しているオブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setvirtualrect"></a>CPane::SetVirtualRect  
 セット、*仮想の長方形*ウィンドウのです。  
  
```  
void SetVirtualRect(
    const CRect& rect,  
    BOOL bMapToParent = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 A`CRect`を設定する仮想四角形を指定するオブジェクト。  
  
 [入力] `bMapToParent`  
 指定`TRUE`場合`rect`親ウィンドウの相対ポイントが含まれています。  
  
### <a name="remarks"></a>コメント  
 A*仮想の長方形*が移動されると、ウィンドウの元の位置を格納します。 フレームワークでは、仮想の四角形を使用して、元の位置を復元します。  
  
 プログラムを使用してウィンドウを移動する場合を除き、仮想四角形に関連するメソッドを呼び出す必要はありません。  
  
##  <a name="setminiframertc"></a>CPane::SetMiniFrameRTC  
 既定のミニフレーム ウィンドウのランタイム クラス情報を設定します。  
  
```  
void SetMiniFrameRTC(CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pClass`  
 ミニフレーム ウィンドウのランタイム クラス情報を指定します。  
  
### <a name="remarks"></a>コメント  
 配置するウィンドウがフローティング状態になった、 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) (ミニフレーム) ウィンドウです。 カスタムを使用できる`CPaneFrameWnd`-となるクラスを派生際に使用される[CPane::CreateDefaultMiniframe](#createdefaultminiframe)が呼び出されます。  
  
##  <a name="stretchpanedeferwndpos"></a>CPane::StretchPaneDeferWndPos  
 垂直方向または水平方向にドッキング スタイルに基づいて、ウィンドウを拡大します。  
  
```  
virtual int StretchPaneDeferWndPos(
    int nStretchSize,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nStretchSize`  
 ペインを引き伸ばすのピクセル数。 ウィンドウを縮小するのにには、負の値を使用します。  
  
 [入力] `hdwp`  
 使用しません。  
  
### <a name="return-value"></a>戻り値  
 実際の量 (ピクセル単位) のウィンドウが拡大されました。  
  
### <a name="remarks"></a>コメント  
 必要に応じて、このメソッドによって変更`nStretchSize`ウィンドウがサイズの制限を超えないことを確認します。 これらの制限は呼び出すことによって取得[CPane::GetAvailableStretchSize](#getavailablestretchsize)と[CPane::GetAvailableExpandSize](#getavailableexpandsize)します。  
  
##  <a name="toggleautohide"></a>CPane::ToggleAutoHide  
 切り替えを自動的に隠すモードです。  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>コメント  
 自動非表示モードを切り替えるには、このメソッドを呼び出します。 ペインは、自動非表示モードに切り替えるには、メイン フレーム ウィンドウにドッキングする必要があります。  
  
##  <a name="undockpane"></a>CPane::UndockPane  
 ドッキング サイト、既定のスライダーまたはミニフレーム ウィンドウの現在のドッキング位置から、ウィンドウを削除します。  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDelay`  
 場合`FALSE`、フレームワークによって[CBasePane::AdjustDockingLayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout)ドッキング レイアウトを調整します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、プログラムを使用して、ウィンドウのドッキングを解除します。  
  
##  <a name="updatevirtualrect"></a>CPane::UpdateVirtualRect  
 仮想の四角形を更新します。  
  
```  
void UpdateVirtualRect();  
void UpdateVirtualRect(CPoint ptOffset);  
  void UpdateVirtualRect(CSize sizeNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ptOffset`  
 A`CPoint`をウィンドウをシフトするオフセットを指定するオブジェクト。  
  
 [入力] `sizeNew`  
 A`CSize`ペインの新しいサイズを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 最初のオーバー ロードは、現在の位置とウィンドウのサイズを使用して仮想の四角形を設定します。  
  
 2 番目のオーバー ロードでは、仮想の四角形をシフトで指定した量だけ`ptOffset`します。  
  
 3 番目のオーバー ロードでは、仮想の四角形を設定、ウィンドウと、指定されたサイズの現在位置を使用して、`sizeNew`です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CBasePane クラス](../../mfc/reference/cbasepane-class.md)

