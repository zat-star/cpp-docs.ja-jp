---
title: "COleResizeBar クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleResizeBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleResizeBar クラス"
  - "コントロール バー, サイズ変更"
  - "埋め込み先アイテム"
  - "埋め込み先アイテム, サイズ変更"
  - "OLE 項目, サイズ変更"
  - "サイズ変更 (埋め込み先 OLE アイテムを)"
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleResizeBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE の埋め込み先アイテムのサイズ変更をサポートするコントロール バーの一種です。  
  
## 構文  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleResizeBar::COleResizeBar](../Topic/COleResizeBar::COleResizeBar.md)|`COleResizeBar` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleResizeBar::Create](../Topic/COleResizeBar::Create.md)|作成し、Windows の子ウィンドウを初期化し、`COleResizeBar` のオブジェクトに関連付けます。|  
  
## 解説  
 `COleResizeBar` のオブジェクトは、ハッチ境界線と外部のサイズ変更ハンドルとの [CRectTracker](../../mfc/reference/crecttracker-class.md) 表示されます。  
  
 `COleResizeBar` のオブジェクトは、通常 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) のクラスから派生したフレーム ウィンドウ オブジェクトの埋め込みメンバーです。  
  
 詳細については、" " [&#91;アクティブ化&#93;](../../mfc/activation-cpp.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## 必要条件  
 **Header:** afxole.h  
  
## 参照  
 [MFC SUPERPAD サンプル](../../top/visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleServerDoc クラス](../Topic/COleServerDoc%20Class.md)