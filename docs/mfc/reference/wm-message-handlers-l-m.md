---
title: "WM_ で始まるメッセージのハンドラー : L - M | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_WM_MENUSELECT"
  - "ON_WM_MBUTTONDBLCLK"
  - "ON_WM_MOUSEACTIVATE"
  - "ON_WM_MOUSEMOVE"
  - "ON_WM_MOVING"
  - "ON_WM_LBUTTONUP"
  - "ON_WM_LBUTTONDBLCLK"
  - "ON_WM_MEASUREITEM"
  - "ON_WM_MDIACTIVATE"
  - "ON_WM_MOVE"
  - "ON_WM_LBUTTONDOWN"
  - "ON_WM_MBUTTONDOWN"
  - "ON_WM_MENUCHAR"
  - "ON_WM_MBUTTONUP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_LBUTTONDBLCLK"
  - "ON_WM_LBUTTONDOWN"
  - "ON_WM_LBUTTONUP"
  - "ON_WM_MBUTTONDBLCLK"
  - "ON_WM_MBUTTONDOWN"
  - "ON_WM_MBUTTONUP"
  - "ON_WM_MDIACTIVATE"
  - "ON_WM_MEASUREITEM"
  - "ON_WM_MENUCHAR"
  - "ON_WM_MENUSELECT"
  - "ON_WM_MOUSEACTIVATE"
  - "ON_WM_MOUSEMOVE"
  - "ON_WM_MOVE"
  - "ON_WM_MOVING"
  - "WM_ メッセージ"
ms.assetid: 96ecaaf1-6d13-4e12-a454-535635967489
caps.latest.revision: 15
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WM_ で始まるメッセージのハンドラー : L - M
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

右側の関数プロトタイプに対応する左側のマップ エントリを次に示します。  
  
|マップ エントリ|関数プロトタイプ|  
|--------------|--------------|  
|ON\_WM\_LBUTTONDBLCLK\(\)|afx\_msg void な [OnLButtonDblClk](../Topic/CWnd::OnLButtonDblClk.md) \(UINT、CPoint\) ;|  
|ON\_WM\_LBUTTONDOWN\(\)|afx\_msg void な [OnLButtonDown](../Topic/CWnd::OnLButtonDown.md) \(UINT、CPoint\) ;|  
|ON\_WM\_LBUTTONUP\(\)|afx\_msg void な [OnLButtonUp](../Topic/CWnd::OnLButtonUp.md) \(UINT、CPoint\) ;|  
|ON\_WM\_MBUTTONDBLCLK\(\)|afx\_msg void な [OnMButtonDblClk](../Topic/CWnd::OnMButtonDblClk.md) \(UINT、CPoint\) ;|  
|ON\_WM\_MBUTTONDOWN\(\)|afx\_msg void な [OnMButtonDown](../Topic/CWnd::OnMButtonDown.md) \(UINT、CPoint\) ;|  
|ON\_WM\_MBUTTONUP\(\)|afx\_msg void な [OnMButtonUp](../Topic/CWnd::OnMButtonUp.md) \(UINT、CPoint\) ;|  
|ON\_WM\_MDIACTIVATE\(\)|afx\_msg void な [OnMDIActivate](../Topic/CWnd::OnMDIActivate.md) \(ブール型、CWnd\*、CWnd\*\) ;|  
|ON\_WM\_MEASUREITEM\(\)|afx\_msg void な [OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)LPMEASUREITEMSTRUCT \(\) ;|  
|ON\_WM\_MENUCHAR\(\)|afx\_msg LONG な [OnMenuChar](../Topic/CWnd::OnMenuChar.md) \(UINT、UINT、CMenu\*\) ;|  
|ON\_WM\_MENUDRAG\(\)|afx\_msg UINT [OnMenuDrag](../Topic/CWnd::OnMenuDrag.md) \(UINT、CMenu\*\) ;|  
|ON\_WM\_MENUGETOBJECT\(\)|afx\_msg [OnMenuGetObject](../Topic/CWnd::OnMenuGetObject.md) \(UINT MENUGETOBJECTINFO\*\) ;|  
|ON\_WM\_MENURBUTTONUP\(\)|afx\_msg void な [OnMenuRButtonUp](../Topic/CWnd::OnMenuRButtonUp.md) \(UINT、CMenu\*\) ;|  
|ON\_WM\_MENUSELECT\(\)|afx\_msg void な [OnMenuSelect](../Topic/CWnd::OnMenuSelect.md) \(UINT、UINT、HMENU\) ;|  
|ON\_WM\_MOUSEACTIVATE\(\)|afx\_msg [OnMouseActivate](../Topic/CWnd::OnMouseActivate.md)int \(CWnd\*、UINT、UINT\) ;|  
|ON\_WM\_MOUSEHOVER\(\)|afx\_msg void な [OnMouseHover](../Topic/CWnd::OnMouseHover.md) \(UINT、CPoint\) ;|  
|ON\_WM\_MOUSEHWHEEL\(\)|afx\_msg void な [OnMouseHWheel](../Topic/CWnd::OnMouseHWheel.md) \(UINT の short、CPoint\) ;|  
|ON\_WM\_MOUSELEAVE\(\)|afx\_msg void な [OnMouseLeave](../Topic/CWnd::OnMouseLeave.md) \(\) ;|  
|ON\_WM\_MOUSEMOVE\(\)|afx\_msg void な [OnMouseMove](../Topic/CWnd::OnMouseMove.md) \(UINT、CPoint\) ;|  
|ON\_WM\_MOUSEWHEEL\(\)|afx\_msg BOOL [OnMouseWheel](../Topic/CWnd::OnMouseWheel.md) \(UINT の short、CPoint\) ;|  
|ON\_WM\_MOVE\(\)|afx\_msg void な [位置](../Topic/CWnd::OnMove.md) \(int、int\) ;|  
|ON\_WM\_MOVING\(\)|afx\_msg void な [OnMoving](../Topic/CWnd::OnMoving.md) \(UINT、LPRECT\) ;|  
  
## 参照  
 [メッセージ マップ](../../mfc/reference/message-maps-mfc.md)   
 [WM\_ で始まるメッセージのハンドラー](../../mfc/reference/handlers-for-wm-messages.md)