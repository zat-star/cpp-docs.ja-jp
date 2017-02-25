---
title: "COleLinksDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleLinksDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleLinksDialog クラス"
  - "ダイアログ ボックス, OLE"
  - "[リンクの編集] ダイアログ ボックス"
  - "OLE の [リンクの編集] ダイアログ ボックス"
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleLinksDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE の \[リンクの編集\] ダイアログ ボックスに使用します。  
  
## 構文  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleLinksDialog::COleLinksDialog](../Topic/COleLinksDialog::COleLinksDialog.md)|`COleLinksDialog` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleLinksDialog::DoModal](../Topic/COleLinksDialog::DoModal.md)|OLE リンクの編集\]ダイアログ ボックスを表示します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[COleLinksDialog::m\_el](../Topic/COleLinksDialog::m_el.md)|ダイアログ ボックスの動作を制御する型の構造 **OLEUIEDITLINKS**。|  
  
## 解説  
 このダイアログ ボックスを使用すると `COleLinksDialog` クラスのオブジェクトを作成します。  `COleLinksDialog` オブジェクトの構築後、ダイアログ ボックスのコントロールの値や状態を初期化するために [m\_el](../Topic/COleLinksDialog::m_el.md) の構造を使用できます。  `m_el` の構造は、型 **OLEUIEDITLINKS**です。  このダイアログ クラスの使用方法の詳細については、[DoModal](../Topic/COleLinksDialog::DoModal.md) のメンバー関数に関するトピックを参照してください。  
  
> [!NOTE]
>  アプリケーション ウィザードによって生成されたコンテナー コードは、このクラスを使用します。  
  
 詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) の構造体を参照してください。  
  
 OLE 固有のダイアログ ボックスに関する詳細については、" " [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleLinksDialog`  
  
## 必要条件  
 **Header:** afxodlgs.h  
  
## 参照  
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)