---
title: "CMFCVisualManagerWindows クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCVisualManagerWindows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerWindows クラス"
ms.assetid: 568b6e9e-8e67-4477-9a3d-2981cbd09861
caps.latest.revision: 46
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 48
---
# CMFCVisualManagerWindows クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerWindows` は、ユーザーが Microsoft Windows XP または Microsoft Vista のテーマを選択したときに、Windows XP または Vista と同様の外観を表示します。  
  
## 構文  
  
```  
class CMFCVisualManagerWindows : public CMFCVisualManagerOfficeXP  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCVisualManagerWindows::CMFCVisualManagerWindows`|既定のコンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCVisualManagerWindows::AlwaysHighlight3DTabs](../Topic/CMFCVisualManagerWindows::AlwaysHighlight3DTabs.md)|フレームワークは、アプリケーションの 3D タブが常に強調表示されるかどうかを判断する場合に、このメソッドを呼び出します   \([CMFCVisualManager::AlwaysHighlight3DTabs](../Topic/CMFCVisualManager::AlwaysHighlight3DTabs.md) をオーバーライドします\)。|  
|[CMFCVisualManagerWindows::DrawComboBorderWinXP](../Topic/CMFCVisualManagerWindows::DrawComboBorderWinXP.md)|\(`CMFCVisualManager::DrawComboBorderWinXP` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::DrawComboDropButtonWinXP](../Topic/CMFCVisualManagerWindows::DrawComboDropButtonWinXP.md)|\([CMFCVisualManager::DrawComboDropButtonWinXP](../Topic/CMFCVisualManager::DrawComboDropButtonWinXP.md) をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::DrawPushButtonWinXP](../Topic/CMFCVisualManagerWindows::DrawPushButtonWinXP.md)|\([CMFCVisualManager::DrawPushButtonWinXP](../Topic/CMFCVisualManager::DrawPushButtonWinXP.md) をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::GetButtonExtraBorder](../Topic/CMFCVisualManagerWindows::GetButtonExtraBorder.md)|フレームワークは、ツール バーのボタンを描画するときにこのメソッドを呼び出します   \([CMFCVisualManager::GetButtonExtraBorder](../Topic/CMFCVisualManager::GetButtonExtraBorder.md) をオーバーライドします\)。|  
|[CMFCVisualManagerWindows::GetCaptionButtonExtraBorder](../Topic/CMFCVisualManagerWindows::GetCaptionButtonExtraBorder.md)|\([CMFCVisualManager::GetCaptionButtonExtraBorder](../Topic/CMFCVisualManager::GetCaptionButtonExtraBorder.md) をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::GetDockingPaneCaptionExtraHeight](../Topic/CMFCVisualManagerWindows::GetDockingPaneCaptionExtraHeight.md)|\(`CMFCVisualManager::GetDockingPaneCaptionExtraHeight` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::GetHighlightedMenuItemTextColor](../Topic/CMFCVisualManagerWindows::GetHighlightedMenuItemTextColor.md)|\(`CMFCVisualManagerOfficeXP::GetHighlightedMenuItemTextColor` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::GetPopupMenuGap](../Topic/CMFCVisualManagerWindows::GetPopupMenuGap.md)|\(`CMFCVisualManagerOfficeXP::GetPopupMenuGap` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::GetToolbarButtonTextColor](../Topic/CMFCVisualManagerWindows::GetToolbarButtonTextColor.md)|\(`CMFCVisualManagerOfficeXP::GetToolbarButtonTextColor` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::IsDefaultWinXPPopupButton](../Topic/CMFCVisualManagerWindows::IsDefaultWinXPPopupButton.md)|\([CMFCVisualManager::IsDefaultWinXPPopupButton](../Topic/CMFCVisualManager::IsDefaultWinXPPopupButton.md) をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::IsHighlightWholeMenuItem](../Topic/CMFCVisualManagerWindows::IsHighlightWholeMenuItem.md)|\(`CMFCVisualManagerOfficeXP::IsHighlightWholeMenuItem` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::IsOfficeStyleMenus](../Topic/CMFCVisualManagerWindows::IsOfficeStyleMenus.md)||  
|[CMFCVisualManagerWindows::IsOfficeXPStyleMenus](../Topic/CMFCVisualManagerWindows::IsOfficeXPStyleMenus.md)|ビジュアル マネージャーが Office XP スタイルのメニューを実装するかどうかを示します。  \([CMFCVisualManager::IsOfficeXPStyleMenus](../Topic/CMFCVisualManager::IsOfficeXPStyleMenus.md) をオーバーライドします\)。|  
|[CMFCVisualManagerWindows::IsWindowsThemingSupported](../Topic/CMFCVisualManagerWindows::IsWindowsThemingSupported.md)|\(`CMFCVisualManager::IsWindowsThemingSupported` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::IsWinXPThemeAvailable](../Topic/CMFCVisualManagerWindows::IsWinXPThemeAvailable.md)|Windows テーマを利用できるかどうかを示します。  テーマは、Windows XP テーマまたは [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] テーマです。|  
|[CMFCVisualManagerWindows::OnDrawBarGripper](../Topic/CMFCVisualManagerWindows::OnDrawBarGripper.md)|\(`CMFCVisualManagerOfficeXP::OnDrawBarGripper` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawBrowseButton](../Topic/CMFCVisualManagerWindows::OnDrawBrowseButton.md)|\(`CMFCVisualManagerOfficeXP::OnDrawBrowseButton` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawButtonBorder.md)|\(`CMFCVisualManagerOfficeXP::OnDrawButtonBorder` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawButtonSeparator](../Topic/CMFCVisualManagerWindows::OnDrawButtonSeparator.md)|\(`CMFCVisualManagerOfficeXP::OnDrawButtonSeparator` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawCaptionButton](../Topic/CMFCVisualManagerWindows::OnDrawCaptionButton.md)|\(`CMFCVisualManagerOfficeXP::OnDrawCaptionButton` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawCaptionButtonIcon](../Topic/CMFCVisualManagerWindows::OnDrawCaptionButtonIcon.md)|\(`CMFCVisualManagerOfficeXP::OnDrawCaptionButtonIcon` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawCheckBoxEx](../Topic/CMFCVisualManagerWindows::OnDrawCheckBoxEx.md)|\([CMFCVisualManager::OnDrawCheckBoxEx](../Topic/CMFCVisualManager::OnDrawCheckBoxEx.md) をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawComboBorder](../Topic/CMFCVisualManagerWindows::OnDrawComboBorder.md)|\(`CMFCVisualManagerOfficeXP::OnDrawComboBorder` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawComboDropButton](../Topic/CMFCVisualManagerWindows::OnDrawComboDropButton.md)|\(`CMFCVisualManagerOfficeXP::OnDrawComboDropButton` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawControlBorder](../Topic/CMFCVisualManagerWindows::OnDrawControlBorder.md)|\([CMFCVisualManager::OnDrawControlBorder](../Topic/CMFCVisualManager::OnDrawControlBorder.md) をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawEditBorder](../Topic/CMFCVisualManagerWindows::OnDrawEditBorder.md)|\(`CMFCVisualManagerOfficeXP::OnDrawEditBorder` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawExpandingBox](../Topic/CMFCVisualManagerWindows::OnDrawExpandingBox.md)|\([CMFCVisualManager::OnDrawExpandingBox](../Topic/CMFCVisualManager::OnDrawExpandingBox.md) をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawFloatingToolbarBorder](../Topic/CMFCVisualManagerWindows::OnDrawFloatingToolbarBorder.md)|\(`CMFCVisualManagerOfficeXP::OnDrawFloatingToolbarBorder` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManagerWindows::OnDrawHeaderCtrlBorder.md)|フレームワークは、[CMFCHeaderCtrl クラス](../Topic/CMFCHeaderCtrl%20Class.md)のインスタンスの周囲に境界線を描画するときにこのメソッドを呼び出します   \([CMFCVisualManager::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManager::OnDrawHeaderCtrlBorder.md) をオーバーライドします\)。|  
|[CMFCVisualManagerWindows::OnDrawHeaderCtrlSortArrow](../Topic/CMFCVisualManagerWindows::OnDrawHeaderCtrlSortArrow.md)|フレームワークは、ヘッダー コントロールの並べ替え矢印を描画するときにこの関数を呼び出します   \([CMFCVisualManager::OnDrawHeaderCtrlSortArrow](../Topic/CMFCVisualManager::OnDrawHeaderCtrlSortArrow.md) をオーバーライドします\)。|  
|[CMFCVisualManagerWindows::OnDrawMenuBorder](../Topic/CMFCVisualManagerWindows::OnDrawMenuBorder.md)|\(`CMFCVisualManagerOfficeXP::OnDrawMenuBorder` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawMenuSystemButton](../Topic/CMFCVisualManagerWindows::OnDrawMenuSystemButton.md)|\(`CMFCVisualManagerOfficeXP::OnDrawMenuSystemButton` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawMiniFrameBorder](../Topic/CMFCVisualManagerWindows::OnDrawMiniFrameBorder.md)|\(`CMFCVisualManagerOfficeXP::OnDrawMiniFrameBorder` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawOutlookPageButtonBorder.md)|Outlook のページ ボタンの境界線を描画するときに、フレームワークによって呼び出されます。  \([CMFCVisualManager::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManager::OnDrawOutlookPageButtonBorder.md) をオーバーライドします\)。|  
|[CMFCVisualManagerWindows::OnDrawPaneBorder](../Topic/CMFCVisualManagerWindows::OnDrawPaneBorder.md)|\(`CMFCVisualManagerOfficeXP::OnDrawPaneBorder` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawPaneCaption](../Topic/CMFCVisualManagerWindows::OnDrawPaneCaption.md)|\(`CMFCVisualManagerOfficeXP::OnDrawPaneCaption` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawPopupWindowButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawPopupWindowButtonBorder.md)|\(`CMFCVisualManagerOfficeXP::OnDrawPopupWindowButtonBorder` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawScrollButtons](../Topic/CMFCVisualManagerWindows::OnDrawScrollButtons.md)|\(`CMFCVisualManagerOfficeXP::OnDrawScrollButtons` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawSeparator](../Topic/CMFCVisualManagerWindows::OnDrawSeparator.md)|\(`CMFCVisualManagerOfficeXP::OnDrawSeparator` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawSpinButtons](../Topic/CMFCVisualManagerWindows::OnDrawSpinButtons.md)|\(`CMFCVisualManagerOfficeXP::OnDrawSpinButtons` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawStatusBarPaneBorder](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarPaneBorder.md)|\(`CMFCVisualManagerOfficeXP::OnDrawStatusBarPaneBorder` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawStatusBarProgress](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarProgress.md)|フレームワークは、[CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md) オブジェクトにプログレス インジケーターを描画するときにこのメソッドを呼び出します   \([CMFCVisualManager::OnDrawStatusBarProgress](../Topic/CMFCVisualManager::OnDrawStatusBarProgress.md) をオーバーライドします\)。|  
|[CMFCVisualManagerWindows::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarSizeBox.md)|フレームワークは、[CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md) のサイズ ボックスを描画するときにこのメソッドを呼び出します   \([CMFCVisualManager::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManager::OnDrawStatusBarSizeBox.md) をオーバーライドします\)。|  
|[CMFCVisualManagerWindows::OnDrawTab](../Topic/CMFCVisualManagerWindows::OnDrawTab.md)|\(`CMFCVisualManagerOfficeXP::OnDrawTab` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawTabCloseButton](../Topic/CMFCVisualManagerWindows::OnDrawTabCloseButton.md)|\(`CMFCVisualManagerOfficeXP::OnDrawTabCloseButton` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawTabsButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawTabsButtonBorder.md)|\(`CMFCVisualManagerOfficeXP::OnDrawTabsButtonBorder` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawTask](../Topic/CMFCVisualManagerWindows::OnDrawTask.md)|\(`CMFCVisualManagerOfficeXP::OnDrawTask` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawTasksGroupAreaBorder](../Topic/CMFCVisualManagerWindows::OnDrawTasksGroupAreaBorder.md)|\(`CMFCVisualManagerOfficeXP::OnDrawTasksGroupAreaBorder` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawTasksGroupCaption](../Topic/CMFCVisualManagerWindows::OnDrawTasksGroupCaption.md)|\(`CMFCVisualManagerOfficeXP::OnDrawTasksGroupCaption` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnDrawTearOffCaption](../Topic/CMFCVisualManagerWindows::OnDrawTearOffCaption.md)|\(`CMFCVisualManagerOfficeXP::OnDrawTearOffCaption` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnErasePopupWindowButton](../Topic/CMFCVisualManagerWindows::OnErasePopupWindowButton.md)|\(`CMFCVisualManagerOfficeXP::OnErasePopupWindowButton` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnEraseTabsArea](../Topic/CMFCVisualManagerWindows::OnEraseTabsArea.md)|\(`CMFCVisualManagerOfficeXP::OnEraseTabsArea` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnEraseTabsButton](../Topic/CMFCVisualManagerWindows::OnEraseTabsButton.md)|\(`CMFCVisualManagerOfficeXP::OnEraseTabsButton` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnEraseTabsFrame](../Topic/CMFCVisualManagerWindows::OnEraseTabsFrame.md)|フレームワークは、[CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md) のフレームを消去するときにこのメソッドを呼び出します   \([CMFCVisualManager::OnEraseTabsFrame](../Topic/CMFCVisualManager::OnEraseTabsFrame.md) をオーバーライドします\)。|  
|[CMFCVisualManagerWindows::OnFillBarBackground](../Topic/CMFCVisualManagerWindows::OnFillBarBackground.md)|\(`CMFCVisualManagerOfficeXP::OnFillBarBackground` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnFillButtonInterior](../Topic/CMFCVisualManagerWindows::OnFillButtonInterior.md)|\(`CMFCVisualManagerOfficeXP::OnFillButtonInterior` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnFillCommandsListBackground](../Topic/CMFCVisualManagerWindows::OnFillCommandsListBackground.md)|\(`CMFCVisualManagerOfficeXP::OnFillCommandsListBackground` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnFillMiniFrameCaption](../Topic/CMFCVisualManagerWindows::OnFillMiniFrameCaption.md)|\(`CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnFillOutlookPageButton](../Topic/CMFCVisualManagerWindows::OnFillOutlookPageButton.md)|フレームワークは、Outlook のページ ボタンの内部を塗りつぶすときにこのメソッドを呼び出します   \([CMFCVisualManager::OnFillOutlookPageButton](../Topic/CMFCVisualManager::OnFillOutlookPageButton.md) をオーバーライドします\)。|  
|[CMFCVisualManagerWindows::OnFillTasksGroupInterior](../Topic/CMFCVisualManagerWindows::OnFillTasksGroupInterior.md)|\(`CMFCVisualManagerOfficeXP::OnFillTasksGroupInterior` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnFillTasksPaneBackground](../Topic/CMFCVisualManagerWindows::OnFillTasksPaneBackground.md)|フレームワークは、[CMFCTasksPane](../Topic/CMFCTasksPane%20Class.md) コントロールの背景を塗りつぶすときにこのメソッドを呼び出します   \([CMFCVisualManager::OnFillTasksPaneBackground](../Topic/CMFCVisualManager::OnFillTasksPaneBackground.md) をオーバーライドします\)。|  
|[CMFCVisualManagerWindows::OnHighlightMenuItem](../Topic/CMFCVisualManagerWindows::OnHighlightMenuItem.md)|\(`CMFCVisualManagerOfficeXP::OnHighlightMenuItem` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnHighlightRarelyUsedMenuItems](../Topic/CMFCVisualManagerWindows::OnHighlightRarelyUsedMenuItems.md)|\(`CMFCVisualManagerOfficeXP::OnHighlightRarelyUsedMenuItems` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::OnUpdateSystemColors](../Topic/CMFCVisualManagerWindows::OnUpdateSystemColors.md)|\(`CMFCVisualManagerOfficeXP::OnUpdateSystemColors` をオーバーライドします。\)|  
|[CMFCVisualManagerWindows::SetOfficeStyleMenus](../Topic/CMFCVisualManagerWindows::SetOfficeStyleMenus.md)||  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCVisualManagerWindows::m\_b3DTabsXPTheme](../Topic/CMFCVisualManagerWindows::m_b3DTabsXPTheme.md)|Windows XP テーマに 3D タブを表示するかどうかを指定します。|  
  
## 解説  
 `CMFCVisualManagerWindows` クラスを使用してアプリケーションの外観を変更し、アプリケーションが実行されているコンピューターで現在の Windows XP テーマまたは [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] テーマを表示します。  
  
 ただし、アプリケーションが Windows XP より前のバージョンの Windows で実行されている場合、またはユーザーが "クラシック" 表示を使用しているためにテーマが無効になっている場合、Windows テーマを使用できないことがあります。  テーマを使用できない場合、アプリケーションは [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md) で定義された既定のビジュアル マネージャーを使用します。  
  
## 使用例  
 `CMFCVisualManagerWindows` を使用する方法を次の例に示します。  このコード スニペットは [デスクトップ通知デモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#10](../../mfc/reference/codesnippet/CPP/cmfcvisualmanagerwindows-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
## 必要条件  
 **ヘッダー :** afxvisualmanagerwindows.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCVisualManager クラス](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP クラス](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)