---
title: "リスト コントロールとリスト ビュー | Microsoft Docs"
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
  - "CListCtrl クラス, および CListView"
  - "CListView クラス, および CListCtrl"
  - "リスト コントロール, リスト ビュー"
  - "リスト ビュー"
  - "ビュー, リストとリスト コントロール"
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# リスト コントロールとリスト ビュー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

便宜上、MFC は 2 とおりの方法でリスト コントロールをカプセル化します。  リスト コントロールを使用する場合:  
  
-   直接、ダイアログ クラスで [CListCtrl](../Topic/CListCtrl%20Class.md) オブジェクトを埋め込むことによって。  
  
-   間接的に、[CListView](../mfc/reference/clistview-class.md)クラスを使用します。  
  
 `CListView` は [CEditView](../Topic/CEditView%20Class.md) がエディット コントロールにカプセル化するようにコントロールをカプセル化する MFC のドキュメント\/ビュー アーキテクチャを持つリスト コントロールの統合を簡単に多くします: コントロールは、MFC ビューの領域を塗りつぶします。\(ビューは、コントロール `CListView`へキャスト *です*\)。  
  
 `CListView` オブジェクトは [CCtrlView](../mfc/reference/cctrlview-class.md) と基本クラスから継承し、基になるリストのコントロールを取得するためのメンバー関数を追加します。  ビューとしてビューを使用するためにビューのメンバーを使用します。  リスト コントロールのメンバー関数へのアクセスを取得するために [GetListCtrl](../Topic/CListView::GetListCtrl.md) メンバー関数を使用します。  これらのメンバーを使用する:  
  
-   リストの「Item」を追加、削除、または処理します。  
  
-   定数またはリスト コントロールの属性を取得します。  
  
 `CListView`の下にある `CListCtrl` への参照を取得するには、リスト ビュー クラスの `GetListCtrl` を呼び出します。:  
  
 [!CODE [NVC_MFCListView#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCListView#4)]  
  
 このトピックでは、リスト コントロールを使用する二つの方法について説明します。  
  
## 参照  
 [CListCtrl の使い方](../Topic/Using%20CListCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)