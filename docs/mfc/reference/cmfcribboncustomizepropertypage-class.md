---
title: "CMFCRibbonCustomizePropertyPage クラス | Microsoft Docs"
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
  - "GetThisClass"
  - "CMFCRibbonCustomizePropertyPage::CreateObject"
  - "CMFCRibbonCustomizePropertyPage"
  - "CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage"
  - "CMFCRibbonCustomizePropertyPage.GetThisClass"
  - "CMFCRibbonCustomizePropertyPage.CreateObject"
  - "~CMFCRibbonCustomizePropertyPage"
  - "CreateObject"
  - "CMFCRibbonCustomizePropertyPage.~CMFCRibbonCustomizePropertyPage"
  - "CMFCRibbonCustomizePropertyPage::GetThisClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCRibbonCustomizePropertyPage デストラクター"
  - "CMFCRibbonCustomizePropertyPage クラス"
  - "CMFCRibbonCustomizePropertyPage クラス, デストラクター"
  - "CreateObject メソッド"
  - "GetThisClass メソッド"
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonCustomizePropertyPage クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リボン ベースのアプリケーションに **\[カスタマイズ\]** ダイアログ ボックスのカスタム ページを実装します。  
  
## 構文  
  
```  
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](../Topic/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage.md)|`CMFCRibbonCustomizePropertyPage` オブジェクトを構築します。|  
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|デストラクターです。|  
  
### パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](../Topic/CMFCRibbonCustomizePropertyPage::AddCustomCategory.md)|**\[コマンド\]** ボックスにカスタム カテゴリを追加します。|  
|`CMFCRibbonCustomizePropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CMFCRibbonCustomizePropertyPage::OnOK](../Topic/CMFCRibbonCustomizePropertyPage::OnOK.md)|ユーザーが **\[カスタマイズ\]** ダイアログ ボックスで **\[OK\]** をクリックしたときに呼び出されます。|  
  
## 解説  
 **\[ユーザー設定\]** ダイアログ ボックスにカスタム コマンドを追加する場合は、AFX\_WM\_ON\_RIBBON\_CUSTOMIZE メッセージを処理する必要があります。  メッセージ ハンドラーでは、スタックの `CMFCRibbonCustomizePropertyPage` オブジェクトをインスタンス化します。  カスタム コマンドの一覧を作成して、`AddCustomCategory` を呼び出し、**\[カスタマイズ\]** ダイアログ ボックスに新しいページを追加します。  
  
## 使用例  
 `CMFCRibbonCustomizePropertyPage` オブジェクトを構築してカスタム カテゴリを追加する方法を次の例に示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/CPP/cmfcribboncustomizepropertypage-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
 [CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)  
  
## 必要条件  
 **ヘッダー :** afxribboncustomizedialog.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)