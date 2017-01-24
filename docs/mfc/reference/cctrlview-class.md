---
title: "CCtrlView クラス | Microsoft Docs"
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
  - "CCtrlView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCtrlView クラス"
  - "コントロール [MFC], コモン"
  - "ビュー, およびコモン コントロール"
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCtrlView クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 98 および Windows NT Version 3.51 以降がサポートするコモン コントロールにドキュメント\/ビュー アーキテクチャを適合させます。  
  
## 構文  
  
```  
class CCtrlView : public CView  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CCtrlView::CCtrlView](../Topic/CCtrlView::CCtrlView.md)|`CCtrlView` オブジェクトを構築します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CCtrlView::OnDraw](../Topic/CCtrlView::OnDraw.md)|指定されたデバイス コンテキストを使用して描画するために、フレームワークによって呼び出されます。|  
|[CCtrlView::PreCreateWindow](../Topic/CCtrlView::PreCreateWindow.md)|`CCtrlView` オブジェクトに関連付けられている Windows のウィンドウが作成される前に呼び出されます。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CCtrlView::m\_dwDefaultStyle](../Topic/CCtrlView::m_dwDefaultStyle.md)|ビュー クラスの既定のスタイルが含まれます。|  
|[CCtrlView::m\_strClass](../Topic/CCtrlView::m_strClass.md)|ビュー クラスの Windows クラス名が含まれます。|  
  
## 解説  
 `CCtrlView` クラスとその派生クラス、[CEditView](../Topic/CEditView%20Class.md)、[CListView](../../mfc/reference/clistview-class.md)、[CTreeView](../../mfc/reference/ctreeview-class.md)と [CRichEditView](../../mfc/reference/cricheditview-class.md)\/98 は、Windows 95 と Windows NT Version 3.51 以降でサポートされている新しいコモン コントロールに、ドキュメント ビュー アーキテクチャを同期します。  ドキュメント ビュー アーキテクチャの詳細については、[ドキュメント\/ビュー アーキテクチャ](../Topic/Document-View%20Architecture.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 `CCtrlView`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [CView クラス](../Topic/CView%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CTreeView クラス](../../mfc/reference/ctreeview-class.md)   
 [CListView クラス](../../mfc/reference/clistview-class.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)