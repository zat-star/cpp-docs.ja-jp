---
title: "ドキュメント/ビュー アーキテクチャの利点 | Microsoft Docs"
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
  - "ドキュメント/ビュー アーキテクチャ, 利点"
  - "ビュー, 利点"
ms.assetid: 0bc27071-e120-4889-939c-ce1e61fb9cb3
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ドキュメント/ビュー アーキテクチャの利点
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC のドキュメント\/ビュー アーキテクチャを使用する主な利点は、アーキテクチャが同じドキュメントの複数のビューを特別にサポートします。複数のビューを必要とせず、ドキュメント\/ビュー アプリケーションに追加のオーバーヘッドが小さい場合、アーキテクチャを回避できます。  [ドキュメント\/ビュー アーキテクチャの代替手段](../mfc/alternatives-to-the-document-view-architecture.md)\)。  
  
 アプリケーションがスプレッドシートのフォームまたはフォームのユーザーのグラフ ビューの数値データを有効にするとします。  ユーザーは、データの結果生データ、スプレッドシートのフォームで、グラフを同時に参照したい場合があります。  別のフレーム ウィンドウまたは一つのウィンドウ内のペインの別のビューを表示します。  これにより、ユーザーがスプレッドシートのデータを編集し、すぐに反映されるグラフの変更を参照するとします。  
  
 MFC では、スプレッドシートのビューとグラフ ビューには、CView から派生された別のクラスに基づいています。  ビューは、どちらもシングル ドキュメント オブジェクトに関連付けられます。  ドキュメントにデータ \(場合によってはデータベースからレコードを取得します。  ビューは、ドキュメントにアクセスし、そのオブジェクトから取得するデータを表示します。  
  
 ユーザーがビューの 1 を更新すると、ビュー オブジェクトの呼び出し `CDocument::UpdateAllViews`。  この関数はドキュメントの最新のデータを使用してドキュメントのビューはすべて、および各ビューの更新自体を通知します。  `UpdateAllViews` への単一の呼び出しは異なるビューを同期します。  
  
 このシナリオでは、ビューは、データを格納する場合は、ビューのデータを分離せずにコードが困難です。  ドキュメント\/ビューで、これは簡単です。  フレームワークによってはほとんどの作業します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [別のビュー文書化します。](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [CDocument](../Topic/CDocument%20Class.md)  
  
-   [CView](../Topic/CView%20Class.md)  
  
-   [CDocument::UpdateAllViews](../Topic/CDocument::UpdateAllViews.md)  
  
-   [CView::GetDocument](../Topic/CView::GetDocument.md)  
  
## 参照  
 [ドキュメント\/ビュー アーキテクチャ](../Topic/Document-View%20Architecture.md)