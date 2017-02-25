---
title: "CHtmlEditView クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHtmlEditView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditView クラス"
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CHtmlEditView クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC のドキュメント\/ビュー アーキテクチャのコンテキストで WebBrowser 編集プラットフォームの機能を提供します。  
  
## 構文  
  
```  
  
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase< CHtmlEditView >  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CHtmlEditView::CHtmlEditView](../Topic/CHtmlEditView::CHtmlEditView.md)|`CHtmlEditView` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CHtmlEditView::Create](../Topic/CHtmlEditView::Create.md)|新しいウィンドウ オブジェクトを作成します。|  
|[CHtmlEditView::GetDHtmlDocument](../Topic/CHtmlEditView::GetDHtmlDocument.md)|現在のドキュメントの **IHTMLDocument2** のインターフェイスを返します。|  
|[CHtmlEditView::GetStartDocument](../Topic/CHtmlEditView::GetStartDocument.md)|このビューの既定のドキュメント名を取得します。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 [CHtmlEditCtrlBase](../Topic/CHtmlEditCtrlBase%20Class.md)  
  
 [CHtmlView](../../mfc/reference/chtmlview-class.md)  
  
 `CHtmlEditView`  
  
## 必要条件  
 **ヘッダー:** afxhtml.h  
  
## 参照  
 [HTMLEdit サンプル](../../top/visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)