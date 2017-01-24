---
title: "COlePropertyPage クラス | Microsoft Docs"
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
  - "COlePropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COlePropertyPage クラス"
  - "カスタム コントロール [MFC], プロパティ"
  - "表示 (プロパティを)"
  - "OLE プロパティ ページ"
  - "プロパティ [C++], 表示"
  - "プロパティ ページ, OLE"
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COlePropertyPage クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ダイアログ ボックスのようなグラフィカルなインターフェイスでカスタム コントロールのプロパティを表示します。  
  
## 構文  
  
```  
class AFX_NOVTABLE COlePropertyPage : public CDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COlePropertyPage::COlePropertyPage](../Topic/COlePropertyPage::COlePropertyPage.md)|`COlePropertyPage` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COlePropertyPage::GetControlStatus](../Topic/COlePropertyPage::GetControlStatus.md)|ユーザーが変更したかどうかを示します。|  
|[COlePropertyPage::GetObjectArray](../Topic/COlePropertyPage::GetObjectArray.md)|プロパティ ページで編集されたオブジェクトの配列を返します。|  
|[COlePropertyPage::GetPageSite](../Topic/COlePropertyPage::GetPageSite.md)|プロパティ ページの `IPropertyPageSite` のインターフェイスへのポインターを返します。|  
|[COlePropertyPage::IgnoreApply](../Topic/COlePropertyPage::IgnoreApply.md)|どのコントロールが適用のボタンを有効にしないかを判定します。|  
|[COlePropertyPage::IsModified](../Topic/COlePropertyPage::IsModified.md)|ユーザーがプロパティ ページを変更したかどうかを示します。|  
|[COlePropertyPage::OnEditProperty](../Topic/COlePropertyPage::OnEditProperty.md)|ユーザーがプロパティを編集するときに、フレームワークによって呼び出されます。|  
|[COlePropertyPage::OnHelp](../Topic/COlePropertyPage::OnHelp.md)|ユーザーがヘルプを起動するときに、フレームワークによって呼び出されます。|  
|[COlePropertyPage::OnInitDialog](../Topic/COlePropertyPage::OnInitDialog.md)|プロパティ ページが初期化されるときに、フレームワークによって呼び出されます。|  
|[COlePropertyPage::OnObjectsChanged](../Topic/COlePropertyPage::OnObjectsChanged.md)|別の OLE コントロールが、新しいプロパティと、選択されたときに、フレームワークによって呼び出されます。|  
|[COlePropertyPage::OnSetPageSite](../Topic/COlePropertyPage::OnSetPageSite.md)|プロパティ フレームがページのサイトを提供するときに、フレームワークによって呼び出されます。|  
|[COlePropertyPage::SetControlStatus](../Topic/COlePropertyPage::SetControlStatus.md)|ユーザーが変更したかどうかを示すフラグを設定します。|  
|[COlePropertyPage::SetDialogResource](../Topic/COlePropertyPage::SetDialogResource.md)|プロパティ ページのダイアログ リソースを設定します。|  
|[COlePropertyPage::SetHelpInfo](../Topic/COlePropertyPage::SetHelpInfo.md)|ヘルプ ファイルのプロパティ ページの短い名前、ヘルプ テキスト、およびヘルプ コンテキストを設定します。|  
|[COlePropertyPage::SetModifiedFlag](../Topic/COlePropertyPage::SetModifiedFlag.md)|ユーザーがプロパティ ページを変更したかどうかを示すフラグを設定します。|  
|[COlePropertyPage::SetPageName](../Topic/COlePropertyPage::SetPageName.md)|プロパティ ページの名前 \(キャプション\) を設定します。|  
  
## 解説  
 たとえば、プロパティ ページは、ユーザーがコントロールのキャプションのプロパティを表示および変更できるようにする編集コントロールが含まれる場合があります。  
  
 各カスタム リソースまたは在庫のプロパティは、コントロールでユーザーが現在のプロパティの値を表示し、必要に応じてその値を変更できるダイアログのコントロールがあることができます。  
  
 `COlePropertyPage`の使用の詳細については、" " [ActiveX コントロール: &#91;プロパティ ページ&#93;](../../mfc/mfc-activex-controls-property-pages.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `COlePropertyPage`  
  
## 必要条件  
 **Header:** afxctl.h  
  
## 参照  
 [MFC のサンプル CIRC3](../../top/visual-cpp-samples.md)   
 [MFC の TESTHELP サンプル](../../top/visual-cpp-samples.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)