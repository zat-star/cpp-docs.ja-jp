---
title: "CMFCVisualManager クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCVisualManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManager クラス"
ms.assetid: beed80f7-36a2-4d64-9f09-e807cfefc3fe
caps.latest.revision: 58
caps.handback.revision: 46
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCVisualManager クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アプリケーションの外観変更のサポートをグローバル レベルで提供します。  `CMFCVisualManager` クラスは、一貫したスタイルを使用してアプリケーションの GUI コントロールを描画する機能を提供するクラスと連携します。  これらの連携するクラスはビジュアル マネージャーと呼ばれ、`CMFCBaseVisualManager` から継承されます。  
  
## 構文  
  
```  
class CMFCVisualManager : public CMFCBaseVisualManager  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCVisualManager::CMFCVisualManager`|既定のコンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCVisualManager::AdjustFrames](../Topic/CMFCVisualManager::AdjustFrames.md)||  
|[CMFCVisualManager::AdjustToolbars](../Topic/CMFCVisualManager::AdjustToolbars.md)||  
|[CMFCVisualManager::AlwaysHighlight3DTabs](../Topic/CMFCVisualManager::AlwaysHighlight3DTabs.md)|3D タブを常に強調表示色で描画する必要があるかどうかを判断するために、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::DestroyInstance](../Topic/CMFCVisualManager::DestroyInstance.md)||  
|[CMFCVisualManager::DoDrawHeaderSortArrow](../Topic/CMFCVisualManager::DoDrawHeaderSortArrow.md)||  
|[CMFCVisualManager::DrawComboDropButtonWinXP](../Topic/CMFCVisualManager::DrawComboDropButtonWinXP.md)||  
|[CMFCVisualManager::DrawPushButtonWinXP](../Topic/CMFCVisualManager::DrawPushButtonWinXP.md)||  
|[CMFCVisualManager::DrawTextOnGlass](../Topic/CMFCVisualManager::DrawTextOnGlass.md)||  
|[CMFCVisualManager::GetAutoHideButtonTextColor](../Topic/CMFCVisualManager::GetAutoHideButtonTextColor.md)|自動的に隠すボタンのテキストの色を取得するために、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::GetButtonExtraBorder](../Topic/CMFCVisualManager::GetButtonExtraBorder.md)|現在のビジュアル マネージャーがボタンを描画するために必要な、拡大されたボタン サイズを取得するために、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::GetCaptionBarTextColor](../Topic/CMFCVisualManager::GetCaptionBarTextColor.md)|キャプション バーのテキストの色を取得するために、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::GetDockingTabsBordersSize](../Topic/CMFCVisualManager::GetDockingTabsBordersSize.md)|ドッキングされたツール バーの境界線のサイズを取得するために、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::GetHighlightedMenuItemTextColor](../Topic/CMFCVisualManager::GetHighlightedMenuItemTextColor.md)||  
|[CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md)|`CMFCVisualManager` オブジェクトへのポインターを返します。|  
|[CMFCVisualManager::GetMDITabsBordersSize](../Topic/CMFCVisualManager::GetMDITabsBordersSize.md)|MDITabs ウィンドウの境界線のサイズを取得するために、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::GetMenuItemTextColor](../Topic/CMFCVisualManager::GetMenuItemTextColor.md)||  
|[CMFCVisualManager::GetMenuShadowDepth](../Topic/CMFCVisualManager::GetMenuShadowDepth.md)|メニュー シャドウの幅と高さを示す値を返します。|  
|[CMFCVisualManager::GetNcBtnSize](../Topic/CMFCVisualManager::GetNcBtnSize.md)|システム ボタンのサイズを現在のビジュアル マネージャーから取得するために、フレームワークによって呼び出されます。  システム ボタンとはメイン フレームのキャプションのボタンで、**\[閉じる\]**、**\[最小化\]**、**\[最大化\]**、および **\[元のサイズに戻す\]** の各コマンドにマップされています。|  
|[CMFCVisualManager::GetPopupMenuBorderSize](../Topic/CMFCVisualManager::GetPopupMenuBorderSize.md)|ポップアップ メニューの境界線のサイズを取得するために、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::GetPropertyGridGroupColor](../Topic/CMFCVisualManager::GetPropertyGridGroupColor.md)|プロパティ リストの背景色を取得するために、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::GetPropertyGridGroupTextColor](../Topic/CMFCVisualManager::GetPropertyGridGroupTextColor.md)|プロパティ リストのテキストの色を取得するために、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::GetRibbonHyperlinkTextColor](../Topic/CMFCVisualManager::GetRibbonHyperlinkTextColor.md)||  
|[CMFCVisualManager::GetRibbonPopupBorderSize](../Topic/CMFCVisualManager::GetRibbonPopupBorderSize.md)||  
|[CMFCVisualManager::GetRibbonQuickAccessToolBarTextColor](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarTextColor.md)||  
|[CMFCVisualManager::GetRibbonSliderColors](../Topic/CMFCVisualManager::GetRibbonSliderColors.md)||  
|[CMFCVisualManager::GetShowAllMenuItemsHeight](../Topic/CMFCVisualManager::GetShowAllMenuItemsHeight.md)||  
|[CMFCVisualManager::GetSmartDockingBaseGuideColors](../Topic/CMFCVisualManager::GetSmartDockingBaseGuideColors.md)||  
|[CMFCVisualManager::GetSmartDockingHighlightToneColor](../Topic/CMFCVisualManager::GetSmartDockingHighlightToneColor.md)||  
|[CMFCVisualManager::GetSmartDockingTheme](../Topic/CMFCVisualManager::GetSmartDockingTheme.md)|スマート ドッキング マーカーの表示に使用されるテーマを返します。|  
|[CMFCVisualManager::GetStatusBarPaneTextColor](../Topic/CMFCVisualManager::GetStatusBarPaneTextColor.md)||  
|[CMFCVisualManager::GetTabFrameColors](../Topic/CMFCVisualManager::GetTabFrameColors.md)|タブ フレームを描画するときに使用する色のセットを取得するために、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::GetTabTextColor](../Topic/CMFCVisualManager::GetTabTextColor.md)||  
|[CMFCVisualManager::GetToolbarButtonTextColor](../Topic/CMFCVisualManager::GetToolbarButtonTextColor.md)|ツール バー ボタンのテキストの現在の色を取得するために、フレームワークによって呼び出されます。  色は、現在のビジュアル マネージャーとボタンの状態と応じて異なります。|  
|[CMFCVisualManager::GetToolbarDisabledTextColor](../Topic/CMFCVisualManager::GetToolbarDisabledTextColor.md)|無効ツール バー要素に表示されるテキストの色を取得するために、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::GetToolbarHighlightColor](../Topic/CMFCVisualManager::GetToolbarHighlightColor.md)||  
|[CMFCVisualManager::GetToolTipInfo](../Topic/CMFCVisualManager::GetToolTipInfo.md)||  
|[CMFCVisualManager::HasOverlappedAutoHideButtons](../Topic/CMFCVisualManager::HasOverlappedAutoHideButtons.md)|自動非表示ボタンがオーバーラップしているかどうかを判定します。|  
|[CMFCVisualManager::IsDockingTabHasBorder](../Topic/CMFCVisualManager::IsDockingTabHasBorder.md)|現在のビジュアル マネージャーが、タブ付きのドッキング バーの周囲に境界線を描画するかどうかを指定します。|  
|[CMFCVisualManager::IsEmbossDisabledImage](../Topic/CMFCVisualManager::IsEmbossDisabledImage.md)|無効イメージをエンボスするかどうかを指定します。|  
|[CMFCVisualManager::IsFadeInactiveImage](../Topic/CMFCVisualManager::IsFadeInactiveImage.md)|ツール バーやメニュー上のアクティブではないイメージを淡色表示するかどうかを決定するために、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::IsMenuFlatLook](../Topic/CMFCVisualManager::IsMenuFlatLook.md)|メニュー ボタンの外観がフラットかどうかを示します。|  
|[CMFCVisualManager::IsOfficeXPStyleMenus](../Topic/CMFCVisualManager::IsOfficeXPStyleMenus.md)|ビジュアル マネージャーが Office XP スタイルのメニューを実装するかどうかを示します。|  
|[CMFCVisualManager::IsOwnerDrawCaption](../Topic/CMFCVisualManager::IsOwnerDrawCaption.md)|現在のビジュアル マネージャーがフレーム ウィンドウのオーナー描画キャプションを実装しているかどうかを示します。|  
|[CMFCVisualManager::IsShadowHighlightedImage](../Topic/CMFCVisualManager::IsShadowHighlightedImage.md)|強調表示されるイメージに影が表示されるかどうかを示します。|  
|[CMFCVisualManager::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManager::OnDrawAutoHideButtonBorder.md)|自動非表示ボタンの境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawBarGripper](../Topic/CMFCVisualManager::OnDrawBarGripper.md)|コントロール バーのグリップを描画するときに、フレームワークによって呼び出されます。  ユーザーがコントロール バーを動かすには、グリッパーをクリックする必要があります。|  
|[CMFCVisualManager::OnDrawBrowseButton](../Topic/CMFCVisualManager::OnDrawBrowseButton.md)|エディット コントロール \([CMFCEditBrowseCtrl クラス](../Topic/CMFCEditBrowseCtrl%20Class.md)\) に属する参照ボタンを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawButtonBorder](../Topic/CMFCVisualManager::OnDrawButtonBorder.md)|ツール バー ボタンの境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawButtonSeparator](../Topic/CMFCVisualManager::OnDrawButtonSeparator.md)||  
|[CMFCVisualManager::OnDrawCaptionBarBorder](../Topic/CMFCVisualManager::OnDrawCaptionBarBorder.md)|キャプション バーの境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawCaptionBarButtonBorder](../Topic/CMFCVisualManager::OnDrawCaptionBarButtonBorder.md)||  
|[CMFCVisualManager::OnDrawCaptionBarInfoArea](../Topic/CMFCVisualManager::OnDrawCaptionBarInfoArea.md)||  
|[CMFCVisualManager::OnDrawCaptionButton](../Topic/CMFCVisualManager::OnDrawCaptionButton.md)|キャプション ボタンを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawCheckBox](../Topic/CMFCVisualManager::OnDrawCheckBox.md)||  
|[CMFCVisualManager::OnDrawCheckBoxEx](../Topic/CMFCVisualManager::OnDrawCheckBoxEx.md)||  
|[CMFCVisualManager::OnDrawComboBorder](../Topic/CMFCVisualManager::OnDrawComboBorder.md)|コンボ ボックス ボタンの境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawComboDropButton](../Topic/CMFCVisualManager::OnDrawComboDropButton.md)|コンボ ボックス ドロップ ボタンを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawControlBorder](../Topic/CMFCVisualManager::OnDrawControlBorder.md)||  
|[CMFCVisualManager::OnDrawDefaultRibbonImage](../Topic/CMFCVisualManager::OnDrawDefaultRibbonImage.md)|既定のリボン イメージを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawEditBorder](../Topic/CMFCVisualManager::OnDrawEditBorder.md)|[CMFCToolBarEditBoxButton](../Topic/CMFCToolBarEditBoxButton%20Class.md) オブジェクトの周囲の境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawExpandingBox](../Topic/CMFCVisualManager::OnDrawExpandingBox.md)||  
|[CMFCVisualManager::OnDrawFloatingToolbarBorder](../Topic/CMFCVisualManager::OnDrawFloatingToolbarBorder.md)|フローティング ツール バーの境界線を描画するときに、フレームワークによって呼び出されます。  フローティング ツール バーは、ミニフレーム ウィンドウとして表示されるツール バーです。|  
|[CMFCVisualManager::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManager::OnDrawHeaderCtrlBorder.md)|ヘッダー コントロールを含む境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawHeaderCtrlSortArrow](../Topic/CMFCVisualManager::OnDrawHeaderCtrlSortArrow.md)|ヘッダー コントロールの並べ替え矢印を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawMenuArrowOnCustomizeList](../Topic/CMFCVisualManager::OnDrawMenuArrowOnCustomizeList.md)||  
|[CMFCVisualManager::OnDrawMenuBorder](../Topic/CMFCVisualManager::OnDrawMenuBorder.md)|メニューの境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawMenuCheck](../Topic/CMFCVisualManager::OnDrawMenuCheck.md)||  
|[CMFCVisualManager::OnDrawMenuItemButton](../Topic/CMFCVisualManager::OnDrawMenuItemButton.md)||  
|[CMFCVisualManager::OnDrawMenuLabel](../Topic/CMFCVisualManager::OnDrawMenuLabel.md)||  
|[CMFCVisualManager::OnDrawMenuResizeBar](../Topic/CMFCVisualManager::OnDrawMenuResizeBar.md)||  
|[CMFCVisualManager::OnDrawMenuScrollButton](../Topic/CMFCVisualManager::OnDrawMenuScrollButton.md)|メニュー スクロール ボタンを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawMenuShadow](../Topic/CMFCVisualManager::OnDrawMenuShadow.md)||  
|[CMFCVisualManager::OnDrawMenuSystemButton](../Topic/CMFCVisualManager::OnDrawMenuSystemButton.md)|**\[閉じる\]**、**\[最小化\]**、**\[最大化\]**、および **\[元のサイズに戻す\]** の各メニュー システム ボタンを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawMiniFrameBorder](../Topic/CMFCVisualManager::OnDrawMiniFrameBorder.md)||  
|[CMFCVisualManager::OnDrawOutlookBarSplitter](../Topic/CMFCVisualManager::OnDrawOutlookBarSplitter.md)|Outlook バーの分割線を描画するときに、フレームワークによって呼び出されます。  分割線は、コントロールをグループ化するために使用される水平のバーです。|  
|[CMFCVisualManager::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManager::OnDrawOutlookPageButtonBorder.md)|Outlook のページ ボタンの境界線を描画するときに、フレームワークによって呼び出されます。  Outlook のページ ボタンは、表示できる数より多いボタンが Outlook バー ペインに含まれている場合に表示されます。|  
|[CMFCVisualManager::OnDrawPaneBorder](../Topic/CMFCVisualManager::OnDrawPaneBorder.md)|[CPane クラス](../../mfc/reference/cpane-class.md)の境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawPaneCaption](../Topic/CMFCVisualManager::OnDrawPaneCaption.md)|`CPane` のキャプションを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawPaneDivider](../Topic/CMFCVisualManager::OnDrawPaneDivider.md)||  
|[CMFCVisualManager::OnDrawPopupWindowBorder](../Topic/CMFCVisualManager::OnDrawPopupWindowBorder.md)||  
|[CMFCVisualManager::OnDrawPopupWindowButtonBorder](../Topic/CMFCVisualManager::OnDrawPopupWindowButtonBorder.md)||  
|[CMFCVisualManager::OnDrawPopupWindowCaption](../Topic/CMFCVisualManager::OnDrawPopupWindowCaption.md)||  
|[CMFCVisualManager::OnDrawRibbonApplicationButton](../Topic/CMFCVisualManager::OnDrawRibbonApplicationButton.md)|リボンの**メイン ボタン**を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonButtonBorder.md)|リボン ボタンの境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonButtonsGroup](../Topic/CMFCVisualManager::OnDrawRibbonButtonsGroup.md)|リボン上のボタンのグループを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonCaption](../Topic/CMFCVisualManager::OnDrawRibbonCaption.md)|リボン バーがフレームに統合されている場合に限り、メイン フレームのキャプションを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonCaptionButton](../Topic/CMFCVisualManager::OnDrawRibbonCaptionButton.md)|リボン バーに配置されたキャプション ボタンを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonCategory](../Topic/CMFCVisualManager::OnDrawRibbonCategory.md)|リボン カテゴリを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonCategoryCaption](../Topic/CMFCVisualManager::OnDrawRibbonCategoryCaption.md)|リボン カテゴリのキャプションを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonCategoryScroll](../Topic/CMFCVisualManager::OnDrawRibbonCategoryScroll.md)||  
|[CMFCVisualManager::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManager::OnDrawRibbonCategoryTab.md)|リボン カテゴリのタブを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonCheckBoxOnList](../Topic/CMFCVisualManager::OnDrawRibbonCheckBoxOnList.md)||  
|[CMFCVisualManager::OnDrawRibbonColorPaletteBox](../Topic/CMFCVisualManager::OnDrawRibbonColorPaletteBox.md)||  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButtonContext](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButtonContext.md)||  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButton.md)|リボン ペインの既定のボタンを描画するときに、フレームワークによって呼び出されます。  既定のボタンは、ユーザーが縮小したリボン パネルが小さくなりすぎて、リボン要素を表示できなくなった場合に表示されます。  代わりに既定のボタンが表示されると、ドロップダウン メニューの項目としてリボン要素が追加されます。|  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButtonIndicator](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButtonIndicator.md)||  
|[CMFCVisualManager::OnDrawRibbonGalleryBorder](../Topic/CMFCVisualManager::OnDrawRibbonGalleryBorder.md)||  
|[CMFCVisualManager::OnDrawRibbonGalleryButton](../Topic/CMFCVisualManager::OnDrawRibbonGalleryButton.md)||  
|[CMFCVisualManager::OnDrawRibbonKeyTip](../Topic/CMFCVisualManager::OnDrawRibbonKeyTip.md)||  
|[CMFCVisualManager::OnDrawRibbonLabel](../Topic/CMFCVisualManager::OnDrawRibbonLabel.md)|リボン ラベルを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonMainPanelButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonMainPanelButtonBorder.md)|**メイン** パネルに配置されるリボン ボタンの境界線を描画するときに、フレームワークによって呼び出されます。  **メイン** パネルは、ユーザーが**メイン ボタン**をクリックしたときに表示されるパネルです。|  
|[CMFCVisualManager::OnDrawRibbonMainPanelFrame](../Topic/CMFCVisualManager::OnDrawRibbonMainPanelFrame.md)|**メイン** パネルの周囲に境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonMenuCheckFrame](../Topic/CMFCVisualManager::OnDrawRibbonMenuCheckFrame.md)||  
|[CMFCVisualManager::OnDrawRibbonPanel](../Topic/CMFCVisualManager::OnDrawRibbonPanel.md)|リボン パネルを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonPanelCaption](../Topic/CMFCVisualManager::OnDrawRibbonPanelCaption.md)|リボン パネルのキャプションを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonProgressBar](../Topic/CMFCVisualManager::OnDrawRibbonProgressBar.md)|[CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) オブジェクトを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonQuickAccessToolBarSeparator](../Topic/CMFCVisualManager::OnDrawRibbonQuickAccessToolBarSeparator.md)|リボンの**クイック アクセス ツール バー**に区分線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonRecentFilesFrame](../Topic/CMFCVisualManager::OnDrawRibbonRecentFilesFrame.md)|最近使用したファイルの一覧の周囲にフレームを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManager::OnDrawRibbonSliderChannel.md)|[CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) オブジェクトのチャネルを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManager::OnDrawRibbonSliderThumb.md)|`CMFCRibbonSlider` オブジェクトのつまみを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManager::OnDrawRibbonSliderZoomButton.md)|`CMFCRibbonSlider` オブジェクトのズーム ボタンを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonStatusBarPane](../Topic/CMFCVisualManager::OnDrawRibbonStatusBarPane.md)|リボンのステータス バーにペインを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawRibbonTabsFrame](../Topic/CMFCVisualManager::OnDrawRibbonTabsFrame.md)|一連のリボン タブの周囲にフレームを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawScrollButtons](../Topic/CMFCVisualManager::OnDrawScrollButtons.md)||  
|[CMFCVisualManager::OnDrawSeparator](../Topic/CMFCVisualManager::OnDrawSeparator.md)|区分線を描画するときに、フレームワークによって呼び出されます。  区分線は、一般的に、アイコンのグループを仕切るためにコントロール バーで使用されます。|  
|[CMFCVisualManager::OnDrawShowAllMenuItems](../Topic/CMFCVisualManager::OnDrawShowAllMenuItems.md)||  
|[CMFCVisualManager::OnDrawSpinButtons](../Topic/CMFCVisualManager::OnDrawSpinButtons.md)|スピン ボタンを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawSplitterBorder](../Topic/CMFCVisualManager::OnDrawSplitterBorder.md)|分割ウィンドウの境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawSplitterBox](../Topic/CMFCVisualManager::OnDrawSplitterBox.md)|分割ウィンドウの分割ドラッグ ボックスを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawStatusBarPaneBorder](../Topic/CMFCVisualManager::OnDrawStatusBarPaneBorder.md)|ステータス バー ペインの境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawStatusBarProgress](../Topic/CMFCVisualManager::OnDrawStatusBarProgress.md)|ステータス バーのプログレス インジケーターの境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManager::OnDrawStatusBarSizeBox.md)|ステータス バーのサイズ ボックスの境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawTab](../Topic/CMFCVisualManager::OnDrawTab.md)|[CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md) オブジェクトを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawTabCloseButton](../Topic/CMFCVisualManager::OnDrawTabCloseButton.md)|アクティブなタブに**閉じる**ボタンを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawTabContent](../Topic/CMFCVisualManager::OnDrawTabContent.md)|タブの内容 \(イメージ、テキスト\) を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawTabsButtonBorder](../Topic/CMFCVisualManager::OnDrawTabsButtonBorder.md)|タブ ボタンの境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawTask](../Topic/CMFCVisualManager::OnDrawTask.md)|作業ウィンドウにタスクを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawTasksGroupAreaBorder](../Topic/CMFCVisualManager::OnDrawTasksGroupAreaBorder.md)|作業ウィンドウのグループ領域の周囲に境界線を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawTasksGroupCaption](../Topic/CMFCVisualManager::OnDrawTasksGroupCaption.md)|作業ウィンドウ上のタスク グループのキャプションを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawTasksGroupIcon](../Topic/CMFCVisualManager::OnDrawTasksGroupIcon.md)||  
|[CMFCVisualManager::OnDrawTearOffCaption](../Topic/CMFCVisualManager::OnDrawTearOffCaption.md)|ティアオフ バーのティアオフ キャプションを描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnDrawToolBoxFrame](../Topic/CMFCVisualManager::OnDrawToolBoxFrame.md)||  
|[CMFCVisualManager::OnEraseMDIClientArea](../Topic/CMFCVisualManager::OnEraseMDIClientArea.md)|MDI クライアント領域を消去するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnErasePopupWindowButton](../Topic/CMFCVisualManager::OnErasePopupWindowButton.md)||  
|[CMFCVisualManager::OnEraseTabsArea](../Topic/CMFCVisualManager::OnEraseTabsArea.md)|タブ ウィンドウ内のタブ領域を消去するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnEraseTabsButton](../Topic/CMFCVisualManager::OnEraseTabsButton.md)|タブ ボタンのアイコンとテキストを消去するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnEraseTabsFrame](../Topic/CMFCVisualManager::OnEraseTabsFrame.md)|タブ フレームを消去するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManager::OnFillAutoHideButtonBackground.md)|自動非表示ボタンの背景を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillBarBackground](../Topic/CMFCVisualManager::OnFillBarBackground.md)|コントロール バーの背景を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillButtonInterior](../Topic/CMFCVisualManager::OnFillButtonInterior.md)|ツール バー ボタンの背景を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillCaptionBarButton](../Topic/CMFCVisualManager::OnFillCaptionBarButton.md)||  
|[CMFCVisualManager::OnFillCommandsListBackground](../Topic/CMFCVisualManager::OnFillCommandsListBackground.md)|これからカスタム ダイアログ ボックスの一部となるコマンド リストに属するツール バー ボタンの背景を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillHeaderCtrlBackground](../Topic/CMFCVisualManager::OnFillHeaderCtrlBackground.md)|ヘッダー コントロールの背景を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillMiniFrameCaption](../Topic/CMFCVisualManager::OnFillMiniFrameCaption.md)|ミニフレーム ウィンドウのキャプションを塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillOutlookBarCaption](../Topic/CMFCVisualManager::OnFillOutlookBarCaption.md)|Outlook のキャプションの背景を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillOutlookPageButton](../Topic/CMFCVisualManager::OnFillOutlookPageButton.md)|Outlook のページ ボタンの内部を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillPopupWindowBackground](../Topic/CMFCVisualManager::OnFillPopupWindowBackground.md)|ポップアップ ウィンドウの背景を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillRibbonButton](../Topic/CMFCVisualManager::OnFillRibbonButton.md)|リボン ボタンの内部を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillRibbonEdit](../Topic/CMFCVisualManager::OnFillRibbonEdit.md)|リボン エディット コントロールの内部を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillRibbonMainPanelButton](../Topic/CMFCVisualManager::OnFillRibbonMainPanelButton.md)|**メイン** パネルにあるリボン ボタンの内部を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillRibbonMenuFrame](../Topic/CMFCVisualManager::OnFillRibbonMenuFrame.md)|メイン リボン パネルのメニュー フレームを塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](../Topic/CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup.md)||  
|[CMFCVisualManager::OnFillSplitterBackground](../Topic/CMFCVisualManager::OnFillSplitterBackground.md)|分割ウィンドウの背景を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillTab](../Topic/CMFCVisualManager::OnFillTab.md)|タブの背景を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillTasksGroupInterior](../Topic/CMFCVisualManager::OnFillTasksGroupInterior.md)|[CMFCTasksPane](../Topic/CMFCTasksPane%20Class.md) 上の [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) オブジェクトの内部を塗りつぶすために、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnFillTasksPaneBackground](../Topic/CMFCVisualManager::OnFillTasksPaneBackground.md)|`CMFCTasksPane` コントロールの背景を塗りつぶすときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnHighlightMenuItem](../Topic/CMFCVisualManager::OnHighlightMenuItem.md)|強調表示されたメニュー項目を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnHighlightRarelyUsedMenuItems](../Topic/CMFCVisualManager::OnHighlightRarelyUsedMenuItems.md)|ほとんど使用されない、強調表示されたメニュー項目を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnNcPaint](../Topic/CMFCVisualManager::OnNcPaint.md)|非クライアント領域を描画するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnSetWindowRegion](../Topic/CMFCVisualManager::OnSetWindowRegion.md)|フレームとポップアップ メニューのある領域を設定するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::OnUpdateSystemColors](../Topic/CMFCVisualManager::OnUpdateSystemColors.md)|システム カラー設定を変更するときに、フレームワークによって呼び出されます。|  
|[CMFCVisualManager::RedrawAll](../Topic/CMFCVisualManager::RedrawAll.md)|アプリケーションのすべてのコントロール バーを再描画します。|  
|[CMFCVisualManager::RibbonCategoryColorToRGB](../Topic/CMFCVisualManager::RibbonCategoryColorToRGB.md)||  
|[CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)|既定のビジュアル マネージャーを設定します。|  
|[CMFCVisualManager::SetEmbossDisabledImage](../Topic/CMFCVisualManager::SetEmbossDisabledImage.md)|無効なツール バー イメージのエンボス モードを有効または無効にします。|  
|[CMFCVisualManager::SetFadeInactiveImage](../Topic/CMFCVisualManager::SetFadeInactiveImage.md)|メニューまたはツール バー上のアクティブでないイメージのライティング効果を有効または無効にします。|  
|[CMFCVisualManager::SetMenuFlatLook](../Topic/CMFCVisualManager::SetMenuFlatLook.md)|アプリケーション メニュー ボタンの外観がフラットかどうかを示すフラグを設定します。|  
|[CMFCVisualManager::SetMenuShadowDepth](../Topic/CMFCVisualManager::SetMenuShadowDepth.md)|メニュー シャドウの幅と高さを設定します。|  
|[CMFCVisualManager::SetShadowHighlightedImage](../Topic/CMFCVisualManager::SetShadowHighlightedImage.md)|強調表示されたイメージを描画するときに影を表示するかどうかを示すフラグを設定します。|  
  
## 解説  
 `CMFCVisualManager` クラスはアプリケーションの GUI を制御します。このため、各アプリケーションは `CMFCVisualManager` のインスタンスを 1 つ、または `CMFCVisualManager` から派生したクラスのインスタンスを 1 つ持つことができます。  また、アプリケーションは、`CMFCVisualManager` がない場合も機能します。  現在の `CMFCVisualManager` 派生オブジェクトへのポインターを取得するには、`GetInstance` 静的メソッドを使用します。  
  
 アプリケーションの外観を変更するには、アプリケーションのすべてのビジュアル要素を描画するメソッドを提供する他のクラスを使用する必要があります。  そのようなクラスには、[CMFCVisualManagerOfficeXP クラス](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)、[CMFCVisualManagerOffice2003 クラス](../Topic/CMFCVisualManagerOffice2003%20Class.md)、[CMFCVisualManagerOffice2007 クラス](../../mfc/reference/cmfcvisualmanageroffice2007-class.md)などがあります。  アプリケーションの外観を変更する場合は、このようなビジュアル マネージャーのどれかを `SetDefaultManager` メソッドに渡します。  アプリケーションの外観を Microsoft Office 2003 と同様にする方法の例については、「[CMFCVisualManagerOffice2003 クラス](../Topic/CMFCVisualManagerOffice2003%20Class.md)」を参照してください。  
  
 描画メソッドはすべて仮想です。  これにより、アプリケーションの GUI 用にカスタム ビジュアル スタイルを作成できます。  独自のビジュアル スタイルを作成するには、ビジュアル マネージャー クラスの派生クラスのどれかを作成し、変更する描画メソッドをオーバーライドします。  
  
## 使用例  
 このサンプルは、標準およびカスタムの `CMFCVisualManager` オブジェクトをインスタンス化する方法の例を示しています。  
  
```  
void CMFCSkinsApp::SetSkin (int iIndex)  
{   // destroy the current visual manager  
   if (CMFCVisualManager::GetInstance () != NULL)  
   {  
      delete CMFCVisualManager::GetInstance ();  
   }  
   switch (iIndex)  
  {  
   case 0:  
      CMFCVisualManager::GetInstance (); // create the standard visual manager  
      break;  
   case 1:  
      new CMyVisualManager (); // create the first custom visual manager  
      break;  
   case 2:  
      new CMacStyle ();  // create the second custom visual manager  
      break;  
   }  
  
   // access the manager and set it properly  
   CMFCVisualManager::GetInstance ()->SetLook2000 ();  
   CMFCVisualManager::GetInstance ()->RedrawAll ();  
}  
```  
  
## 使用例  
 `CMFCVisualManager` オブジェクトの既定値を取得する方法を次に示します。  このコード スニペットは [タスク ウィンドウのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_TasksPane#1](../../mfc/reference/codesnippet/CPP/cmfcvisualmanager-class_1.h)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
## 必要条件  
 **ヘッダー :** afxvisualmanager.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md)   
 [ビジュアル マネージャー](../../mfc/visualization-manager.md)