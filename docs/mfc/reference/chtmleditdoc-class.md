---
title: "CHtmlEditDoc クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHtmlEditDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditDoc クラス"
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CHtmlEditDoc クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CHtmlEditView](../../mfc/reference/chtmleditview-class.md)ともに、MFC のドキュメント ビュー アーキテクチャのコンテキストで WebBrowser 編集プラットフォームの機能を提供します。  
  
## 構文  
  
```  
class AFX_NOVTABLE CHtmlEditDoc : public CDocument  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CHtmlEditDoc::CHtmlEditDoc](../Topic/CHtmlEditDoc::CHtmlEditDoc.md)|`CHtmlEditDoc` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CHtmlEditDoc::GetView](../Topic/CHtmlEditDoc::GetView.md)|このアタッチされているドキュメントへの `CHtmlEditView` のオブジェクトを取得します。|  
|[CHtmlEditDoc::IsModified](../Topic/CHtmlEditDoc::IsModified.md)|関連ビューで WebBrowser コントロールがユーザーによって変更されたドキュメントが含まれているかどうかを返します。|  
|[CHtmlEditDoc::OpenURL](../Topic/CHtmlEditDoc::OpenURL.md)|URL を開きます。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocument](../Topic/CDocument%20Class.md)  
  
 `CHtmlEditDoc`  
  
## 必要条件  
 **ヘッダー:** afxhtml.h  
  
## 参照  
 [HTMLEdit サンプル](../../top/visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)