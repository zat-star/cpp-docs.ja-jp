---
title: "CMFCDesktopAlertDialog クラス | Microsoft Docs"
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
  - "CMFCDesktopAlertDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertDialog クラス"
ms.assetid: a53c60aa-9607-485b-b826-ec64962075f6
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDesktopAlertDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCDesktopAlertDialog` クラスは、ポップアップ ウィンドウにカスタム ダイアログを表示するため、[CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)と共に使用されます。  
  
## 構文  
  
```  
class CMFCDesktopAlertDialog : public CDialogEx  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCDesktopAlertDialog::CreateFromParams](../Topic/CMFCDesktopAlertDialog::CreateFromParams.md)||  
|[CMFCDesktopAlertDialog::GetDlgSize](../Topic/CMFCDesktopAlertDialog::GetDlgSize.md)||  
|[CMFCDesktopAlertDialog::HasFocus](../Topic/CMFCDesktopAlertDialog::HasFocus.md)||  
|[CMFCDesktopAlertDialog::PreTranslateMessage](../Topic/CMFCDesktopAlertDialog::PreTranslateMessage.md)|\(`CDialogEx::PreTranslateMessage` をオーバーライドします\)。|  
  
### コメント  
 次の手順を実行し、ポップアップ ウィンドウにカスタム ダイアログを表示します。  
  
1.  `CMFCDesktopAlertDialog` の派生クラスを作成します。  
  
2.  プロジェクトのリソースに、子のダイアログ テンプレートを作成します。  
  
3.  ダイアログ テンプレートのリソース ID と派生クラスのランタイム クラス情報へのポインターをパラメーターとして使用し、[CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) を呼び出します。  
  
4.  ホストされるコントロールからのすべての通知を処理するようにカスタム ダイアログをプログラミングするか、これらの通知を直接処理するようにホストされるコントロールをプログラミングします。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)  
  
## 必要条件  
 **ヘッダー:** afxDesktopAlertDialog.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWndInfo クラス](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CDialogEx クラス](../../mfc/reference/cdialogex-class.md)