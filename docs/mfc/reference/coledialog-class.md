---
title: "COleDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDialog クラス"
  - "ダイアログ ボックス, OLE"
  - "OLE ダイアログ ボックス, 基本クラス"
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# COleDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE のダイアログ ボックスに共通の機能が用意されています。  
  
## 構文  
  
```  
class COleDialog : public CCommonDialog  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleDialog::GetLastError](../Topic/COleDialog::GetLastError.md)|エラー コードをダイアログ ボックスから返される取得します。|  
  
## 解説  
 Microsoft Foundation Class ライブラリには `COleDialog`から派生する複数のクラスが用意されています:  
  
-   [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)  
  
-   [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)  
  
-   [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)  
  
-   [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
-   [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)  
  
-   [COleUpdateDialog](../Topic/COleUpdateDialog%20Class.md)  
  
-   [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)  
  
-   [COlePropertiesDialog](../Topic/COlePropertiesDialog%20Class.md)  
  
-   [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)  
  
 OLE 固有のダイアログ ボックスの詳細については、" " [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 `COleDialog`  
  
## 必要条件  
 **Header:** afxodlgs.h  
  
## 参照  
 [CCommonDialog クラス](../Topic/CCommonDialog%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)