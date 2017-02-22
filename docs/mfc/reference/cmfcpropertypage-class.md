---
title: "CMFCPropertyPage クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyPage クラス"
  - "CMFCPropertyPage::CreateObject メソッド"
  - "CMFCPropertyPage::OnSetActive メソッド"
  - "CMFCPropertyPage::PreTranslateMessage メソッド"
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCPropertyPage クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCPropertyPage` クラスは、プロパティ ページでのポップアップ メニューの表示をサポートします。  
  
## 構文  
  
```  
class CMFCPropertyPage : public CPropertyPage  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCPropertyPage::CMFCPropertyPage](../Topic/CMFCPropertyPage::CMFCPropertyPage.md)|`CMFCPropertyPage` オブジェクトを構築します。|  
|`CMFCPropertyPage::~CMFCPropertyPage`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|`CMFCPropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|`CMFCPropertyPage::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|`CMFCPropertyPage::OnSetActive`|ユーザーがページを選択し、ページがアクティブになったときに、フレームワークが呼び出します。  \([CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md) をオーバーライドします。\)|  
|`CMFCPropertyPage::PreTranslateMessage`|Windows 関数の [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) や [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) にディスパッチする前にウィンドウ メッセージを変換します。  詳細とメソッド構文については、「[CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md)」を参照してください。  \(`CPropertyPage::PreTranslateMessage` をオーバーライドします。\)|  
  
## 解説  
 `CMFCPropertyPage` クラスは、プロパティ シートの各ページを表します。プロパティ シートは、タブ ダイアログ ボックスとも呼ばれます。  
  
 `CMFCPropertyPage` クラスと [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) クラスを併用します。  プロパティ ページのメニューを使用するには、`CPropertyPage` クラスをすべて `CMFCPropertyPage` クラスに置き換えます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
## 必要条件  
 **ヘッダー :** afxpropertypage.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCPropertySheet クラス](../../mfc/reference/cmfcpropertysheet-class.md)