---
title: "CMFCCustomColorsPropertyPage クラス | Microsoft Docs"
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
  - "CMFCCustomColorsPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCustomColorsPropertyPage クラス"
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCCustomColorsPropertyPage クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

色のダイアログ ボックスでカスタム カラーを選択できるプロパティ ページを表します。  
  
## 構文  
  
```  
class CMFCCustomColorsPropertyPage : public CPropertyPage  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|既定のコンストラクターです。|  
  
### パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCCustomColorsPropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|`CMFCCustomColorsPropertyPage::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CMFCCustomColorsPropertyPage::Setup](../Topic/CMFCCustomColorsPropertyPage::Setup.md)|プロパティ ページの色要素を設定します。|  
  
### 解説  
 `CMFCColorDialog` クラスは、カスタム カラーのプロパティ ページを表示するために、このクラスを使用します。  `CMFCColorDialog` の詳細については、「[CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)」を参照してください。  
  
## 使用例  
 `CMFCCustomColorsPropertyPage` オブジェクトを構築し、プロパティ ページの色要素を設定する方法を次の例に示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/CPP/cmfccustomcolorspropertypage-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)  
  
## 必要条件  
 **ヘッダー :** afxcustomcolorspropertypage.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCStandardColorsPropertyPage クラス](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)