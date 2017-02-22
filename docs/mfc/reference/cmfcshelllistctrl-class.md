---
title: "CMFCShellListCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCShellListCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCShellListCtrl クラス"
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCShellListCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCShellListCtrl` クラスは、Windows のリスト コントロール機能を提供し、シェル項目の一覧を表示できるように機能します。  
  
## 構文  
  
```  
class CMFCShellListCtrl : public CMFCListCtrl  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCShellListCtrl::DisplayFolder](../Topic/CMFCShellListCtrl::DisplayFolder.md)|指定されたフォルダーに含まれている項目の一覧を表示します。|  
|[CMFCShellListCtrl::DisplayParentFolder](../Topic/CMFCShellListCtrl::DisplayParentFolder.md)|現在表示されているフォルダーの親フォルダーに含まれている項目の一覧を表示します。|  
|[CMFCShellListCtrl::EnableShellContextMenu](../Topic/CMFCShellListCtrl::EnableShellContextMenu.md)|ショートカット メニューを有効または無効にします。|  
|[CMFCShellListCtrl::GetCurrentFolder](../Topic/CMFCShellListCtrl::GetCurrentFolder.md)|現在のフォルダーのパスを取得します。|  
|[CMFCShellListCtrl::GetCurrentFolderName](../Topic/CMFCShellListCtrl::GetCurrentFolderName.md)|現在のフォルダーの名前を取得します。|  
|[CMFCShellListCtrl::GetCurrentItemIdList](../Topic/CMFCShellListCtrl::GetCurrentItemIdList.md)|現在のリスト コントロール項目の PIDL を返します。|  
|[CMFCShellListCtrl::GetCurrentShellFolder](../Topic/CMFCShellListCtrl::GetCurrentShellFolder.md)|現在のシェル フォルダーへのポインターを返します。|  
|[CMFCShellListCtrl::GetItemPath](../Topic/CMFCShellListCtrl::GetItemPath.md)|項目のパスのテキスト表現を返します。|  
|[CMFCShellListCtrl::GetItemTypes](../Topic/CMFCShellListCtrl::GetItemTypes.md)|リスト コントロールによって表示されるシェル項目の種類を返します。|  
|[CMFCShellListCtrl::IsDesktop](../Topic/CMFCShellListCtrl::IsDesktop.md)|現在選択されているフォルダーがデスクトップ フォルダーかどうかを確認します。|  
|[CMFCShellListCtrl::OnCompareItems](../Topic/CMFCShellListCtrl::OnCompareItems.md)|フレームワークは、2 つの項目を比較するときにこのメソッドを呼び出します。  \([CMFCListCtrl::OnCompareItems](../Topic/CMFCListCtrl::OnCompareItems.md) をオーバーライドします。\)|  
|[CMFCShellListCtrl::OnFormatFileDate](../Topic/CMFCShellListCtrl::OnFormatFileDate.md)|フレームワークがリスト コントロールによって表示されるファイルの日付を取得するときに呼び出されます。|  
|[CMFCShellListCtrl::OnFormatFileSize](../Topic/CMFCShellListCtrl::OnFormatFileSize.md)|フレームワークがリスト コントロールのファイル サイズを変換するときに呼び出されます。|  
|[CMFCShellListCtrl::OnGetItemIcon](../Topic/CMFCShellListCtrl::OnGetItemIcon.md)|フレームワークがリスト コントロール項目のアイコンを取得するときに呼び出されます。|  
|[CMFCShellListCtrl::OnGetItemText](../Topic/CMFCShellListCtrl::OnGetItemText.md)|フレームワークがリスト コントロール項目のテキストを変換するときに呼び出されます。|  
|[CMFCShellListCtrl::OnSetColumns](../Topic/CMFCShellListCtrl::OnSetColumns.md)|列の名前を設定するときにフレームワークによって呼び出されます。|  
|[CMFCShellListCtrl::Refresh](../Topic/CMFCShellListCtrl::Refresh.md)|リスト コントロールを更新して再描画します。|  
|[CMFCShellListCtrl::SetItemTypes](../Topic/CMFCShellListCtrl::SetItemTypes.md)|リスト コントロールによって表示される項目の種類を設定します。|  
  
## 解説  
 `CMFCShellListCtrl` クラスは [CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)の機能を拡張して、プログラムで Windows シェル項目を一覧表示できるようにします。  エクスプローラー ウィンドウの一覧表示のような表示形式が使用されます。  
  
 [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) オブジェクトを `CMFCShellListCtrl` オブジェクトと関連付けると、まさにエクスプローラーのようなウィンドウを作成できます。  この状態で `CMFCShellTreeCtrl` の項目を選択すると、`CMFCShellListCtrl` オブジェクトによって選択された項目の内容が一覧表示されます。  
  
## 使用例  
 次の例は、`CMFCShellListCtrl` クラスのオブジェクトを作成する方法、および現在表示されているフォルダーの親フォルダーを表示する方法について説明しています。  このコード スニペットは [Explorer サンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_Explorer#1](../../mfc/reference/codesnippet/CPP/cmfcshelllistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#2](../../mfc/reference/codesnippet/CPP/cmfcshelllistctrl-class_2.cpp)]  
[!code-cpp[NVC_MFC_Explorer#3](../../mfc/reference/codesnippet/CPP/cmfcshelllistctrl-class_3.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CListCtrl](../Topic/CListCtrl%20Class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)  
  
## 必要条件  
 **ヘッダー :** afxshelllistCtrl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)   
 [CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md)