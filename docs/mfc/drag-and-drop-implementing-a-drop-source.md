---
title: "ドラッグ アンド ドロップ : ドロップ ソースの実装 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ドラッグ アンド ドロップ, 呼び出し (DoDragDrop を)"
  - "ドラッグ アンド ドロップ, ドロップ ソース"
  - "ドラッグ アンド ドロップ, 開始 (ドラッグ操作を)"
  - "OLE のドラッグ アンド ドロップ, 呼び出し (DoDragDrop を)"
  - "OLE のドラッグ アンド ドロップ, ドロップ ソース"
  - "OLE のドラッグ アンド ドロップ, 開始 (ドラッグ操作を)"
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ドラッグ アンド ドロップ : ドロップ ソースの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ドラッグ アンド ドロップ操作にデータを提供するためにアプリケーションを取得する方法について説明します。  
  
 ドラッグ ソースの基本実装は比較的簡単です。  最初の手順は、イベントがドラッグ操作を開始する位置を決定します。  推奨されるユーザー インターフェイスのガイドラインでは、データの選択とドラッグ操作と選択したデータ内の位置で一致する `WM_LBUTTONDOWN` イベントの先頭を定義します。  MFC の OLE サンプル [OCLIENT](../top/visual-cpp-samples.md) と [HIERSVR](../top/visual-cpp-samples.md) は、以下のガイドラインに従います。  
  
 アプリケーションがコンテナーで、選択したデータ型が `COleClientItem`のリンクされたや埋め込みオブジェクト、`DoDragDrop` メンバー関数を呼び出します。  それ以外の場合は `COleDataSource` オブジェクトを構築し、選択を初期化し、データ ソース オブジェクトの `DoDragDrop` メンバー関数を呼び出します。  アプリケーションは、サーバー `COleServerItem::DoDragDrop`を使用します。  標準ドラッグ アンド ドロップの動作をカスタマイズする方法の詳細については、[ドラッグ アンド ドロップ: カスタマイズ](../Topic/Drag%20and%20Drop:%20Customizing.md)記事を参照してください。  
  
 `DoDragDrop` が `DROPEFFECT_MOVE`が返されると、ソース ドキュメントからソース データを削除します。  `DoDragDrop` から他の戻り値は、ドラッグ ソースには影響しません。  
  
 詳細については、次のトピックを参照してください。  
  
-   [ドロップ ターゲットの実装](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [ドラッグ アンド ドロップのカスタマイズ](../Topic/Drag%20and%20Drop:%20Customizing.md)  
  
-   [作成と破棄の OLE データ オブジェクトとデータ ソース](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [処理の OLE データ オブジェクトとデータ ソース](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## 参照  
 [ドラッグ アンド ドロップ \(OLE\)](../mfc/drag-and-drop-ole.md)   
 [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)   
 [COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md)   
 [CView::OnDragLeave](../Topic/CView::OnDragLeave.md)