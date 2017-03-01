---
title: "Wm _ で始まるメッセージのハンドラー: P-R |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_WM_RBUTTONUP
- ON_WM_PALETTECHANGED
- ON_WM_RBUTTONDBLCLK
- ON_WM_QUERYENDSESSION
- ON_WM_PARENTNOTIFY
- ON_WM_PALETTEISCHANGING
- ON_WM_QUERYOPEN
- ON_WM_PAINT
- ON_WM_QUERYNEWPALETTE
- ON_WM_RBUTTONDOWN
- ON_WM_RENDERALLFORMATS
- ON_WM_PAINTCLIPBOARD
- ON_WM_RENDERFORMAT
- ON_WM_QUERYDRAGICON
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_RENDERFORMAT
- ON_WM_QUERYOPEN
- ON_WM_RBUTTONDOWN
- ON_WM_PAINTCLIPBOARD
- ON_WM_QUERYNEWPALETTE
- ON_WM_RBUTTONUP
- ON_WM_PARENTNOTIFY
- ON_WM_RBUTTONDBLCLK
- ON_WM_PALETTECHANGED
- ON_WM_PALETTEISCHANGING
- ON_WM_QUERYDRAGICON
- ON_WM_PAINT
- ON_WM_RENDERALLFORMATS
- ON_WM_QUERYENDSESSION
- WM_ messages
ms.assetid: f46962e5-8329-4f1f-9b4d-fdad2a5ce1f8
caps.latest.revision: 15
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: c849c360902980d90587398ff4b035d11e6fa68e
ms.lasthandoff: 02/24/2017

---
# <a name="wm-messages-p---r"></a>WM_ で始まるメッセージのハンドラー : P - R
次のマップ エントリは、関数プロトタイプに対応しています。  
  
|マップ エントリ|関数プロトタイプ|  
|---------------|------------------------|  
|ON_WM_PAINT()|afx_msg void [OnPaint](../../mfc/reference/cwnd-class.md#onpaint)();|  
|ON_WM_PAINTCLIPBOARD()|afx_msg void [OnPaintClipboard](../../mfc/reference/cwnd-class.md#onpaintclipboard)(CWnd *、ハンドル)。|  
|ON_WM_PALETTECHANGED()|afx_msg void [OnPaletteChanged](../../mfc/reference/cwnd-class.md#onpalettechanged)(CWnd *)。|  
|ON_WM_PALETTEISCHANGING()|afx_msg void [OnPaletteIsChanging](../../mfc/reference/cwnd-class.md#onpaletteischanging)(CWnd *)。|  
|ON_WM_PARENTNOTIFY()|afx_msg void [OnParentNotify](../../mfc/reference/cwnd-class.md#onparentnotify); 全体の (UINT、LONG)|  
|ON_WM_POWERBROADCAST()|afx_msg UINT [OnPowerBroadcast](../../mfc/reference/cwnd-class.md#onpowerbroadcast)(UINT、UINT) です。|  
|ON_WM_QUERYDRAGICON()|afx_msg HCURSOR [OnQueryDragIcon](../../mfc/reference/cwnd-class.md#onquerydragicon)() ();|  
|ON_WM_QUERYENDSESSION()|afx_msg BOOL[はす](../../mfc/reference/cwnd-class.md#onqueryendsession)() ();|  
|ON_WM_QUERYNEWPALETTE()|afx_msg BOOL [OnQueryNewPalette](../../mfc/reference/cwnd-class.md#onquerynewpalette)() ();|  
|ON_WM_QUERYOPEN()|afx_msg BOOL [OnQueryOpen](../../mfc/reference/cwnd-class.md#onqueryopen)() ();|  
|ON_WM_RBUTTONDBLCLK()|afx_msg void[離し](../../mfc/reference/cwnd-class.md#onrbuttondblclk)(UINT、CPoint) です。|  
|ON_WM_RBUTTONDOWN()|afx_msg void [OnRButtonDown](../../mfc/reference/cwnd-class.md#onrbuttondown)(UINT、CPoint) です。|  
|ON_WM_RBUTTONUP()|afx_msg void [OnRButtonUp](../../mfc/reference/cwnd-class.md#onrbuttonup)(UINT、CPoint) です。|  
|ON_WM_RENDERALLFORMATS()|afx_msg void [OnRenderAllFormats](../../mfc/reference/cwnd-class.md#onrenderallformats)();|  
|ON_WM_RENDERFORMAT()|afx_msg void [OnRenderFormat](../../mfc/reference/cwnd-class.md#onrenderformat)(UINT) です。|  
  
## <a name="see-also"></a>関連項目  
 [メッセージ マップ](../../mfc/reference/message-maps-mfc.md)   
 [Wm _ で始まるメッセージのハンドラー](../../mfc/reference/handlers-for-wm-messages.md)


