---
title: "CTabView クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTabView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabView クラス"
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 34
---
# CTabView クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CTabView` クラスは、MFC のドキュメント\/ビュー アーキテクチャを使用するアプリケーションでタブ コントロール クラス \([CMFCTabCtrl](../../mfc/reference/ctabview-class.md)\) を簡単に使用できるようにします。  
  
## 構文  
  
```  
class CTabbedView : public CView  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CTabView::AddView](../Topic/CTabView::AddView.md)|タブ コントロールに新しいビューを追加します。|  
|[CTabView::FindTab](../Topic/CTabView::FindTab.md)|タブ コントロール内の指定したビューのインデックスを返します。|  
|[CTabView::GetActiveView](../Topic/CTabView::GetActiveView.md)|現在アクティブなビューへのポインターを返します。|  
|[CTabView::GetTabControl](../Topic/CTabView::GetTabControl.md)|ビューに関連付けられたタブ コントロールへの参照を返します。|  
|[CTabView::RemoveView](../Topic/CTabView::RemoveView.md)|タブ コントロールからビューを削除します。|  
|[CTabView::SetActiveView](../Topic/CTabView::SetActiveView.md)|ビューをアクティブにします。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CTabView::IsScrollBar](../Topic/CTabView::IsScrollBar.md)|タブ ビューを作成するときに、タブ ビューに共有の水平スクロール バーを付けるかどうかを決定するためにフレームワークによって呼び出されます。|  
|[CTabView::OnActivateView](../Topic/CTabView::OnActivateView.md)|タブ ビューがアクティブまたは非アクティブになるときに、フレームワークによって呼び出されます。|  
  
## 解説  
 このクラスを使用すると、ドキュメント\/ビュー アプリケーションにタブ付きのビューを簡単に追加できます。  `CTabView` は、埋め込みの `CMFCTabCtrl` オブジェクトが含まれる `CView` 派生クラスです。  `CTabView` は、`CMFCTabCtrl` オブジェクトをサポートするために必要なすべてのメッセージを処理します。  `CTabView` からクラスを派生し、アプリケーションに組み込んだら、`AddView` メソッドを使用して、その `CView` 派生クラスを追加します。  タブ コントロールによって、それらのビューがタブとして表示されます。  
  
 たとえば、スプレッドシート、グラフ、編集可能なフォームなど、さまざまな形式で表現できるドキュメントがあるとします。  この場合、データを描画する個々のビューを必要に応じて作成し、`CTabView` 派生オブジェクトに挿入すると、追加のコーディングを必要とせずに、それぞれをタブとして表示できます。  
  
 [TabbedView サンプル: MFC タブ付きビュー アプリケーション](../../top/visual-cpp-samples.md) は `CTabView`の使用例を示しています。  
  
## 使用例  
 TabbedView サンプルで `CTabView` を使用する方法を次の例に示します。  
  
 [!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/CPP/ctabview-class_1.h)]  
  
## 必要条件  
 **ヘッダー :** afxTabView.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CTabView クラス](../../mfc/reference/ctabview-class.md)   
 [CView クラス](../Topic/CView%20Class.md)