---
title: "ビューの使い方 | Microsoft Docs"
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
  - "CView クラス, ビュー アーキテクチャ"
  - "描画, データ"
  - "ユーザーとの対話とビュー クラスの役割"
  - "MFC, ビュー"
  - "描画 (データを)"
  - "描画 (データを)"
  - "ユーザー入力, 解釈 (ビュー クラスを通じた)"
  - "ビュー クラス, 役割 (アプリケーション データの表示での)"
  - "ビュー クラス, 役割 (ユーザーとの対話の管理での)"
  - "ビュー, 使用"
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ビューの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ビューの責任は、ドキュメント内のデータをユーザーにグラフィカルに表示され、文書のアクションとして、ユーザー入力を受け入れ、解釈します。  ビュー クラスを作成する場合のタスクが存在する:  
  
-   ドキュメントにデータを表示するビュー クラスの [OnDraw](../Topic/CView::OnDraw.md) メンバー関数を記述します。  
  
-   ビュー クラスのメッセージ ハンドラー メンバー関数にメニュー項目の適切な Windows メッセージおよびユーザー インターフェイス オブジェクトを追加します。  
  
-   ユーザー入力を解釈するためにこれらのハンドラーを実装してください。  
  
 また、派生ビュー クラスの `CView` の他のメンバー関数をオーバーライドする必要があります。  特にビューがそれ自体を再描画する直前に、必要な特別な処理をするビューと [OnUpdate](../Topic/CView::OnUpdate.md) の特別な初期化を実行する [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) をオーバーライドすることもできます。  複数ページのドキュメントでは、印刷するページの指定、および数などの情報を含む印刷ダイアログ ボックスを初期化するようにように [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) をオーバーライドする必要があります。  `CView` のメンバー関数をオーバーライドする詳細については、" *MFC リファレンス"の*" [CView](../Topic/CView%20Class.md) クラスを参照します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [MFC で使用できる派生ビュー クラス](../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [ビューで描画できます。](../mfc/drawing-in-a-view.md)  
  
-   [ビューによるユーザー入力の解釈](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [印刷のビューのロール](../mfc/role-of-the-view-in-printing.md)  
  
-   [ビューをスクロールし、スケーリングします。](../mfc/scrolling-and-scaling-views.md)  
  
-   [ドキュメントやビューを初期化し、クリーンアップします](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
## 参照  
 [ドキュメント\/ビュー アーキテクチャ](../Topic/Document-View%20Architecture.md)   
 [CFormView クラス](../mfc/reference/cformview-class.md)   
 [レコード ビュー \(MFC データ アクセス\)](../data/record-views-mfc-data-access.md)   
 [シリアル化機構のバイパス](../mfc/bypassing-the-serialization-mechanism.md)