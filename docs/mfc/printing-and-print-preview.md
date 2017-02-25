---
title: "印刷および印刷プレビュー | Microsoft Docs"
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
  - "プレビュー (印刷を)"
  - "印刷プレビュー"
  - "印刷 [C++]"
  - "印刷 [C++], 印刷プレビュー"
  - "印刷 [MFC]"
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 印刷および印刷プレビュー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC は [CView](../Topic/CView%20Class.md)クラスによってプログラムのドキュメントの印刷や印刷プレビューをサポートします。  基本的な印刷と印刷プレビュー用に、常にする必要 [OnDraw](../Topic/CView::OnDraw.md) ビュー クラスのメンバー関数をオーバーライドします。  この機能は、画面の表示は、実際のプリンターのプリンター デバイス コンテキスト、または画面のプリンターをシミュレートするデバイス コンテキストに描画できます。  
  
 または複数ページのドキュメントおよび印刷プレビューを管理し、印刷されたドキュメントにページを付け、ヘッダー、フッターを追加するコードを追加できます。  
  
 ここでは印刷する Microsoft Foundation Class ライブラリ \(MFC\) と既にフレームワークに組み込まれている印刷アーキテクチャを利用する方法がどのように実装されるかについて説明します。  ここでは、MFC の印刷プレビュー機能の簡単な実装をサポートする方法と、その機能を使用するため、変更する方法について説明します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [印刷](../mfc/printing.md)  
  
-   [印刷プレビュー アーキテクチャ](../mfc/print-preview-architecture.md)  
  
-   [サンプル](../top/visual-cpp-samples.md)  
  
## 参照  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)