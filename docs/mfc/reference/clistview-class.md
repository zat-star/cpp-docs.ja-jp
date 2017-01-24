---
title: "CListView クラス | Microsoft Docs"
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
  - "CListView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListView クラス"
  - "ビュー, およびコモン コントロール"
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CListView クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リスト コントロールと [CListCtrl](../Topic/CListCtrl%20Class.md)のリスト コントロールの機能をカプセル化する MFC のドキュメント ビュー アーキテクチャを使用するクラスの使用を単純化します。  
  
## 構文  
  
```  
class CListView : public CCtrlView  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CListView::CListView](../Topic/CListView::CListView.md)|`CListView` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CListView::GetListCtrl](../Topic/CListView::GetListCtrl.md)|ビューに関連付けられたコントロールの一覧を返します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CListView::RemoveImageList](../Topic/CListView::RemoveImageList.md)|リスト ビューの指定されたイメージ リストを削除します。|  
  
## 解説  
 このアーキテクチャの詳細には、そこで引用された [&#91;CW2CT&#93;](../Topic/CView%20Class.md) のクラスと相互参照については、" "を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CListView`  
  
## 必要条件  
 **Header:** afxcview.h  
  
## 参照  
 [MFC ROWLIST サンプル](../../top/visual-cpp-samples.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)