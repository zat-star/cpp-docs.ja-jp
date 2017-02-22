---
title: "CMFCVisualManagerWindows7 クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxvisualmanagerwindows7/CMFCVisualManagerWindows7"
  - "CMFCVisualManagerWindows7"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerWindows7 クラス"
ms.assetid: e8d87df1-0c09-4b58-8ade-4e911f796e42
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMFCVisualManagerWindows7 クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerWindows7` は、アプリケーションを [!INCLUDE[win7](../../build/includes/win7_md.md)] の外観にします。  
  
## 構文  
  
```  
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCVisualManagerWindows7::CMFCVisualManagerWindows7](../Topic/CMFCVisualManagerWindows7::CMFCVisualManagerWindows7.md)|既定のコンストラクターです。|  
|[CMFCVisualManagerWindows7::~CMFCVisualManagerWindows7](../Topic/CMFCVisualManagerWindows7::~CMFCVisualManagerWindows7.md)|既定のデストラクター。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|`CMFCVisualManagerWindows7::CleanStyle`|現在の visual スタイルをクリアし、既定の visual スタイルをリセットします。|  
|`CMFCVisualManagerWindows7::CleanUp`|すべてのユーザー インターフェイス オブジェクトをオフにし、メニューをリセットします。|  
|`CMFCVisualManagerWindows7::DrawNcBtn`|フレームの非クライアント領域のボタンを描画します。  フレームワークは、描画するために、このメソッドを最小化し、最大になりますが、フレーム ウィンドウの右上隅の末尾とボタンを復元使用します。  このメソッドは、プログラムが非の Aero テーマを使用するときに呼び出されます。|  
|`CMFCVisualManagerWindows7::DrawNcText`|描画は、フレームの非クライアント領域にテキストを表示します。  フレームワークは、フレーム ウィンドウの上部にあるタイトル バーのアプリケーションのタイトルを描画するには、このメソッドを使用します。|  
|`CMFCVisualManagerWindows7::DrawSeparator`|[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)の区分線を描画します。|  
|`CMFCVisualManagerWindows7::GetRibbonBar`|ユーザー インターフェイスに関連付けられている [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md) を取得します。|  
|[CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor](../Topic/CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor.md)|リボン編集ボックスの背景色を取得します。|  
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|[CMFCVisualManager::GetRibbonPopupBorderSize](../Topic/CMFCVisualManager::GetRibbonPopupBorderSize.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|[CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|[CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|[CMFCVisualManagerWindows::IsHighlightWholeMenuItem](../Topic/CMFCVisualManagerWindows::IsHighlightWholeMenuItem.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|[CMFCVisualManager::IsOwnerDrawMenuCheck](../Topic/CMFCVisualManager::IsOwnerDrawMenuCheck.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::IsRibbonPresent`|`CMFCRibbonBar` が存在し、表示されるかどうかを判定します。|  
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|[CMFCVisualManagerWindows::OnDrawButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawButtonBorder.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|[CMFCVisualManagerWindows::OnDrawCheckBoxEx](../Topic/CMFCVisualManagerWindows::OnDrawCheckBoxEx.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|[CMFCVisualManagerWindows::OnDrawComboDropButton](../Topic/CMFCVisualManagerWindows::OnDrawComboDropButton.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|[CMFCVisualManager::OnDrawDefaultRibbonImage](../Topic/CMFCVisualManager::OnDrawDefaultRibbonImage.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|[CMFCVisualManagerWindows::OnDrawMenuBorder](../Topic/CMFCVisualManagerWindows::OnDrawMenuBorder.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|[CMFCVisualManager::OnDrawMenuCheck](../Topic/CMFCVisualManager::OnDrawMenuCheck.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|[CMFCVisualManager::OnDrawMenuLabel](../Topic/CMFCVisualManager::OnDrawMenuLabel.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|`CMFCVisualManager::OnDrawRadioButton` をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|[CMFCVisualManager::OnDrawRibbonApplicationButton](../Topic/CMFCVisualManager::OnDrawRibbonApplicationButton.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|[CMFCVisualManager::OnDrawRibbonButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonButtonBorder.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|[CMFCVisualManager::OnDrawRibbonCaption](../Topic/CMFCVisualManager::OnDrawRibbonCaption.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|[CMFCVisualManager::OnDrawRibbonCaptionButton](../Topic/CMFCVisualManager::OnDrawRibbonCaptionButton.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|[CMFCVisualManager::OnDrawRibbonCategory](../Topic/CMFCVisualManager::OnDrawRibbonCategory.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|[CMFCVisualManager::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManager::OnDrawRibbonCategoryTab.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|[CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButton.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|[CMFCVisualManager::OnDrawRibbonGalleryButton](../Topic/CMFCVisualManager::OnDrawRibbonGalleryButton.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|`CMFCVisualManager::OnDrawRibbonLaunchButton` をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|[CMFCVisualManager::OnDrawRibbonMenuCheckFrame](../Topic/CMFCVisualManager::OnDrawRibbonMenuCheckFrame.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|[CMFCVisualManager::OnDrawRibbonPanel](../Topic/CMFCVisualManager::OnDrawRibbonPanel.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|[CMFCVisualManager::OnDrawRibbonPanelCaption](../Topic/CMFCVisualManager::OnDrawRibbonPanelCaption.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|[CMFCVisualManager::OnDrawRibbonProgressBar](../Topic/CMFCVisualManager::OnDrawRibbonProgressBar.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|[CMFCVisualManager::OnDrawRibbonRecentFilesFrame](../Topic/CMFCVisualManager::OnDrawRibbonRecentFilesFrame.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|[CMFCVisualManager::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManager::OnDrawRibbonSliderChannel.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|[CMFCVisualManager::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManager::OnDrawRibbonSliderThumb.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|[CMFCVisualManager::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManager::OnDrawRibbonSliderZoomButton.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|[CMFCVisualManager::OnDrawRibbonStatusBarPane](../Topic/CMFCVisualManager::OnDrawRibbonStatusBarPane.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|[CMFCVisualManager::OnDrawRibbonTabsFrame](../Topic/CMFCVisualManager::OnDrawRibbonTabsFrame.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|[CMFCVisualManagerWindows::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarSizeBox.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnFillBarBackground`|[CMFCVisualManagerWindows::OnFillBarBackground](../Topic/CMFCVisualManagerWindows::OnFillBarBackground.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|[CMFCVisualManagerWindows::OnFillButtonInterior](../Topic/CMFCVisualManagerWindows::OnFillButtonInterior.md) をオーバーライドします。|  
|[CMFCVisualManagerWindows7::OnFillMenuImageRect](../Topic/CMFCVisualManagerWindows7::OnFillMenuImageRect.md)|フレームワークは、メニュー項目のイメージの周囲を塗りつぶすときにこのメソッドを呼び出します。|  
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|[CMFCVisualManager::OnFillRibbonButton](../Topic/CMFCVisualManager::OnFillRibbonButton.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|[CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](../Topic/CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|[CMFCVisualManagerWindows::OnHighlightMenuItem](../Topic/CMFCVisualManagerWindows::OnHighlightMenuItem.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnNcActivate`|[CMFCVisualManager::OnNcActivate](../Topic/CMFCVisualManager::OnNcActivate.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnNcPaint`|[CMFCVisualManager::OnNcPaint](../Topic/CMFCVisualManager::OnNcPaint.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|[CMFCVisualManagerWindows::OnUpdateSystemColors](../Topic/CMFCVisualManagerWindows::OnUpdateSystemColors.md) をオーバーライドします。|  
|`CMFCVisualManagerWindows7::SetResourceHandle`|ビジュアル マネージャーの属性を記述するリソース ハンドルを設定します。|  
|`CMFCVisualManagerWindows7::SetStyle`|`CMFCVisualManagerWindows7` GUI の配色を設定します。|  
  
## 解説  
 アプリケーションの外観を既定の [!INCLUDE[win7](../../build/includes/win7_md.md)] アプリケーションのように変更するには、`CMFCVisualManagerWindows7` クラスを使用します。  このクラスは、[!INCLUDE[win7](../../build/includes/win7_md.md)] より前のバージョンの Windows でアプリケーションを実行する場合は有効ではないことがあります。  この場合、アプリケーションは [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md) で定義された既定のビジュアル マネージャーを使用します。  
  
 CMFCVisualManagerWindows7 は、[CMFCVisualManagerWindows クラス](../../mfc/reference/cmfcvisualmanagerwindows-class.md) と `CMFCVisualManager` クラスの両方から複数のメソッドを継承します。  前のセクションに記載されたメソッドは、`CMFCVisualManagerWindows7` クラスの新しいメソッドです。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
 `CMFCVisualManagerWindows7`  
  
## 必要条件  
 **ヘッダー:** afxvisualmanagerwindows7.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCVisualManager クラス](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerWindows クラス](../../mfc/reference/cmfcvisualmanagerwindows-class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)