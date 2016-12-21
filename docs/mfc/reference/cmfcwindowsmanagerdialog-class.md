---
title: "CMFCWindowsManagerDialog クラス | Microsoft Docs"
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
  - "CMFCWindowsManagerDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCWindowsManagerDialog クラス"
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCWindowsManagerDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCWindowsManagerDialog` オブジェクトは、ユーザーが MDI アプリケーションの中で MDI 子ウィンドウを管理できるようにします。  
  
## 構文  
  
```  
class CMFCWindowsManagerDialog : public CDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](../Topic/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog.md)|`CMFCWindowsManagerDialog` オブジェクトを構築します。|  
  
## 解説  
 `CMFCWindowsManagerDialog` には、アプリケーションで現在開かれている MDI 子ウィンドウのリストが含まれています。  ユーザーはこのダイアログ ボックスを使用して、MDI 子ウィンドウの状態を手動で制御できます。  
  
 `CMFCWindowsManagerDialog` は [CMDIFrameWndEx クラス](../Topic/CMDIFrameWndEx%20Class.md)内に埋め込まれています。  `CMFCWindowsManagerDialog` は、手動で作成する必要のないクラスです。  代わりに [CMDIFrameWndEx::ShowWindowsDialog](../Topic/CMDIFrameWndEx::ShowWindowsDialog.md) 関数を呼び出します。これにより、`CMFCWindowsManagerDialog` オブジェクトが作成され、表示されます。  
  
## 使用例  
 `CMDIFrameWndEx::ShowWindowsDialog` を呼び出して `CMFCWindowsManagerDialog` オブジェクトを構築する方法を次の例に示します。  このコード スニペットは [Visual Studio のデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/reference/codesnippet/CPP/cmfcwindowsmanagerdialog-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)  
  
## 必要条件  
 **ヘッダー :** afxWindowsManagerDialog.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMDIFrameWndEx クラス](../Topic/CMDIFrameWndEx%20Class.md)   
 [CMDIFrameWndEx::ShowWindowsDialog](../Topic/CMDIFrameWndEx::ShowWindowsDialog.md)