---
title: "CMFCShellTreeCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCShellTreeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCShellTreeCtrl クラス"
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCShellTreeCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCShellTreeCtrl` クラスは、シェル項目の階層を表示するように [CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md)の機能を拡張します。  
  
## 構文  
  
```  
class CMFCShellTreeCtrl : public CTreeCtrl  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCShellTreeCtrl::EnableShellContextMenu](../Topic/CMFCShellTreeCtrl::EnableShellContextMenu.md)|ショートカット メニューを有効または無効にします。|  
|[CMFCShellTreeCtrl::GetFlags](../Topic/CMFCShellTreeCtrl::GetFlags.md)|[IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066) に渡されたフラグの組み合わせを返します。|  
|[CMFCShellTreeCtrl::GetItemPath](../Topic/CMFCShellTreeCtrl::GetItemPath.md)|項目のパスを取得します。|  
|[CMFCShellTreeCtrl::GetRelatedList](../Topic/CMFCShellTreeCtrl::GetRelatedList.md)|エクスプローラーのようなウィンドウを作成するために、この `CMFCShellTreeCtrl` オブジェクトと共に使用される [CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md) オブジェクトへのポインターを返します。|  
|[CMFCShellTreeCtrl::OnChildNotify](../Topic/CMFCShellTreeCtrl::OnChildNotify.md)|このウィンドウで処理する必要のある通知メッセージを親ウィンドウが受け取ったときに、親ウィンドウによって呼び出されます   \([CWnd::OnChildNotify](../Topic/CWnd::OnChildNotify.md) をオーバーライドします\)。|  
|[CMFCShellTreeCtrl::OnGetItemIcon](../Topic/CMFCShellTreeCtrl::OnGetItemIcon.md)||  
|[CMFCShellTreeCtrl::OnGetItemText](../Topic/CMFCShellTreeCtrl::OnGetItemText.md)||  
|[CMFCShellTreeCtrl::Refresh](../Topic/CMFCShellTreeCtrl::Refresh.md)|現在の `CMFCShellTreeCtrl` オブジェクトを更新して再描画します。|  
|[CMFCShellTreeCtrl::SelectPath](../Topic/CMFCShellTreeCtrl::SelectPath.md)|指定された PIDL または文字列パスに基づく適切なツリー コントロール項目を選択します。|  
|[CMFCShellTreeCtrl::SetFlags](../Topic/CMFCShellTreeCtrl::SetFlags.md)|ツリー コンテキストをフィルター処理するフラグを設定します \(`IShellFolder::EnumObjects` により使用されるフラグに似ています\)。|  
|[CMFCShellTreeCtrl::SetRelatedList](../Topic/CMFCShellTreeCtrl::SetRelatedList.md)|現在の `CMFCShellTreeCtrl` オブジェクトと `CMFCShellListCtrl` オブジェクトの間の関係を設定します。|  
  
## 解説  
 このクラスは、プログラムのツリーに Windows シェル項目を追加できるようにすることにより、`CTreeCtrl` クラスを拡張します。  このクラスを `CMFCShellListCtrl` オブジェクトと関連付けることで、まさにエクスプローラーのようなウィンドウを作成できます。  この状態でツリーの項目を選択すると、関連付けられた一覧に Windows シェル項目の一覧が表示されます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CTreeCtrl](../../mfc/reference/ctreectrl-class.md)  
  
 [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)  
  
## 必要条件  
 **ヘッダー :** afxshelltreeCtrl.h  
  
## 使用例  
 次の例は、`CMFCShellTreeCtrl` クラスのオブジェクトを作成する方法を説明しています。  このコード スニペットは [Explorer サンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/CPP/cmfcshelltreectrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/CPP/cmfcshelltreectrl-class_2.cpp)]  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md)   
 [CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)