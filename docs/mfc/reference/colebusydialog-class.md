---
title: "COleBusyDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleBusyDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleBusyDialog クラス"
  - "[サーバーを使用できません] ダイアログ ボックス"
  - "[サーバーが応答しません] ダイアログ ボックス"
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleBusyDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE の \[サーバーが応答しません\] ダイアログ ボックスまたは \[サーバーを使用できません\] ダイアログ ボックスに使用されます。  
  
## 構文  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleBusyDialog::COleBusyDialog](../Topic/COleBusyDialog::COleBusyDialog.md)|`COleBusyDialog` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleBusyDialog::DoModal](../Topic/COleBusyDialog::DoModal.md)|OLE サーバーの\[中のダイアログ ボックスを表示します。|  
|[COleBusyDialog::GetSelectionType](../Topic/COleBusyDialog::GetSelectionType.md)|ダイアログ ボックスで行った選択を決定します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[COleBusyDialog::m\_bz](../Topic/COleBusyDialog::m_bz.md)|ダイアログ ボックスの動作を制御する型の構造 **OLEUIBUSY**。|  
  
## 解説  
 これらのダイアログ ボックスを使用すると `COleBusyDialog` クラスのオブジェクトを作成します。  `COleBusyDialog` オブジェクトの構築後、ダイアログ ボックスのコントロールの値や状態を初期化するために [m\_bz](../Topic/COleBusyDialog::m_bz.md) の構造を使用できます。  `m_bz` の構造は、型 **OLEUIBUSY**です。  このダイアログ クラスの使用方法の詳細については、[DoModal](../Topic/COleBusyDialog::DoModal.md) のメンバー関数に関するトピックを参照してください。  
  
> [!NOTE]
>  アプリケーション ウィザードによって生成されたコンテナー コードは、このクラスを使用します。  
  
 詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) の構造体を参照してください。  
  
 OLE 固有のダイアログ ボックスの詳細については、" " [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleBusyDialog`  
  
## 必要条件  
 **Header:** afxodlgs.h  
  
## 参照  
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)