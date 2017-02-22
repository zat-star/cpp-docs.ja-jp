---
title: "CMFCRibbonCustomizeDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "GetThisClass"
  - "CMFCRibbonCustomizeDialog"
  - "~CMFCRibbonCustomizeDialog"
  - "CMFCRibbonCustomizeDialog::GetThisClass"
  - "CMFCRibbonCustomizeDialog.~CMFCRibbonCustomizeDialog"
  - "CMFCRibbonCustomizeDialog.GetThisClass"
  - "CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCRibbonCustomizeDialog デストラクター"
  - "CMFCRibbonCustomizeDialog クラス"
  - "CMFCRibbonCustomizeDialog クラス, デストラクター"
  - "GetThisClass メソッド"
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMFCRibbonCustomizeDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リボンの **\[ユーザー設定\]** ページを表示します。  
  
## 構文  
  
```  
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](../Topic/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog.md)|`CMFCRibbonCustomizeDialog` オブジェクトを構築します。|  
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|`CMFCRibbonCustomizeDialog::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
  
## 解説  
 MFC では、AFX\_WM\_ON\_RIBBON\_CUSTOMIZE メッセージを処理しない場合、またはメッセージ ハンドラーから 0 を返す場合に、このクラスが自動的にインスタンス化されます。  
  
 アプリケーションでこのクラスを使用して、リボンの **\[ユーザー設定\]** ダイアログ ボックスを表示する場合は、このクラスをインスタンス化して `DoModal` メソッドを呼び出すだけで表示できます。  
  
 このクラスは [CMFCPropertySheet クラス](../../mfc/reference/cmfcpropertysheet-class.md)から派生するため、`CMFCPropertySheet` API を使用してカスタム ページを追加できます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
 [CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)  
  
## 必要条件  
 **ヘッダー :** afxribboncustomizedialog.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)