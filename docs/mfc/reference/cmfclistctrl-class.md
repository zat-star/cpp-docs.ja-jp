---
title: "CMFCListCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCListCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCListCtrl クラス"
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CMFCListCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCListCtrl` クラスは、[CMFCHeaderCtrl クラス](../Topic/CMFCHeaderCtrl%20Class.md)の高度なヘッダー コントロール機能をサポートすることで、[CListCtrl クラス](../Topic/CListCtrl%20Class.md) クラスの機能を拡張します。  
  
## 構文  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCListCtrl::EnableMarkSortedColumn](../Topic/CMFCListCtrl::EnableMarkSortedColumn.md)|並べ替えられた列を別の背景色でマークする機能を有効にします。|  
|[CMFCListCtrl::EnableMultipleSort](../Topic/CMFCListCtrl::EnableMultipleSort.md)|複数の並べ替えモードを有効にします。|  
|[CMFCListCtrl::GetHeaderCtrl](../Topic/CMFCListCtrl::GetHeaderCtrl.md)|下線付きヘッダー コントロールへの参照を返します。|  
|[CMFCListCtrl::IsMultipleSort](../Topic/CMFCListCtrl::IsMultipleSort.md)|リスト コントロールが複数の並べ替えモードかどうかを確認します。|  
|[CMFCListCtrl::OnCompareItems](../Topic/CMFCListCtrl::OnCompareItems.md)|2 つのリスト コントロール項目を比較する必要があるときに、フレームワークによって呼び出されます。|  
|[CMFCListCtrl::OnGetCellBkColor](../Topic/CMFCListCtrl::OnGetCellBkColor.md)|個々のセルの背景色を確認する必要があるときに、フレームワークによって呼び出されます。|  
|[CMFCListCtrl::OnGetCellFont](../Topic/CMFCListCtrl::OnGetCellFont.md)|描画されるセルのフォントを取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CMFCListCtrl::OnGetCellTextColor](../Topic/CMFCListCtrl::OnGetCellTextColor.md)|個々のセルのテキストの色を確認する必要があるときに、フレームワークによって呼び出されます。|  
|[CMFCListCtrl::RemoveSortColumn](../Topic/CMFCListCtrl::RemoveSortColumn.md)|並べ替え対象の列の一覧から並べ替え対象の列を削除します。|  
|[CMFCListCtrl::SetSortColumn](../Topic/CMFCListCtrl::SetSortColumn.md)|現在の並べ替え列と並べ替え順序を設定します。|  
|[CMFCListCtrl::Sort](../Topic/CMFCListCtrl::Sort.md)|リスト コントロールを並べ替えます。|  
  
## 解説  
 `CMFCListCtrl` は、[CListCtrl クラス](../Topic/CListCtrl%20Class.md) クラスに 2 つの機能を追加します。  1 つ目として、ヘッダーに並べ替え矢印を自動的に描画することにより、列の並べ替えが可能であることを示します。  2 つ目として、複数列でのデータの同時並べ替えをサポートします。  
  
## 使用例  
 `CMFCListCtrl` クラスのさまざまなメソッドの使用方法を次の例に示します。  この例では、リスト コントロールの作成、列の挿入、項目の挿入、項目のテキストの設定、およびリスト コントロールのフォントの設定の各方法を示します。  このコード スニペットは [Visual Studio のデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/reference/codesnippet/CPP/cmfclistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/reference/codesnippet/CPP/cmfclistctrl-class_2.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CListCtrl](../Topic/CListCtrl%20Class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
## 必要条件  
 **ヘッダー :** afxlistctrl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CListCtrl クラス](../Topic/CListCtrl%20Class.md)