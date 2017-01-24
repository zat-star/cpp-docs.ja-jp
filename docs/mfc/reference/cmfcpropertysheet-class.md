---
title: "CMFCPropertySheet クラス | Microsoft Docs"
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
  - "CMFCPropertySheet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertySheet クラス"
  - "CMFCPropertySheet::OnInitDialog メソッド"
  - "CMFCPropertySheet::PreTranslateMessage メソッド"
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
caps.latest.revision: 35
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertySheet クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCPropertySheet` クラスは、各プロパティ ページがページ タブ、ツール バー ボタン、ツリー コントロールのノード、またはリスト項目で示されるプロパティ シートをサポートします。  
  
## 構文  
  
```  
class CMFCPropertySheet : public CPropertySheet  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCPropertySheet::CMFCPropertySheet](../Topic/CMFCPropertySheet::CMFCPropertySheet.md)|`CMFCPropertySheet` オブジェクトを構築します。|  
|`CMFCPropertySheet::~CMFCPropertySheet`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCPropertySheet::AddPage](../Topic/CMFCPropertySheet::AddPage.md)|プロパティ シートにページを追加します。|  
|[CMFCPropertySheet::AddPageToTree](../Topic/CMFCPropertySheet::AddPageToTree.md)|ツリー コントロールに新しいプロパティ ページを追加します。|  
|[CMFCPropertySheet::AddTreeCategory](../Topic/CMFCPropertySheet::AddTreeCategory.md)|ツリー コントロールに新しいノードを追加します。|  
|[CMFCPropertySheet::EnablePageHeader](../Topic/CMFCPropertySheet::EnablePageHeader.md)|カスタム ヘッダーを描画する領域を各ページの上部に確保します。|  
|[CMFCPropertySheet::GetHeaderHeight](../Topic/CMFCPropertySheet::GetHeaderHeight.md)|現在のヘッダーの高さを取得します。|  
|[CMFCPropertySheet::GetLook](../Topic/CMFCPropertySheet::GetLook.md)|現在のプロパティ シートの外観を指定する列挙値を取得します。|  
|[CMFCPropertySheet::GetNavBarWidth](../Topic/CMFCPropertySheet::GetNavBarWidth.md)|ナビゲーション バーの幅をピクセル単位で取得します。|  
|[CMFCPropertySheet::GetTab](../Topic/CMFCPropertySheet::GetTab.md)|現在のプロパティ シート コントロールをサポートする内部タブ コントロール オブジェクトを取得します。|  
|`CMFCPropertySheet::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するためにフレームワークで使用されます。|  
|[CMFCPropertySheet::InitNavigationControl](../Topic/CMFCPropertySheet::InitNavigationControl.md)|現在のプロパティ シート コントロールの外観を初期化します。|  
|[CMFCPropertySheet::OnActivatePage](../Topic/CMFCPropertySheet::OnActivatePage.md)|プロパティ ページが有効になったときにフレームワークによって呼び出されます。|  
|[CMFCPropertySheet::OnDrawPageHeader](../Topic/CMFCPropertySheet::OnDrawPageHeader.md)|カスタム プロパティ ページのヘッダーを描画するためにフレームワークによって呼び出されます。|  
|`CMFCPropertySheet::OnInitDialog`|[WM\_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) メッセージを処理します   \([CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md) をオーバーライドします\)。|  
|[CMFCPropertySheet::OnRemoveTreePage](../Topic/CMFCPropertySheet::OnRemoveTreePage.md)|ツリー コントロールからプロパティ ページを削除するためにフレームワークによって呼び出されます。|  
|`CMFCPropertySheet::PreTranslateMessage`|[TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) と [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) の各 Windows 関数にディスパッチされる前にウィンドウ メッセージを変換します。  \(`CPropertySheet::PreTranslateMessage` をオーバーライドします\)。|  
|[CMFCPropertySheet::RemoveCategory](../Topic/CMFCPropertySheet::RemoveCategory.md)|ツリー コントロールからノードを削除します。|  
|[CMFCPropertySheet::RemovePage](../Topic/CMFCPropertySheet::RemovePage.md)|プロパティ シートからプロパティ ページを削除します。|  
|[CMFCPropertySheet::SetIconsList](../Topic/CMFCPropertySheet::SetIconsList.md)|Outlook ウィンドウのナビゲーション コントロールで使用されるイメージの一覧を指定します。|  
|[CMFCPropertySheet::SetLook](../Topic/CMFCPropertySheet::SetLook.md)|プロパティ シートの外観を指定します。|  
  
## 解説  
 `CMFCPropertySheet` クラスは、プロパティ シート \(タブ ダイアログ ボックスとも呼ばれます\) を表します。  `CMFCPropertySheet` クラスは、さまざまな方法でプロパティ ページを表示できます。  
  
 アプリケーションで `CMFCPropertySheet` クラスを使用するには、次の手順を実行します。  
  
1.  `CMFCPropertySheet` クラスから派生クラスを作成し、名前 \(CMyPropertySheet など\) を付けます。  
  
2.  各プロパティ ページに [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) オブジェクトを構築します。  
  
3.  CMyPropertySheet コンストラクターで [CMFCPropertySheet::SetLook](../Topic/CMFCPropertySheet::SetLook.md) メソッドを呼び出します。  このメソッドのパラメーターで、プロパティ ページの表示方法として、プロパティ シートの上部または左側のタブ、Microsoft OneNote プロパティ シート スタイルのタブ、Microsoft Outlook ツール バー コントロールのボタン、ツリー コントロールのノード、プロパティ シートの左側の項目リストのいずれかを指定します。  
  
4.  Microsoft Outlook ツール バー スタイルのプロパティ シートを作成する場合は、[CMFCPropertySheet::SetIconsList](../Topic/CMFCPropertySheet::SetIconsList.md) メソッドを呼び出して、イメージ リストをプロパティ ページに関連付けます。  
  
5.  プロパティ ページごとに [CMFCPropertySheet::AddPage](../Topic/CMFCPropertySheet::AddPage.md) メソッドを呼び出します。  
  
6.  `CMFCPropertySheet` コントロールを作成し、その `DoModal` メソッドを呼び出します。  
  
## 図  
 次の図は、埋め込みの Microsoft Outlook ツール バー スタイルのプロパティ シートを示しています。  プロパティ シートの左側に Outlook ツール バーが表示されます。  
  
 ![CMFCPropertySheet カラー コントロール](../../mfc/reference/media/cmfcpropertysheet_color.png "cmfcpropertysheet\_color")  
  
 次の図は、[CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)のオブジェクトを含むプロパティ シートを示しています。  このオブジェクトは、標準のコモン コントロール スタイルのプロパティ シートです。  
  
 ![CMFCPropertySheet リストおよびプロパティ コントロール](../../mfc/reference/media/cmfcpropertysheet_list.png "cmfcpropertysheet\_list")  
  
 次の図は、ツリー コントロール スタイルのプロパティ シートを示しています。  
  
 ![プロパティ ツリー](../Image/PropTree.png "PropTree")  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
## 必要条件  
 **ヘッダー:** afxpropertysheet.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCPropertyPage クラス](../../mfc/reference/cmfcpropertypage-class.md)   
 [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)