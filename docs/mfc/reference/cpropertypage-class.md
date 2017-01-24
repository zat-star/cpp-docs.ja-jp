---
title: "CPropertyPage クラス | Microsoft Docs"
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
  - "CPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPropertyPage クラス"
  - "ダイアログ ボックス, タブ"
  - "プロパティ ページ, CPropertyPage クラス"
  - "タブ ダイアログ ボックス"
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
caps.latest.revision: 25
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPropertyPage クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

タブ ダイアログ ボックスとして知られているプロパティ シートの各ページを表します。  
  
## 構文  
  
```  
class CPropertyPage : public CDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CPropertyPage::CPropertyPage](../Topic/CPropertyPage::CPropertyPage.md)|`CPropertyPage` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPropertyPage::CancelToClose](../Topic/CPropertyPage::CancelToClose.md)|\[OK\]ボタンを閉じるを読み取るために変更し、モーダル プロパティ シートのページの回復できない変更後の\[キャンセル\]ボタンを無効にします。|  
|[CPropertyPage::Construct](../Topic/CPropertyPage::Construct.md)|`CPropertyPage` オブジェクトを構築します。  実行時に、パラメーターを指定したり、配列を使用する場合は `Construct` を使用します。|  
|[CPropertyPage::GetPSP](../Topic/CPropertyPage::GetPSP.md)|`CPropertyPage` のオブジェクトに関連付けられた Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) の構造体を取得します。|  
|[CPropertyPage::OnApply](../Topic/CPropertyPage::OnApply.md)|を適用して、ボタンがかかるときに、フレームワークによって呼び出されますクリックします。|  
|[CPropertyPage::OnCancel](../Topic/CPropertyPage::OnCancel.md)|\[キャンセル\]ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnKillActive](../Topic/CPropertyPage::OnKillActive.md)|現在のページがアクティブでなくなるページでない場合にフレームワークによって呼び出されます。  データの妥当性検査をここで実行します。|  
|[CPropertyPage::OnOK](../Topic/CPropertyPage::OnOK.md)|\[OK\]が、適用すると、フレームワーク、または閉じるボタンによって呼び出され、をクリックします。|  
|[CPropertyPage::OnQueryCancel](../Topic/CPropertyPage::OnQueryCancel.md)|\[キャンセル\]ボタンがクリックされたときに、フレームワークによって、キャンセルの前に呼び出されます。発生しました。|  
|[CPropertyPage::OnReset](../Topic/CPropertyPage::OnReset.md)|\[キャンセル\]ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md)|ページがアクティブになるときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnWizardBack](../Topic/CPropertyPage::OnWizardBack.md)|ウィザード型のプロパティ シートを使用しているときに\[戻る\]ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnWizardFinish](../Topic/CPropertyPage::OnWizardFinish.md)|ウィザード型のプロパティ シートを使用しているときに、\[完了\]をクリックしたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnWizardNext](../Topic/CPropertyPage::OnWizardNext.md)|ウィザード型のプロパティ シートを使用しているときに、次のボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::QuerySiblings](../Topic/CPropertyPage::QuerySiblings.md)|プロパティ シートの各ページにメッセージを転送します。|  
|[CPropertyPage::SetModified](../Topic/CPropertyPage::SetModified.md)|適用をアクティブ化または非アクティブ化しますが、ボタンがあります。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CPropertyPage::m\_psp](../Topic/CPropertyPage::m_psp.md)|Windows の構造 [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548)。  基本プロパティ ページのパラメーターへのアクセスを提供します。|  
  
## 解説  
 標準のダイアログ ボックスと同じように、プロパティ シートのページごとに `CPropertyPage` からクラスを派生します。  `CPropertyPage` から派生したオブジェクトを使うには、まず [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) オブジェクトを構築します。その後、プロパティ シートに含まれるページごとにオブジェクトを構築します。  プロパティ シートのページごとに [CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md) を呼び出します。その後、モーダル プロパティ シートに対しては [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md) を、モードレス プロパティ シートに対しては [CPropertySheet::Create](../Topic/CPropertySheet::Create.md) を呼び出してプロパティ シートを表示します。  
  
 ウィザードと呼ばれる型のタブ ダイアログ ボックスを作成できます。このダイアログ ボックスは、デバイスのセットアップやニュースレターの作成のような、操作の手順をユーザーに示す一連のプロパティ ページを持つプロパティ シートで構成されています。  ウィザード型のタブ ダイアログ ボックスでは、プロパティ ページにタブがなく、一度に 1 つのプロパティ ページだけが表示されます。  また、ウィザード型のタブ ダイアログ ボックスは、\[OK\] ボタンや \[今すぐ適用\] ボタンの代わりに、\[戻る\]、\[次へ\]、\[完了\]、\[キャンセル\] ボタンを持ちます。  
  
 ウィザードのようなプロパティ シートを作成する方法の詳細については、「[CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md)」を参照してください。  `CPropertyPage` オブジェクトの使い方の詳細については、「[プロパティ シートとプロパティ ページ](../../mfc/property-sheets-and-property-pages-in-mfc.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## 必要条件  
 **ヘッダー:** afxdlgs.h  
  
## 参照  
 [MFC CMNCTRL1 サンプル](../../top/visual-cpp-samples.md)   
 [MFC CMNCTRL2 サンプル](../../top/visual-cpp-samples.md)   
 [MFC PROPDLG サンプル](../../top/visual-cpp-samples.md)   
 [MFC SNAPVW サンプル](../../top/visual-cpp-samples.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)   
 [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md)