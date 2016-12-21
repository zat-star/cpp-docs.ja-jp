---
title: "CMFCVisualManagerVS2005 クラス | Microsoft Docs"
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
  - "CMFCVisualManagerVS2005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerVS2005 クラス"
ms.assetid: ea39b9ae-327e-4a51-bce7-dc84c78f005b
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCVisualManagerVS2005 クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerVS2005` は、アプリケーションを Microsoft Visual Studio 2005 の外観にします。  
  
## 構文  
  
```  
class CMFCVisualManagerVS2005 : public CMFCVisualManagerOffice2003  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCVisualManagerVS2005::GetDockingTabsBordersSize](../Topic/CMFCVisualManagerVS2005::GetDockingTabsBordersSize.md)|フレームワークは、ドッキングされタブが付けられるペインを描画するときに、このメソッドを呼び出します。  \([CMFCVisualManager::GetDockingTabsBordersSize](../Topic/CMFCVisualManager::GetDockingTabsBordersSize.md) をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::GetMDITabsBordersSize](../Topic/CMFCVisualManagerVS2005::GetMDITabsBordersSize.md)|フレームワークは、MDITabs ウィンドウを描画する前にこのメソッドを呼び出して、MDITabs ウィンドウの境界線のサイズを確認します。  \([CMFCVisualManager::GetMDITabsBordersSize](../Topic/CMFCVisualManager::GetMDITabsBordersSize.md) をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::GetPropertyGridGroupColor](../Topic/CMFCVisualManagerVS2005::GetPropertyGridGroupColor.md)|\([CMFCVisualManagerOffice2003::GetPropertyGridGroupColor](../Topic/CMFCVisualManagerOffice2003::GetPropertyGridGroupColor.md) をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::GetTabFrameColors](../Topic/CMFCVisualManagerVS2005::GetTabFrameColors.md)|\([CMFCVisualManagerOffice2003::GetTabFrameColors](../Topic/CMFCVisualManagerOffice2003::GetTabFrameColors.md) をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons](../Topic/CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons.md)|現在のビジュアル マネージャーで自動的に隠すボタンが重複しているかどうかを示す値を返します。  \([CMFCVisualManager::HasOverlappedAutoHideButtons](../Topic/CMFCVisualManager::HasOverlappedAutoHideButtons.md) をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder.md)|\([CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder.md) をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::OnDrawCaptionButton](../Topic/CMFCVisualManagerVS2005::OnDrawCaptionButton.md)|\(`CMFCVisualManagerOfficeXP::OnDrawCaptionButton` をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::OnDrawPaneCaption](../Topic/CMFCVisualManagerVS2005::OnDrawPaneCaption.md)|\([CMFCVisualManagerOffice2003::OnDrawPaneCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawPaneCaption.md) をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::OnDrawSeparator](../Topic/CMFCVisualManagerVS2005::OnDrawSeparator.md)|\([CMFCVisualManagerOffice2003::OnDrawSeparator](../Topic/CMFCVisualManagerOffice2003::OnDrawSeparator.md) をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::OnDrawTab](../Topic/CMFCVisualManagerVS2005::OnDrawTab.md)|\([CMFCVisualManagerOffice2003::OnDrawTab](../Topic/CMFCVisualManagerOffice2003::OnDrawTab.md) をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::OnDrawToolBoxFrame](../Topic/CMFCVisualManagerVS2005::OnDrawToolBoxFrame.md)|\([CMFCVisualManager::OnDrawToolBoxFrame](../Topic/CMFCVisualManager::OnDrawToolBoxFrame.md) をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::OnEraseTabsArea](../Topic/CMFCVisualManagerVS2005::OnEraseTabsArea.md)|\([CMFCVisualManagerOffice2003::OnEraseTabsArea](../Topic/CMFCVisualManagerOffice2003::OnEraseTabsArea.md) をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground.md)|\([CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground.md) をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::OnFillHighlightedArea](../Topic/CMFCVisualManagerVS2005::OnFillHighlightedArea.md)|\([CMFCVisualManagerOffice2003::OnFillHighlightedArea](../Topic/CMFCVisualManagerOffice2003::OnFillHighlightedArea.md) をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::OnFillMiniFrameCaption](../Topic/CMFCVisualManagerVS2005::OnFillMiniFrameCaption.md)|\(`CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption` をオーバーライドします。\)|  
|[CMFCVisualManagerVS2005::OnUpdateSystemColors](../Topic/CMFCVisualManagerVS2005::OnUpdateSystemColors.md)|\([CMFCVisualManagerOffice2003::OnUpdateSystemColors](../Topic/CMFCVisualManagerOffice2003::OnUpdateSystemColors.md) をオーバーライドします。\)|  
  
## 解説  
 CMFCVisualManagerVS2005 クラスを使用して、アプリケーションの外観を [!INCLUDE[vsprvsext](../Token/vsprvsext_md.md)] に似た外観に変更できます。  
  
 このクラスのすべてのメンバーは、このクラスの先祖である [CMFCVisualManager クラス](../../mfc/reference/cmfcvisualmanager-class.md)から派生した仮想関数です。  
  
## 使用例  
 ビジュアル マネージャー VS 2005 の使用方法を次の例に示します。  このコード スニペットは [デスクトップ通知デモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#9](../../mfc/reference/codesnippet/CPP/cmfcvisualmanagervs2005-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerOffice2003](../Topic/CMFCVisualManagerOffice2003%20Class.md)  
  
 [CMFCVisualManagerVS2005](../../mfc/reference/cmfcvisualmanagervs2005-class.md)  
  
## 必要条件  
 **ヘッダー :** afxvisualmanagervs2005.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCVisualManager クラス](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP クラス](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)   
 [CMFCVisualManagerWindows クラス](../../mfc/reference/cmfcvisualmanagerwindows-class.md)   
 [CMFCVisualManagerOffice2003 クラス](../Topic/CMFCVisualManagerOffice2003%20Class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)