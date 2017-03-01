---
title: "CMFCVisualManagerWindows クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCVisualManagerWindows
dev_langs:
- C++
helpviewer_keywords:
- CMFCVisualManagerWindows class
ms.assetid: 568b6e9e-8e67-4477-9a3d-2981cbd09861
caps.latest.revision: 46
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
ms.openlocfilehash: 7b5b6a81af56dfabf733fbd5c6b018f5355164c8
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcvisualmanagerwindows-class"></a>CMFCVisualManagerWindows クラス
`CMFCVisualManagerWindows`Windows XP または Vista テーマを選択すると、Microsoft Windows XP または Microsoft Vista の外観を模倣します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCVisualManagerWindows : public CMFCVisualManagerOfficeXP  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCVisualManagerWindows::CMFCVisualManagerWindows`|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCVisualManagerWindows::AlwaysHighlight3DTabs](#alwayshighlight3dtabs)|フレームワークでは、アプリケーションで 3D のタブをハイライト常にかどうかを判断するには、このメソッドを呼び出します。 (上書き[CMFCVisualManager::AlwaysHighlight3DTabs](../../mfc/reference/cmfcvisualmanager-class.md#alwayshighlight3dtabs))。|  
|[CMFCVisualManagerWindows::DrawComboBorderWinXP](#drawcomboborderwinxp)|(`CMFCVisualManager::DrawComboBorderWinXP` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::DrawComboDropButtonWinXP](#drawcombodropbuttonwinxp)|(上書き[CMFCVisualManager::DrawComboDropButtonWinXP](../../mfc/reference/cmfcvisualmanager-class.md#drawcombodropbuttonwinxp))。|  
|[CMFCVisualManagerWindows::DrawPushButtonWinXP](#drawpushbuttonwinxp)|(上書き[CMFCVisualManager::DrawPushButtonWinXP](../../mfc/reference/cmfcvisualmanager-class.md#drawpushbuttonwinxp))。|  
|[CMFCVisualManagerWindows::GetButtonExtraBorder](#getbuttonextraborder)|フレームワークは、ツール バー ボタンを描画するときに、このメソッドを呼び出します。 (上書き[CMFCVisualManager::GetButtonExtraBorder](../../mfc/reference/cmfcvisualmanager-class.md#getbuttonextraborder))。|  
|[CMFCVisualManagerWindows::GetCaptionButtonExtraBorder](#getcaptionbuttonextraborder)|(上書き[CMFCVisualManager::GetCaptionButtonExtraBorder](../../mfc/reference/cmfcvisualmanager-class.md#getcaptionbuttonextraborder))。|  
|[CMFCVisualManagerWindows::GetDockingPaneCaptionExtraHeight](#getdockingpanecaptionextraheight)|(`CMFCVisualManager::GetDockingPaneCaptionExtraHeight` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::GetHighlightedMenuItemTextColor](#gethighlightedmenuitemtextcolor)|(`CMFCVisualManagerOfficeXP::GetHighlightedMenuItemTextColor` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::GetPopupMenuGap](#getpopupmenugap)|(`CMFCVisualManagerOfficeXP::GetPopupMenuGap` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::GetToolbarButtonTextColor](#gettoolbarbuttontextcolor)|(`CMFCVisualManagerOfficeXP::GetToolbarButtonTextColor` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::IsDefaultWinXPPopupButton](#isdefaultwinxppopupbutton)|(上書き[CMFCVisualManager::IsDefaultWinXPPopupButton](../../mfc/reference/cmfcvisualmanager-class.md#isdefaultwinxppopupbutton))。|  
|[CMFCVisualManagerWindows::IsHighlightWholeMenuItem](#ishighlightwholemenuitem)|(`CMFCVisualManagerOfficeXP::IsHighlightWholeMenuItem` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::IsOfficeStyleMenus](#isofficestylemenus)||  
|[CMFCVisualManagerWindows::IsOfficeXPStyleMenus](#isofficexpstylemenus)|ビジュアル マネージャーが Office XP スタイルのメニューを実装するかどうかを示します。 (上書き[CMFCVisualManager::IsOfficeXPStyleMenus](../../mfc/reference/cmfcvisualmanager-class.md#isofficexpstylemenus))。|  
|[CMFCVisualManagerWindows::IsWindowsThemingSupported](#iswindowsthemingsupported)|(`CMFCVisualManager::IsWindowsThemingSupported` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::IsWinXPThemeAvailable](#iswinxpthemeavailable)|Windows のテーマが使用できるかどうかを示します。 テーマは、Windows XP テーマまたは[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]テーマです。|  
|[CMFCVisualManagerWindows::OnDrawBarGripper](#ondrawbargripper)|(`CMFCVisualManagerOfficeXP::OnDrawBarGripper` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawBrowseButton](#ondrawbrowsebutton)|(`CMFCVisualManagerOfficeXP::OnDrawBrowseButton` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawButtonBorder](#ondrawbuttonborder)|(`CMFCVisualManagerOfficeXP::OnDrawButtonBorder` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawButtonSeparator](#ondrawbuttonseparator)|(`CMFCVisualManagerOfficeXP::OnDrawButtonSeparator` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawCaptionButton](#ondrawcaptionbutton)|(`CMFCVisualManagerOfficeXP::OnDrawCaptionButton` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawCaptionButtonIcon](#ondrawcaptionbuttonicon)|(`CMFCVisualManagerOfficeXP::OnDrawCaptionButtonIcon` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawCheckBoxEx](#ondrawcheckboxex)|(上書き[CMFCVisualManager::OnDrawCheckBoxEx](../../mfc/reference/cmfcvisualmanager-class.md#ondrawcheckboxex))。|  
|[CMFCVisualManagerWindows::OnDrawComboBorder](#ondrawcomboborder)|(`CMFCVisualManagerOfficeXP::OnDrawComboBorder` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawComboDropButton](#ondrawcombodropbutton)|(`CMFCVisualManagerOfficeXP::OnDrawComboDropButton` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawControlBorder](#ondrawcontrolborder)|(上書き[CMFCVisualManager::OnDrawControlBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawcontrolborder))。|  
|[CMFCVisualManagerWindows::OnDrawEditBorder](#ondraweditborder)|(`CMFCVisualManagerOfficeXP::OnDrawEditBorder` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawExpandingBox](#ondrawexpandingbox)|(上書き[CMFCVisualManager::OnDrawExpandingBox](../../mfc/reference/cmfcvisualmanager-class.md#ondrawexpandingbox))。|  
|[CMFCVisualManagerWindows::OnDrawFloatingToolbarBorder](#ondrawfloatingtoolbarborder)|(`CMFCVisualManagerOfficeXP::OnDrawFloatingToolbarBorder` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawHeaderCtrlBorder](#ondrawheaderctrlborder)|インスタンスの境界線を描画するときに、フレームワークがこのメソッドを呼び出して、 [CMFCHeaderCtrl クラス](../../mfc/reference/cmfcheaderctrl-class.md)します。 (上書き[CMFCVisualManager::OnDrawHeaderCtrlBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawheaderctrlborder))。|  
|[CMFCVisualManagerWindows::OnDrawHeaderCtrlSortArrow](#ondrawheaderctrlsortarrow)|フレームワークは、ヘッダー コントロールの並べ替えの矢印を描画するときに、この関数を呼び出します。 (上書き[CMFCVisualManager::OnDrawHeaderCtrlSortArrow](../../mfc/reference/cmfcvisualmanager-class.md#ondrawheaderctrlsortarrow))。|  
|[CMFCVisualManagerWindows::OnDrawMenuBorder](#ondrawmenuborder)|(`CMFCVisualManagerOfficeXP::OnDrawMenuBorder` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawMenuSystemButton](#ondrawmenusystembutton)|(`CMFCVisualManagerOfficeXP::OnDrawMenuSystemButton` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawMiniFrameBorder](#ondrawminiframeborder)|(`CMFCVisualManagerOfficeXP::OnDrawMiniFrameBorder` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawOutlookPageButtonBorder](#ondrawoutlookpagebuttonborder)|Outlook のページ ボタンの境界線を描画するときに、フレームワークによって呼び出されます。 (上書き[CMFCVisualManager::OnDrawOutlookPageButtonBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawoutlookpagebuttonborder))。|  
|[CMFCVisualManagerWindows::OnDrawPaneBorder](#ondrawpaneborder)|(`CMFCVisualManagerOfficeXP::OnDrawPaneBorder` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawPaneCaption](#ondrawpanecaption)|(`CMFCVisualManagerOfficeXP::OnDrawPaneCaption` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawPopupWindowButtonBorder](#ondrawpopupwindowbuttonborder)|(`CMFCVisualManagerOfficeXP::OnDrawPopupWindowButtonBorder` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawScrollButtons](#ondrawscrollbuttons)|(`CMFCVisualManagerOfficeXP::OnDrawScrollButtons` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawSeparator](#ondrawseparator)|(`CMFCVisualManagerOfficeXP::OnDrawSeparator` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawSpinButtons](#ondrawspinbuttons)|(`CMFCVisualManagerOfficeXP::OnDrawSpinButtons` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawStatusBarPaneBorder](#ondrawstatusbarpaneborder)|(`CMFCVisualManagerOfficeXP::OnDrawStatusBarPaneBorder` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawStatusBarProgress](#ondrawstatusbarprogress)|フレームワークは、進行状況インジケーターを描画するときにこのメソッドを呼び出して、 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)オブジェクトです。 (上書き[CMFCVisualManager::OnDrawStatusBarProgress](../../mfc/reference/cmfcvisualmanager-class.md#ondrawstatusbarprogress))。|  
|[CMFCVisualManagerWindows::OnDrawStatusBarSizeBox](#ondrawstatusbarsizebox)|フレームワークは、の [サイズ] ボックスを描画するときにこのメソッドを呼び出して、 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)します。 (上書き[CMFCVisualManager::OnDrawStatusBarSizeBox](../../mfc/reference/cmfcvisualmanager-class.md#ondrawstatusbarsizebox))。|  
|[CMFCVisualManagerWindows::OnDrawTab](#ondrawtab)|(`CMFCVisualManagerOfficeXP::OnDrawTab` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawTabCloseButton](#ondrawtabclosebutton)|(`CMFCVisualManagerOfficeXP::OnDrawTabCloseButton` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawTabsButtonBorder](#ondrawtabsbuttonborder)|(`CMFCVisualManagerOfficeXP::OnDrawTabsButtonBorder` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawTask](#ondrawtask)|(`CMFCVisualManagerOfficeXP::OnDrawTask` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawTasksGroupAreaBorder](#ondrawtasksgroupareaborder)|(`CMFCVisualManagerOfficeXP::OnDrawTasksGroupAreaBorder` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawTasksGroupCaption](#ondrawtasksgroupcaption)|(`CMFCVisualManagerOfficeXP::OnDrawTasksGroupCaption` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnDrawTearOffCaption](#ondrawtearoffcaption)|(`CMFCVisualManagerOfficeXP::OnDrawTearOffCaption` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnErasePopupWindowButton](#onerasepopupwindowbutton)|(`CMFCVisualManagerOfficeXP::OnErasePopupWindowButton` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnEraseTabsArea](#onerasetabsarea)|(`CMFCVisualManagerOfficeXP::OnEraseTabsArea` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnEraseTabsButton](#onerasetabsbutton)|(`CMFCVisualManagerOfficeXP::OnEraseTabsButton` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnEraseTabsFrame](#onerasetabsframe)|フレームワークは、上のフレームを消去するときにこのメソッドを呼び出して、 [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)します。 (上書き[CMFCVisualManager::OnEraseTabsFrame](../../mfc/reference/cmfcvisualmanager-class.md#onerasetabsframe))。|  
|[CMFCVisualManagerWindows::OnFillBarBackground](#onfillbarbackground)|(`CMFCVisualManagerOfficeXP::OnFillBarBackground` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnFillButtonInterior](#onfillbuttoninterior)|(`CMFCVisualManagerOfficeXP::OnFillButtonInterior` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnFillCommandsListBackground](#onfillcommandslistbackground)|(`CMFCVisualManagerOfficeXP::OnFillCommandsListBackground` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnFillMiniFrameCaption](#onfillminiframecaption)|(`CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnFillOutlookPageButton](#onfilloutlookpagebutton)|フレームワークは、Outlook のページのボタンの内部を塗りつぶすときに、このメソッドを呼び出します。 (上書き[CMFCVisualManager::OnFillOutlookPageButton](../../mfc/reference/cmfcvisualmanager-class.md#onfilloutlookpagebutton))。|  
|[CMFCVisualManagerWindows::OnFillTasksGroupInterior](#onfilltasksgroupinterior)|(`CMFCVisualManagerOfficeXP::OnFillTasksGroupInterior` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnFillTasksPaneBackground](#onfilltaskspanebackground)|背景を塗りつぶすときに、フレームワークはこのメソッドを呼び出して、 [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)コントロールです。 (上書き[CMFCVisualManager::OnFillTasksPaneBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfilltaskspanebackground))。|  
|[CMFCVisualManagerWindows::OnHighlightMenuItem](#onhighlightmenuitem)|(`CMFCVisualManagerOfficeXP::OnHighlightMenuItem` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnHighlightRarelyUsedMenuItems](#onhighlightrarelyusedmenuitems)|(`CMFCVisualManagerOfficeXP::OnHighlightRarelyUsedMenuItems` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::OnUpdateSystemColors](#onupdatesystemcolors)|(`CMFCVisualManagerOfficeXP::OnUpdateSystemColors` をオーバーライドします)。|  
|[CMFCVisualManagerWindows::SetOfficeStyleMenus](#setofficestylemenus)||  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCVisualManagerWindows::m_b3DTabsXPTheme](#m_b3dtabsxptheme)|Windows XP のテーマが 3D のタブを表示するかどうかを指定します。|  
  
## <a name="remarks"></a>コメント  
 使用して、`CMFCVisualManagerWindows`現在の Windows XP を模倣するために、アプリケーションの外観を変更するクラスまたは[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]アプリケーションを実行するコンピューター上のテーマです。  
  
 ただし、Windows のテーマが利用できないアプリケーションが Windows XP より前のバージョンの Windows で実行されている場合、またはユーザーが使用されているので、テーマが無効な場合、**クラシック**表示します。 アプリケーションで定義されている既定のビジュアル マネージャーを使用して利用可能なテーマがない場合は、 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)します。  
  
## <a name="example"></a>例  
 次の例では、使用して`CMFCVisualManagerWindows`します。 このコード スニペットの一部である、[デスクトップ アラート デモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo&#10;](../../mfc/reference/codesnippet/cpp/cmfcvisualmanagerwindows-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxvisualmanagerwindows.h  
  
##  <a name="a-namealwayshighlight3dtabsa--cmfcvisualmanagerwindowsalwayshighlight3dtabs"></a><a name="alwayshighlight3dtabs"></a>CMFCVisualManagerWindows::AlwaysHighlight3DTabs  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AlwaysHighlight3DTabs() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namecmfcvisualmanagerwindowsa--cmfcvisualmanagerwindowscmfcvisualmanagerwindows"></a><a name="cmfcvisualmanagerwindows"></a>CMFCVisualManagerWindows::CMFCVisualManagerWindows  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCVisualManagerWindows(BOOL bIsTemporary = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bIsTemporary`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namedrawcomboborderwinxpa--cmfcvisualmanagerwindowsdrawcomboborderwinxp"></a><a name="drawcomboborderwinxp"></a>CMFCVisualManagerWindows::DrawComboBorderWinXP  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DrawComboBorderWinXP(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsDropped,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bDisabled`  
 [入力] `bIsDropped`  
 [入力] `bIsHighlighted`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namedrawcombodropbuttonwinxpa--cmfcvisualmanagerwindowsdrawcombodropbuttonwinxp"></a><a name="drawcombodropbuttonwinxp"></a>CMFCVisualManagerWindows::DrawComboDropButtonWinXP  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DrawComboDropButtonWinXP(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsDropped,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bDisabled`  
 [入力] `bIsDropped`  
 [入力] `bIsHighlighted`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namedrawpushbuttonwinxpa--cmfcvisualmanagerwindowsdrawpushbuttonwinxp"></a><a name="drawpushbuttonwinxp"></a>CMFCVisualManagerWindows::DrawPushButtonWinXP  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DrawPushButtonWinXP(
    CDC* pDC,  
    CRect rect,  
    CMFCButton* pButton,  
    UINT uiState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `pButton`  
 [入力] `uiState`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetbuttonextrabordera--cmfcvisualmanagerwindowsgetbuttonextraborder"></a><a name="getbuttonextraborder"></a>CMFCVisualManagerWindows::GetButtonExtraBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetButtonExtraBorder() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetcaptionbuttonextrabordera--cmfcvisualmanagerwindowsgetcaptionbuttonextraborder"></a><a name="getcaptionbuttonextraborder"></a>CMFCVisualManagerWindows::GetCaptionButtonExtraBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetCaptionButtonExtraBorder() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetdockingpanecaptionextraheighta--cmfcvisualmanagerwindowsgetdockingpanecaptionextraheight"></a><a name="getdockingpanecaptionextraheight"></a>CMFCVisualManagerWindows::GetDockingPaneCaptionExtraHeight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetDockingPaneCaptionExtraHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegethighlightedmenuitemtextcolora--cmfcvisualmanagerwindowsgethighlightedmenuitemtextcolor"></a><a name="gethighlightedmenuitemtextcolor"></a>CMFCVisualManagerWindows::GetHighlightedMenuItemTextColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetHighlightedMenuItemTextColor(CMFCToolBarMenuButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetpopupmenugapa--cmfcvisualmanagerwindowsgetpopupmenugap"></a><a name="getpopupmenugap"></a>CMFCVisualManagerWindows::GetPopupMenuGap  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetPopupMenuGap() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegettoolbarbuttontextcolora--cmfcvisualmanagerwindowsgettoolbarbuttontextcolor"></a><a name="gettoolbarbuttontextcolor"></a>CMFCVisualManagerWindows::GetToolbarButtonTextColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetToolbarButtonTextColor(
    CMFCToolBarButton* pButton,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
 [入力] `state`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameisdefaultwinxppopupbuttona--cmfcvisualmanagerwindowsisdefaultwinxppopupbutton"></a><a name="isdefaultwinxppopupbutton"></a>CMFCVisualManagerWindows::IsDefaultWinXPPopupButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsDefaultWinXPPopupButton(CMFCDesktopAlertWndButton* pButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameishighlightwholemenuitema--cmfcvisualmanagerwindowsishighlightwholemenuitem"></a><a name="ishighlightwholemenuitem"></a>CMFCVisualManagerWindows::IsHighlightWholeMenuItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsHighlightWholeMenuItem();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameisofficestylemenusa--cmfcvisualmanagerwindowsisofficestylemenus"></a><a name="isofficestylemenus"></a>CMFCVisualManagerWindows::IsOfficeStyleMenus  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsOfficeStyleMenus() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameisofficexpstylemenusa--cmfcvisualmanagerwindowsisofficexpstylemenus"></a><a name="isofficexpstylemenus"></a>CMFCVisualManagerWindows::IsOfficeXPStyleMenus  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsOfficeXPStyleMenus() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameiswindowsthemingsupporteda--cmfcvisualmanagerwindowsiswindowsthemingsupported"></a><a name="iswindowsthemingsupported"></a>CMFCVisualManagerWindows::IsWindowsThemingSupported  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsWindowsThemingSupported() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameiswinxpthemeavailablea--cmfcvisualmanagerwindowsiswinxpthemeavailable"></a><a name="iswinxpthemeavailable"></a>CMFCVisualManagerWindows::IsWinXPThemeAvailable  
 Windows XP かどうかを決定または[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]テーマとは、使用できます。  
  
```  
static BOOL IsWinXPThemeAvailible();
```  
  
### <a name="return-value"></a>戻り値  
 テーマがある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは両方の Windows XP と[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]テーマです。  
  
 `IsWinXPThemeAvailable`同じ`CMFCVisualManagerWindows::IsWindowsThemingAvailable`する点を除いて`IsWinXPThemeAvailable`の静的メソッドです。 そのため、いずれかが存在しない場合の一時的なビジュアル マネージャーが作成されます。  
  
 `IsWinXPThemeAvailable`常に Windows XP より前のバージョンの Windows で 0 を返します。  
  
##  <a name="a-namemb3dtabsxpthemea--cmfcvisualmanagerwindowsmb3dtabsxptheme"></a><a name="m_b3dtabsxptheme"></a>CMFCVisualManagerWindows::m_b3DTabsXPTheme  
 ビジュアル マネージャーが 3D のタブを表示するかどうかを決定するブール値パラメーター。  
  
```  
AFX_IMPORT_DATA static BOOL m_b3DTabsXPTheme;  
```  
  
##  <a name="a-nameondrawbargrippera--cmfcvisualmanagerwindowsondrawbargripper"></a><a name="ondrawbargripper"></a>CMFCVisualManagerWindows::OnDrawBarGripper  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBarGripper(
    CDC* pDC,  
    CRect rectGripper,  
    BOOL bHorz,  
    CBasePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rectGripper`  
 [入力] `bHorz`  
 [入力] `pBar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawbrowsebuttona--cmfcvisualmanagerwindowsondrawbrowsebutton"></a><a name="ondrawbrowsebutton"></a>CMFCVisualManagerWindows::OnDrawBrowseButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnDrawBrowseButton(
    CDC* pDC,  
    CRect rect,  
    CMFCEditBrowseCtrl* pEdit,  
    CMFCVisualManager::AFX_BUTTON_STATE state,  
    COLORREF& clrText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `pEdit`  
 [入力] `state`  
 [入力] `clrText`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawbuttonbordera--cmfcvisualmanagerwindowsondrawbuttonborder"></a><a name="ondrawbuttonborder"></a>CMFCVisualManagerWindows::OnDrawButtonBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawButtonBorder(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pButton`  
 [入力] `rect`  
 [入力] `state`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawbuttonseparatora--cmfcvisualmanagerwindowsondrawbuttonseparator"></a><a name="ondrawbuttonseparator"></a>CMFCVisualManagerWindows::OnDrawButtonSeparator  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawButtonSeparator(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pButton`  
 [入力] `rect`  
 [入力] `state`  
 [入力] `bHorz`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawcaptionbuttona--cmfcvisualmanagerwindowsondrawcaptionbutton"></a><a name="ondrawcaptionbutton"></a>CMFCVisualManagerWindows::OnDrawCaptionButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawCaptionButton(
    CDC* pDC,  
    CMFCCaptionButton* pButton,  
    BOOL bActive,  
    BOOL bHorz,  
    BOOL bMaximized,  
    BOOL bDisabled,  
    int nImageID = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pButton`  
 [入力] `bActive`  
 [入力] `bHorz`  
 [入力] `bMaximized`  
 [入力] `bDisabled`  
 [入力] `nImageID`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawcaptionbuttonicona--cmfcvisualmanagerwindowsondrawcaptionbuttonicon"></a><a name="ondrawcaptionbuttonicon"></a>CMFCVisualManagerWindows::OnDrawCaptionButtonIcon  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawCaptionButtonIcon(
    CDC* pDC,  
    CMFCCaptionButton* pButton,  
    CMenuImages::IMAGES_IDS id,  
    BOOL bActive,  
    BOOL bDisabled,  
    CPoint ptImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pButton`  
 [入力] `id`  
 [入力] `bActive`  
 [入力] `bDisabled`  
 [入力] `ptImage`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawcheckboxexa--cmfcvisualmanagerwindowsondrawcheckboxex"></a><a name="ondrawcheckboxex"></a>CMFCVisualManagerWindows::OnDrawCheckBoxEx  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawCheckBoxEx(
    CDC* pDC,  
    CRect rect,  
    int nState,  
    BOOL bHighlighted,  
    BOOL bPressed,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `nState`  
 [入力] `bHighlighted`  
 [入力] `bPressed`  
 [入力] `bEnabled`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawcombobordera--cmfcvisualmanagerwindowsondrawcomboborder"></a><a name="ondrawcomboborder"></a>CMFCVisualManagerWindows::OnDrawComboBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawComboBorder(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsDropped,  
    BOOL bIsHighlighted,  
    CMFCToolBarComboBoxButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bDisabled`  
 [入力] `bIsDropped`  
 [入力] `bIsHighlighted`  
 [入力] `pButton`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawcombodropbuttona--cmfcvisualmanagerwindowsondrawcombodropbutton"></a><a name="ondrawcombodropbutton"></a>CMFCVisualManagerWindows::OnDrawComboDropButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawComboDropButton(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsDropped,  
    BOOL bIsHighlighted,  
    CMFCToolBarComboBoxButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bDisabled`  
 [入力] `bIsDropped`  
 [入力] `bIsHighlighted`  
 [入力] `pButton`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawcontrolbordera--cmfcvisualmanagerwindowsondrawcontrolborder"></a><a name="ondrawcontrolborder"></a>CMFCVisualManagerWindows::OnDrawControlBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawControlBorder(CWnd* pWndCtrl);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndCtrl`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondraweditbordera--cmfcvisualmanagerwindowsondraweditborder"></a><a name="ondraweditborder"></a>CMFCVisualManagerWindows::OnDrawEditBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawEditBorder(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsHighlighted,  
    CMFCToolBarEditBoxButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bDisabled`  
 [入力] `bIsHighlighted`  
 [入力] `pButton`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawexpandingboxa--cmfcvisualmanagerwindowsondrawexpandingbox"></a><a name="ondrawexpandingbox"></a>CMFCVisualManagerWindows::OnDrawExpandingBox  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawExpandingBox(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsOpened,  
    COLORREF colorBox);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bIsOpened`  
 [入力] `colorBox`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawfloatingtoolbarbordera--cmfcvisualmanagerwindowsondrawfloatingtoolbarborder"></a><a name="ondrawfloatingtoolbarborder"></a>CMFCVisualManagerWindows::OnDrawFloatingToolbarBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawFloatingToolbarBorder(
    CDC* pDC,  
    CMFCBaseToolBar* pToolBar,  
    CRect rectBorder,  
    CRect rectBorderSize);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pToolBar`  
 [入力] `rectBorder`  
 [入力] `rectBorderSize`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawheaderctrlbordera--cmfcvisualmanagerwindowsondrawheaderctrlborder"></a><a name="ondrawheaderctrlborder"></a>CMFCVisualManagerWindows::OnDrawHeaderCtrlBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawHeaderCtrlBorder(
    CMFCHeaderCtrl* pCtrl,  
    CDC* pDC,  
    CRect& rect,  
    BOOL bIsPressed,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pCtrl`  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bIsPressed`  
 [入力] `bIsHighlighted`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawheaderctrlsortarrowa--cmfcvisualmanagerwindowsondrawheaderctrlsortarrow"></a><a name="ondrawheaderctrlsortarrow"></a>CMFCVisualManagerWindows::OnDrawHeaderCtrlSortArrow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawHeaderCtrlSortArrow(
    CMFCHeaderCtrl* pCtrl,  
    CDC* pDC,  
    CRect& rect,  
    BOOL bIsUp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pCtrl`  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bIsUp`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawmenubordera--cmfcvisualmanagerwindowsondrawmenuborder"></a><a name="ondrawmenuborder"></a>CMFCVisualManagerWindows::OnDrawMenuBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawMenuBorder(
    CDC* pDC,  
    CMFCPopu* pMenu,  
    CRect rect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pMenu`  
 [入力] `rect`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawmenusystembuttona--cmfcvisualmanagerwindowsondrawmenusystembutton"></a><a name="ondrawmenusystembutton"></a>CMFCVisualManagerWindows::OnDrawMenuSystemButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawMenuSystemButton(
    CDC* pDC,  
    CRect rect,  
    UINT uiSystemCommand,  
    UINT nStyle,  
    BOOL bHighlight);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `uiSystemCommand`  
 [入力] `nStyle`  
 [入力] `bHighlight`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawminiframebordera--cmfcvisualmanagerwindowsondrawminiframeborder"></a><a name="ondrawminiframeborder"></a>CMFCVisualManagerWindows::OnDrawMiniFrameBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawMiniFrameBorder(
    CDC* pDC,  
    CPaneFrameWnd* pFrameWnd,  
    CRect rectBorder,  
    CRect rectBorderSize);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pFrameWnd`  
 [入力] `rectBorder`  
 [入力] `rectBorderSize`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawoutlookpagebuttonbordera--cmfcvisualmanagerwindowsondrawoutlookpagebuttonborder"></a><a name="ondrawoutlookpagebuttonborder"></a>CMFCVisualManagerWindows::OnDrawOutlookPageButtonBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawOutlookPageButtonBorder(
    CDC* pDC,  
    CRect& rectBtn,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rectBtn`  
 [入力] `bIsHighlighted`  
 [入力] `bIsPressed`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawpanebordera--cmfcvisualmanagerwindowsondrawpaneborder"></a><a name="ondrawpaneborder"></a>CMFCVisualManagerWindows::OnDrawPaneBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawPaneBorder(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pBar`  
 [入力] `rect`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawpanecaptiona--cmfcvisualmanagerwindowsondrawpanecaption"></a><a name="ondrawpanecaption"></a>CMFCVisualManagerWindows::OnDrawPaneCaption  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnDrawPaneCaption(
    CDC* pDC,  
    CDockablePane* pBar,  
    BOOL bActive,  
    CRect rectCaption,  
    CRect rectButtons);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pBar`  
 [入力] `bActive`  
 [入力] `rectCaption`  
 [入力] `rectButtons`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawpopupwindowbuttonbordera--cmfcvisualmanagerwindowsondrawpopupwindowbuttonborder"></a><a name="ondrawpopupwindowbuttonborder"></a>CMFCVisualManagerWindows::OnDrawPopupWindowButtonBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawPopupWindowButtonBorder(
    CDC* pDC,  
    CRect rectClient,  
    CMFCDesktopAlertWndButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rectClient`  
 [入力] `pButton`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawscrollbuttonsa--cmfcvisualmanagerwindowsondrawscrollbuttons"></a><a name="ondrawscrollbuttons"></a>CMFCVisualManagerWindows::OnDrawScrollButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawScrollButtons(
    CDC* pDC,  
    const CRect& rect,  
    const int nBorderSize,  
    int iImage,  
    BOOL bHilited);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `nBorderSize`  
 [入力] `iImage`  
 [入力] `bHilited`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawseparatora--cmfcvisualmanagerwindowsondrawseparator"></a><a name="ondrawseparator"></a>CMFCVisualManagerWindows::OnDrawSeparator  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawSeparator(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect rect,  
    BOOL bIsHoriz);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pBar`  
 [入力] `rect`  
 [入力] `bIsHoriz`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawspinbuttonsa--cmfcvisualmanagerwindowsondrawspinbuttons"></a><a name="ondrawspinbuttons"></a>CMFCVisualManagerWindows::OnDrawSpinButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawSpinButtons(
    CDC* pDC,  
    CRect rectSpin,  
    int nState,  
    BOOL bOrientation,  
    CMFCSpinButtonCtrl* pSpinCtrl);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rectSpin`  
 [入力] `nState`  
 [入力] `bOrientation`  
 [入力] `pSpinCtrl`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawstatusbarpanebordera--cmfcvisualmanagerwindowsondrawstatusbarpaneborder"></a><a name="ondrawstatusbarpaneborder"></a>CMFCVisualManagerWindows::OnDrawStatusBarPaneBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawStatusBarPaneBorder(
    CDC* pDC,  
    CMFCStatusBar* pBar,  
    CRect rectPane,  
    UINT uiID,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pBar`  
 [入力] `rectPane`  
 [入力] `uiID`  
 [入力] `nStyle`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawstatusbarprogressa--cmfcvisualmanagerwindowsondrawstatusbarprogress"></a><a name="ondrawstatusbarprogress"></a>CMFCVisualManagerWindows::OnDrawStatusBarProgress  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawStatusBarProgress(
    CDC* pDC,  
    CMFCStatusBar* pStatusBar,  
    CRect rectProgress,  
    int nProgressTotal,  
    int nProgressCurr,  
    COLORREF clrBar,  
    COLORREF clrProgressBarDest,  
    COLORREF clrProgressText,  
    BOOL bProgressText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pStatusBar`  
 [入力] `rectProgress`  
 [入力] `nProgressTotal`  
 [入力] `nProgressCurr`  
 [入力] `clrBar`  
 [入力] `clrProgressBarDest`  
 [入力] `clrProgressText`  
 [入力] `bProgressText`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawstatusbarsizeboxa--cmfcvisualmanagerwindowsondrawstatusbarsizebox"></a><a name="ondrawstatusbarsizebox"></a>CMFCVisualManagerWindows::OnDrawStatusBarSizeBox  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawStatusBarSizeBox(
    CDC* pDC,  
    CMFCStatusBar* pStatBar,  
    CRect rectSizeBox);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pStatBar`  
 [入力] `rectSizeBox`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawtaba--cmfcvisualmanagerwindowsondrawtab"></a><a name="ondrawtab"></a>CMFCVisualManagerWindows::OnDrawTab  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTab(
    CDC* pDC,  
    CRect rectTab,  
    int iTab,  
    BOOL bIsActive,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rectTab`  
 [入力] `iTab`  
 [入力] `bIsActive`  
 [入力] `pTabWnd`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawtabclosebuttona--cmfcvisualmanagerwindowsondrawtabclosebutton"></a><a name="ondrawtabclosebutton"></a>CMFCVisualManagerWindows::OnDrawTabCloseButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTabCloseButton(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed,  
    BOOL bIsDisabled);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `pTabWnd`  
 [入力] `bIsHighlighted`  
 [入力] `bIsPressed`  
 [入力] `bIsDisabled`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawtabsbuttonbordera--cmfcvisualmanagerwindowsondrawtabsbuttonborder"></a><a name="ondrawtabsbuttonborder"></a>CMFCVisualManagerWindows::OnDrawTabsButtonBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTabsButtonBorder(
    CDC* pDC,  
    CRect& rect,  
    CMFCButton* pButton,  
    UINT uiState,  
    CMFCBaseTabCtrl* pWndTab);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `pButton`  
 [入力] `uiState`  
 [入力] `pWndTab`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawtaska--cmfcvisualmanagerwindowsondrawtask"></a><a name="ondrawtask"></a>CMFCVisualManagerWindows::OnDrawTask  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTask(
    CDC* pDC,  
    CMFCTasksPaneTask* pTask,  
    CImageList* pIcons,  
    BOOL bIsHighlighted = FALSE,  
    BOOL bIsSelected = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pTask`  
 [入力] `pIcons`  
 [入力] `bIsHighlighted`  
 [入力] `bIsSelected`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawtasksgroupareabordera--cmfcvisualmanagerwindowsondrawtasksgroupareaborder"></a><a name="ondrawtasksgroupareaborder"></a>CMFCVisualManagerWindows::OnDrawTasksGroupAreaBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTasksGroupAreaBorder(
    CDC* pDC,  
    CRect rect,  
    BOOL bSpecial = FALSE,  
    BOOL bNoTitle = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bSpecial`  
 [入力] `bNoTitle`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawtasksgroupcaptiona--cmfcvisualmanagerwindowsondrawtasksgroupcaption"></a><a name="ondrawtasksgroupcaption"></a>CMFCVisualManagerWindows::OnDrawTasksGroupCaption  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTasksGroupCaption(
    CDC* pDC,  
    CMFCTasksPaneTaskGroup* pGroup,  
    BOOL bIsHighlighted = FALSE,  
    BOOL bIsSelected = FALSE,  
    BOOL bCanCollapse = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pGroup`  
 [入力] `bIsHighlighted`  
 [入力] `bIsSelected`  
 [入力] `bCanCollapse`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawtearoffcaptiona--cmfcvisualmanagerwindowsondrawtearoffcaption"></a><a name="ondrawtearoffcaption"></a>CMFCVisualManagerWindows::OnDrawTearOffCaption  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTearOffCaption(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsActive);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bIsActive`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonerasepopupwindowbuttona--cmfcvisualmanagerwindowsonerasepopupwindowbutton"></a><a name="onerasepopupwindowbutton"></a>CMFCVisualManagerWindows::OnErasePopupWindowButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnErasePopupWindowButton(
    CDC* pDC,  
    CRect rectClient,  
    CMFCDesktopAlertWndButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rectClient`  
 [入力] `pButton`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonerasetabsareaa--cmfcvisualmanagerwindowsonerasetabsarea"></a><a name="onerasetabsarea"></a>CMFCVisualManagerWindows::OnEraseTabsArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnEraseTabsArea(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `pTabWnd`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonerasetabsbuttona--cmfcvisualmanagerwindowsonerasetabsbutton"></a><a name="onerasetabsbutton"></a>CMFCVisualManagerWindows::OnEraseTabsButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnEraseTabsButton(
    CDC* pDC,  
    CRect rect,  
    CMFCButton* pButton,  
    CMFCBaseTabCtrl* pWndTab);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `pButton`  
 [入力] `pWndTab`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonerasetabsframea--cmfcvisualmanagerwindowsonerasetabsframe"></a><a name="onerasetabsframe"></a>CMFCVisualManagerWindows::OnEraseTabsFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnEraseTabsFrame(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `pTabWnd`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonfillbarbackgrounda--cmfcvisualmanagerwindowsonfillbarbackground"></a><a name="onfillbarbackground"></a>CMFCVisualManagerWindows::OnFillBarBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnFillBarBackground(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect rectClient,  
    CRect rectClip,  
    BOOL bNCArea = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pBar`  
 [入力] `rectClient`  
 [入力] `rectClip`  
 [入力] `bNCArea`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonfillbuttoninteriora--cmfcvisualmanagerwindowsonfillbuttoninterior"></a><a name="onfillbuttoninterior"></a>CMFCVisualManagerWindows::OnFillButtonInterior  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnFillButtonInterior(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pButton`  
 [入力] `rect`  
 [入力] `state`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonfillcommandslistbackgrounda--cmfcvisualmanagerwindowsonfillcommandslistbackground"></a><a name="onfillcommandslistbackground"></a>CMFCVisualManagerWindows::OnFillCommandsListBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillCommandsListBackground(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsSelected = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bIsSelected`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonfillminiframecaptiona--cmfcvisualmanagerwindowsonfillminiframecaption"></a><a name="onfillminiframecaption"></a>CMFCVisualManagerWindows::OnFillMiniFrameCaption  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillMiniFrameCaption(
    CDC* pDC,  
    CRect rectCaption,  
    CPaneFrameWnd* pFrameWnd,  
    BOOL bActive);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rectCaption`  
 [入力] `pFrameWnd`  
 [入力] `bActive`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonfilloutlookpagebuttona--cmfcvisualmanagerwindowsonfilloutlookpagebutton"></a><a name="onfilloutlookpagebutton"></a>CMFCVisualManagerWindows::OnFillOutlookPageButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnFillOutlookPageButton(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed,  
    COLORREF& clrText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bIsHighlighted`  
 [入力] `bIsPressed`  
 [入力] `clrText`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonfilltasksgroupinteriora--cmfcvisualmanagerwindowsonfilltasksgroupinterior"></a><a name="onfilltasksgroupinterior"></a>CMFCVisualManagerWindows::OnFillTasksGroupInterior  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnFillTasksGroupInterior(
    CDC* pDC,  
    CRect rect,  
    BOOL bSpecial = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bSpecial`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonfilltaskspanebackgrounda--cmfcvisualmanagerwindowsonfilltaskspanebackground"></a><a name="onfilltaskspanebackground"></a>CMFCVisualManagerWindows::OnFillTasksPaneBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnFillTasksPaneBackground(
    CDC* pDC,  
    CRect rectWorkArea);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rectWorkArea`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonhighlightmenuitema--cmfcvisualmanagerwindowsonhighlightmenuitem"></a><a name="onhighlightmenuitem"></a>CMFCVisualManagerWindows::OnHighlightMenuItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnHighlightMenuItem(
    CDC* pDC,  
    CMFCToolBarMenuButton* pButton,  
    CRect rect,  
    COLORREF& clrText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `pButton`  
 [入力] `rect`  
 [入力] `clrText`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonhighlightrarelyusedmenuitemsa--cmfcvisualmanagerwindowsonhighlightrarelyusedmenuitems"></a><a name="onhighlightrarelyusedmenuitems"></a>CMFCVisualManagerWindows::OnHighlightRarelyUsedMenuItems  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnHighlightRarelyUsedMenuItems(
    CDC* pDC,  
    CRect rectRarelyUsed);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rectRarelyUsed`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonupdatesystemcolorsa--cmfcvisualmanagerwindowsonupdatesystemcolors"></a><a name="onupdatesystemcolors"></a>CMFCVisualManagerWindows::OnUpdateSystemColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnUpdateSystemColors();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetofficestylemenusa--cmfcvisualmanagerwindowssetofficestylemenus"></a><a name="setofficestylemenus"></a>CMFCVisualManagerWindows::SetOfficeStyleMenus  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetOfficeStyleMenus(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bOn`  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager クラス](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP クラス](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

