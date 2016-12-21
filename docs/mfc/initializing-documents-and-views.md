---
title: "ドキュメントとビューの初期化 | Microsoft Docs"
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
  - "ドキュメント, 初期化"
  - "初期化 (ドキュメントを)"
  - "初期化 (オブジェクトを), ドキュメント オブジェクト"
  - "初期化 (ビューを)"
  - "ビュー, 初期化"
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ドキュメントとビューの初期化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ドキュメントは、次の 2 とおりの方法で作成されるため、ドキュメント クラスは、両方の方法をサポートする必要があります。  最初に、新しいコマンド ファイルと新しい空の図面を作成できます。  この場合、クラス [CDocument](../Topic/CDocument%20Class.md)の [OnNewDocument](../Topic/CDocument::OnNewDocument.md) のメンバー関数のオーバーライドのドキュメントを初期化してください。  第 2 に、ファイルの内容がファイルから読み込んだ新しいドキュメントを作成する場合は、ファイル メニューの開くコマンドを使用できます。  この場合、クラス **CDocument**の [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md) のメンバー関数のオーバーライドのドキュメントを初期化してください。  初期化が同じである場合、両方のオーバーライドで共通のメンバー関数を呼び出すことができます。また、`OnOpenDocument` は、Clean ドキュメントを初期化し、オープン操作を終了する場合に `OnNewDocument` を呼び出すことができます。  
  
 ビューはドキュメントの作成後に作成されます。  ビューを初期化するのに最適なタイミングは、フレームワークがドキュメント フレーム ウィンドウとビューを作成したら、です。  [CView](../Topic/CView%20Class.md)の [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) のメンバー関数をオーバーライドしてビューを初期化できます。  文書が変更されるたびに初期設定をやり直す必要がある場合は、何も変更するため、[OnUpdate](../Topic/CView::OnUpdate.md)をオーバーライドできます。  
  
## 参照  
 [ドキュメントとビューの初期化と後処理](../mfc/initializing-and-cleaning-up-documents-and-views.md)