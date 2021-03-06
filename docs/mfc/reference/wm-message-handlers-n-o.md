---
title: "Wm _ で始まるメッセージのハンドラー: N-O |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_WM_NCHITTEST
- ON_WM_NCLBUTTONDOWN
- ON_WM_NCCALCSIZE
- ON_WM_NCLBUTTONUP
- ON_WM_NCPAINT
- ON_WM_NCMBUTTONUP
- ON_WM_NCCREATE
- ON_WM_NCACTIVATE
- ON_WM_NCMOUSEMOVE
- ON_WM_NCRBUTTONDBLCLK
- ON_WM_NCLBUTTONDBLCLK
- ON_WM_NCDESTROY
- ON_WM_NCMBUTTONDBLCLK
- ON_WM_NCRBUTTONDOWN
- ON_WM_NCRBUTTONUP
- ON_WM_NCMBUTTONDOWN
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_NCCALCSIZE [MFC]
- ON_WM_NCMBUTTONDOWN [MFC]
- ON_WM_NCRBUTTONDBLCLK [MFC]
- ON_WM_NCMBUTTONDBLCLK [MFC]
- ON_WM_NCLBUTTONDBLCLK [MFC]
- ON_WM_NCDESTROY [MFC]
- ON_WM_NCRBUTTONDOWN [MFC]
- ON_WM_NCLBUTTONDOWN [MFC]
- ON_WM_NCCREATE [MFC]
- ON_WM_NCRBUTTONUP [MFC]
- ON_WM_NCLBUTTONUP [MFC]
- ON_WM_NCPAINT [MFC]
- ON_WM_NCACTIVATE [MFC]
- ON_WM_NCHITTEST [MFC]
- ON_WM_NCMOUSEMOVE [MFC]
- ON_WM_NCMBUTTONUP [MFC]
- WM_ messages
ms.assetid: 4efd1cda-b642-4e8b-89e8-73255fa70d77
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 108afac12d47c009b423e62321eb31a78e2c09d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="wm-message-handlers-n---o"></a>WM_ で始まるメッセージのハンドラー : N - O
左側の次のマップ エントリは、右側の関数プロトタイプに対応します。  
  
|マップのエントリ|関数プロトタイプ|  
|---------------|------------------------|  
|ON_WM_NCACTIVATE()|afx_msg BOOL [OnNcActivate](../../mfc/reference/cwnd-class.md#onncactivate)(ブール値)。|  
|ON_WM_NCCALCSIZE()|afx_msg void [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)(BOOL、NCCALCSIZE_PARAMS FAR *) です。|  
|ON_WM_NCCREATE()|afx_msg BOOL [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)(LPCREATESTRUCT) です。|  
|ON_WM_NCDESTROY()|afx_msg void [OnNcDestroy](../../mfc/reference/cwnd-class.md#onncdestroy)();|  
|ON_WM_NCHITTEST()|afx_msg LRESULT [OnNcHitTest](../../mfc/reference/cwnd-class.md#onnchittest)(CPoint) です。|  
|ON_WM_NCLBUTTONDBLCLK()|afx_msg void [OnNcLButtonDblClk](../../mfc/reference/cwnd-class.md#onnclbuttondblclk)(UINT、CPoint) です。|  
|ON_WM_NCLBUTTONDOWN()|afx_msg void [OnNcLButtonDown](../../mfc/reference/cwnd-class.md#onnclbuttondown)(UINT、CPoint) です。|  
|ON_WM_NCLBUTTONUP()|afx_msg void [OnNcLButtonUp](../../mfc/reference/cwnd-class.md#onnclbuttonup)(UINT、CPoint) です。|  
|ON_WM_NCMBUTTONDBLCLK()|afx_msg void [OnNcMButtonDblClk](../../mfc/reference/cwnd-class.md#onncmbuttondblclk)(UINT、CPoint) です。|  
|ON_WM_NCMBUTTONDOWN()|afx_msg void [OnNcMButtonDown](../../mfc/reference/cwnd-class.md#onncmbuttondown)(UINT、CPoint) です。|  
|ON_WM_NCMBUTTONUP()|afx_msg void [OnNcMButtonUp](../../mfc/reference/cwnd-class.md#onncmbuttonup)(UINT、CPoint) です。|  
|ON_WM_NCMOUSEHOVER()|afx_msg void [OnNcMouseHover](../../mfc/reference/cwnd-class.md#onncmousehover)(UINT、CPoint) です。|  
|ON_WM_NCMOUSELEAVE()|afx_msg void [OnNcMouseLeave](../../mfc/reference/cwnd-class.md#onncmouseleave)();|  
|ON_WM_NCMOUSEMOVE()|afx_msg void [OnNcMouseMove](../../mfc/reference/cwnd-class.md#onncmousemove)(UINT、CPoint) です。|  
|ON_WM_NCPAINT()|afx_msg void [OnNcPaint](../../mfc/reference/cwnd-class.md#onncpaint)();|  
|ON_WM_NCRBUTTONDBLCLK()|afx_msg void [OnNcRButtonDblClk](../../mfc/reference/cwnd-class.md#onncrbuttondblclk)(UINT、CPoint) です。|  
|ON_WM_NCRBUTTONDOWN()|afx_msg void [OnNcRButtonDown](../../mfc/reference/cwnd-class.md#onncrbuttondown)(UINT、CPoint) です。|  
|ON_WM_NCRBUTTONUP()|afx_msg void [OnNcRButtonUp](../../mfc/reference/cwnd-class.md#onncrbuttonup)(UINT、CPoint) です。|  
|ON_WM_NCXBUTTONDBLCLK()|void [OnNcXButtonDblClk](../../mfc/reference/cwnd-class.md#onncxbuttondblclk)(短い形式、UINT、CPoint) です。|  
|ON_WM_NCXBUTTONDOWN()|afx_msg void [OnNcXButtonDown](../../mfc/reference/cwnd-class.md#onncxbuttondown)(短い形式、UINT、CPoint) です。|  
|ON_WM_NCXBUTTONUP()|afx_msg void [OnNcXButtonUp](../../mfc/reference/cwnd-class.md#onncxbuttonup)(短い形式、UINT、CPoint) です。|  
|ON_WM_NEXTMENU()|afx_msg void [OnNextMenu](../../mfc/reference/cwnd-class.md#onnextmenu)(UINT、LPMDINEXTMENU) です。|  
|ON_WM_NOTIFYFORMAT()|afx_msg UINT [OnNotifyFormat](../../mfc/reference/cwnd-class.md#onnotifyformat)(CWnd *、UINT) です。|  
  
## <a name="see-also"></a>参照  
 [メッセージ マップ](../../mfc/reference/message-maps-mfc.md)   
 [WM_ で始まるメッセージのハンドラー](../../mfc/reference/handlers-for-wm-messages.md)

