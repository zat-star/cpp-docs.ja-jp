---
title: "CDockSite クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockSite クラス"
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CDockSite クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 [CPane クラス](../../mfc/reference/cpane-class.md)から派生したペインを一連の行に配置する機能を提供します。  
  
## 構文  
  
```  
class CDockSite: public CBasePane  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDockSite::AddRow](../Topic/CDockSite::AddRow.md)||  
|[CDockSite::AdjustDockingLayout](../Topic/CDockSite::AdjustDockingLayout.md)|\([CBasePane::AdjustDockingLayout](../Topic/CBasePane::AdjustDockingLayout.md) をオーバーライドします\)。|  
|[CDockSite::AdjustLayout](../Topic/CDockSite::AdjustLayout.md)|\([CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md) をオーバーライドします\)。|  
|[CDockSite::AlignDockSite](../Topic/CDockSite::AlignDockSite.md)||  
|[CDockSite::CalcFixedLayout](../Topic/CDockSite::CalcFixedLayout.md)|\([CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md) をオーバーライドします\)。|  
|[CDockSite::CanAcceptPane](../Topic/CDockSite::CanAcceptPane.md)|\([CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md) をオーバーライドします\)。|  
|[CDockSite::CreateEx](../Topic/CDockSite::CreateEx.md)|\([CBasePane::CreateEx](../Topic/CBasePane::CreateEx.md) をオーバーライドします\)。|  
|[CDockSite::CreateRow](../Topic/CDockSite::CreateRow.md)||  
|[CDockSite::DockPane](../Topic/CDockSite::DockPane.md)|\([CBasePane::DockPane](../Topic/CBasePane::DockPane.md) をオーバーライドします\)。|  
|[CDockSite::DoesAllowDynInsertBefore](../Topic/CDockSite::DoesAllowDynInsertBefore.md)|\([CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md) をオーバーライドします\)。|  
|[CDockSite::FindRowIndex](../Topic/CDockSite::FindRowIndex.md)||  
|[CDockSite::FixupVirtualRects](../Topic/CDockSite::FixupVirtualRects.md)||  
|[CDockSite::GetDockSiteID](../Topic/CDockSite::GetDockSiteID.md)||  
|[CDockSite::GetDockSiteRowsList](../Topic/CDockSite::GetDockSiteRowsList.md)||  
|[CDockSite::IsAccessibilityCompatible](../Topic/CDockSite::IsAccessibilityCompatible.md)|\(`CBasePane::IsAccessibilityCompatible` をオーバーライドします\)。|  
|[CDockSite::IsDragMode](../Topic/CDockSite::IsDragMode.md)||  
|[CDockSite::IsLastRow](../Topic/CDockSite::IsLastRow.md)||  
|[CDockSite::IsRectWithinDockSite](../Topic/CDockSite::IsRectWithinDockSite.md)||  
|[CDockSite::IsResizable](../Topic/CDockSite::IsResizable.md)|\([CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md) をオーバーライドします\)。|  
|[CDockSite::MovePane](../Topic/CDockSite::MovePane.md)||  
|[CDockSite::OnInsertRow](../Topic/CDockSite::OnInsertRow.md)||  
|[CDockSite::OnRemoveRow](../Topic/CDockSite::OnRemoveRow.md)||  
|[CDockSite::OnResizeRow](../Topic/CDockSite::OnResizeRow.md)||  
|[CDockSite::OnSetWindowPos](../Topic/CDockSite::OnSetWindowPos.md)||  
|[CDockSite::OnShowRow](../Topic/CDockSite::OnShowRow.md)||  
|[CDockSite::OnSizeParent](../Topic/CDockSite::OnSizeParent.md)||  
|[CDockSite::PaneFromPoint](../Topic/CDockSite::PaneFromPoint.md)|パラメーターによって指定された点にあるドッキング サイトにドッキングされているペインを返します。|  
|[CDockSite::DockPaneLeftOf](../Topic/CDockSite::DockPaneLeftOf.md)|ペインを別のペインの左側にドッキングします。|  
|[CDockSite::FindPaneByID](../Topic/CDockSite::FindPaneByID.md)|指定された ID によって識別されるペインを返します。|  
|[CDockSite::GetPaneList](../Topic/CDockSite::GetPaneList.md)|ドッキング サイトにドッキングされているペインの一覧を返します。|  
|[CDockSite::RectSideFromPoint](../Topic/CDockSite::RectSideFromPoint.md)||  
|[CDockSite::RemovePane](../Topic/CDockSite::RemovePane.md)||  
|[CDockSite::RemoveRow](../Topic/CDockSite::RemoveRow.md)||  
|[CDockSite::ReplacePane](../Topic/CDockSite::ReplacePane.md)||  
|[CDockSite::RepositionPanes](../Topic/CDockSite::RepositionPanes.md)||  
|[CDockSite::ResizeDockSite](../Topic/CDockSite::ResizeDockSite.md)||  
|[CDockSite::ResizeRow](../Topic/CDockSite::ResizeRow.md)||  
|[CDockSite::ShowPane](../Topic/CDockSite::ShowPane.md)|ペインを表示します。|  
|[CDockSite::ShowRow](../Topic/CDockSite::ShowRow.md)||  
|[CDockSite::SwapRows](../Topic/CDockSite::SwapRows.md)||  
  
## 解説  
 [CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md) を呼び出すと、フレームワークが自動的に `CDockSite` オブジェクトを作成します。  ドッキング サイト ウィンドウは、メイン フレーム ウィンドウ上のクライアント領域の端に配置されます。  
  
 通常、ドッキング サイトによって提供されるサービスは [CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md) によって処理されるため、これらのサービスを呼び出す必要はありません。  
  
## 使用例  
 次の例では、`CDockSite` クラスのオブジェクトを作成する方法を示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/CPP/cdocksite-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md) [CCmdTarget](../Topic/CCmdTarget%20Class.md) [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## 必要条件  
 **ヘッダー:** afxDockSite.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CBasePane クラス](../../mfc/reference/cbasepane-class.md)