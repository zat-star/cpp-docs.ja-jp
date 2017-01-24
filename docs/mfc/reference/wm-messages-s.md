---
title: "WM_ で始まるメッセージのハンドラー : S | Microsoft Docs"
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
  - "ON_WM_SYSDEADCHAR"
  - "ON_WM_SYSKEYDOWN"
  - "ON_WM_STYLECHANGING"
  - "ON_WM_STYLECHANGED"
  - "ON_WM_SPOOLERSTATUS"
  - "ON_WM_SYSCHAR"
  - "ON_WM_SETFOCUS"
  - "ON_WM_SIZE"
  - "ON_WM_SIZING"
  - "ON_WM_SETCURSOR"
  - "ON_WM_SYSCOMMAND"
  - "ON_WM_SETTINGCHANGE"
  - "ON_WM_SHOWWINDOW"
  - "ON_WM_SYSKEYUP"
  - "ON_WM_SIZECLIPBOARD"
  - "ON_WM_SYSCOLORCHANGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_SETCURSOR"
  - "ON_WM_SETFOCUS"
  - "ON_WM_SETTINGCHANGE"
  - "ON_WM_SHOWWINDOW"
  - "ON_WM_SIZE"
  - "ON_WM_SIZECLIPBOARD"
  - "ON_WM_SIZING"
  - "ON_WM_SPOOLERSTATUS"
  - "ON_WM_STYLECHANGED"
  - "ON_WM_STYLECHANGING"
  - "ON_WM_SYSCHAR"
  - "ON_WM_SYSCOLORCHANGE"
  - "ON_WM_SYSCOMMAND"
  - "ON_WM_SYSDEADCHAR"
  - "ON_WM_SYSKEYDOWN"
  - "ON_WM_SYSKEYUP"
  - "WM_ メッセージ"
ms.assetid: 4b9aec79-a98f-4aa0-a3d9-110941b6dcbc
caps.latest.revision: 14
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WM_ で始まるメッセージのハンドラー : S
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次のマップ エントリは、関数プロトタイプに対応します。  
  
|マップ エントリ|関数プロトタイプ|  
|--------------|--------------|  
|ON\_WM\_SETCURSOR \(\)|afx\_msg BOOL [OnSetCursor 関数](../Topic/CWnd::OnSetCursor.md) \(CWnd\*、UINT、UINT\) ;|  
|ON\_WM\_SETFOCUS \(\)|afx\_msg void な [OnSetFocus](../Topic/CWnd::OnSetFocus.md)CWnd\* \(\) ;|  
|ON\_WM\_SETTINGCHANGE \(\)|afx\_msg void な [OnSettingChange](../Topic/CWnd::OnSettingChange.md) \(UINT の uFlags、常に lpszSection\) ;|  
|ON\_WM\_SHOWWINDOW \(\)|afx\_msg void な [OnShowWindow](../Topic/CWnd::OnShowWindow.md) \(ブール型、UINT\) ;|  
|ON\_WM\_SIZE \(\)|afx\_msg void な [OnSize](../Topic/CWnd::OnSize.md) \(UINT、int、int\) ;|  
|ON\_WM\_SIZECLIPBOARD \(\)|afx\_msg void な [OnSizeClipboard](../Topic/CWnd::OnSizeClipboard.md) \(CWnd\* のハンドル\) ;|  
|ON\_WM\_SIZING \(\)|afx\_msg void な [OnSizing](../Topic/CWnd::OnSizing.md) \(UINT、LPRECT\) ;|  
|ON\_WM\_SPOOLERSTATUS \(\)|afx\_msg void な [OnSpoolerStatus](../Topic/CWnd::OnSpoolerStatus.md) \(UINT、UINT\) ;|  
|ON\_WM\_STYLECHANGED \(\)|afx\_msg void な [OnStyleChanged](../Topic/CWnd::OnStyleChanged.md) \(int、LPSTYLESTRUCT\) ;|  
|ON\_WM\_STYLECHANGING \(\)|afx\_msg void な [OnStyleChanging](../Topic/CWnd::OnStyleChanging.md) \(int、LPSTYLESTRUCT\) ;|  
|ON\_WM\_SYSCHAR \(\)|afx\_msg void な [OnSysChar](../Topic/CWnd::OnSysChar.md) \(UINT、UINT、UINT\) ;|  
|ON\_WM\_SYSCOLORCHANGE \(\)|afx\_msg void な [OnSysColorChange](../Topic/CWnd::OnSysColorChange.md) \(\) ;|  
|ON\_WM\_SYSCOMMAND \(\)|afx\_msg void な [OnSysCommand](../Topic/CWnd::OnSysCommand.md) \(UINT、LONG な\) ;|  
|ON\_WM\_SYSDEADCHAR \(\)|afx\_msg void な [OnSysDeadChar](../Topic/CWnd::OnSysDeadChar.md) \(UINT、UINT、UINT\) ;|  
|ON\_WM\_SYSKEYDOWN \(\)|afx\_msg void な [OnSysKeyDown](../Topic/CWnd::OnSysKeyDown.md) \(UINT、UINT、UINT\) ;|  
|ON\_WM\_SYSKEYUP \(\)|afx\_msg void な [OnSysKeyUp](../Topic/CWnd::OnSysKeyUp.md) \(UINT、UINT、UINT\) ;|  
  
## 参照  
 [メッセージ マップ](../../mfc/reference/message-maps-mfc.md)   
 [WM\_ で始まるメッセージのハンドラー](../../mfc/reference/handlers-for-wm-messages.md)