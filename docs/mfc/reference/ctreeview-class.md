---
title: "CTreeView クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTreeView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeView クラス"
  - "CTreeView クラス, コモン コントロール"
  - "ディレクトリ一覧"
  - "ファイル リスト [C++]"
  - "ツリー ビュー コントロール"
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CTreeView クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ツリー コントロールと [CTreeCtrl](../../mfc/reference/ctreectrl-class.md)のツリー コントロールの機能をカプセル化する MFC のドキュメント ビュー アーキテクチャを使用するクラスの使用を単純化します。  
  
## 構文  
  
```  
class CTreeView : public CCtrlView  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CTreeView::CTreeView](../Topic/CTreeView::CTreeView.md)|`CTreeView` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CTreeView::GetTreeCtrl](../Topic/CTreeView::GetTreeCtrl.md)|ビューに関連付けられているツリー コントロールを返します。|  
  
## 解説  
 このアーキテクチャの詳細には、そこで引用された [&#91;CW2CT&#93;](../Topic/CView%20Class.md) のクラスと相互参照については、" "を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CTreeView`  
  
## 必要条件  
 **Header:** afxcview.h  
  
## 参照  
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CView クラス](../Topic/CView%20Class.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md)