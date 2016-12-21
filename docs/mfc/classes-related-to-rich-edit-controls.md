---
title: "リッチ エディット コントロールに関連するクラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス [C++], 関連する (リッチ エディット コントロールに)"
  - "CRichEditCtrl クラス, 関連クラス"
  - "CRichEditCtrlItem クラスおよび CRichEditCtrl"
  - "CRichEditDoc クラス, リッチ エディット コントロール"
  - "CRichEditView クラス, および CRichEditCtrl"
  - "リッチ エディット コントロール, および CRichEditDoc"
  - "リッチ エディット コントロール, および CRichEditItem"
  - "リッチ エディット コントロール, および CRichEditView"
  - "リッチ エディット コントロール, クラス (関連する)"
ms.assetid: 4b31c2cc-6ea1-4146-b7c5-b0b5b419f14d
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# リッチ エディット コントロールに関連するクラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CRichEditView](../mfc/reference/cricheditview-class.md)、[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)と [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md) クラスは、MFC のドキュメント\/ビュー アーキテクチャのコンテキストでリッチ エディット コントロール \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\) 機能を提供します。  `CRichEditView` が テキストに特性テキストと書式設定を保持します。  `CRichEditDoc` は ビューの OLE クライアント項目のリストを保持します。  `CRichEditCntrItem` は OLE クライアント項目コンテナー側へのアクセスを提供します。  `CRichEditView`の内容を変更するには、基になるリッチ エディット コントロールにアクセスするに [CRichEditView::GetRichEditCtrl](../Topic/CRichEditView::GetRichEditCtrl.md) を使用します。  
  
## 参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)