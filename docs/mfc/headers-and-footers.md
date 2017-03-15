---
title: "ヘッダーとフッター | Microsoft Docs"
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
  - "フッター, 印刷"
  - "ヘッダー, 印刷"
  - "ページ フッター"
  - "ページ フッター, 印刷"
  - "ページ ヘッダー"
  - "ページ ヘッダー, 印刷"
  - "印刷 [MFC], ヘッダーとフッター"
  - "印刷 [MFC], マルチページ ドキュメント"
ms.assetid: b0be9c53-5773-4955-a777-3c15da745128
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ヘッダーとフッター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、印刷されたドキュメントにヘッダーとフッターを追加する方法について説明します。  
  
 画面のドキュメントを表示すると、ドキュメントの名前とドキュメントの現在の位置は、タイトル バー、ステータス バーに表示されます。  ドキュメントの印刷されたコピーを表示すると、ヘッダーやフッターに表示される名前とページ番号があると便利です。  これは、印刷や画面がどのように動作するかを WYSIWYG プログラムが別の一般的な方法です。  
  
 [OnPrint](../Topic/CView::OnPrint.md) のメンバー関数は、画面の表示の各ページを呼び出すため、および印刷だけ呼び出されるため、ヘッダーやフッターを印刷に適しています。  ヘッダーまたはフッターを印刷するには、別の関数を定義し、それに `OnPrint`のプリンター デバイス コンテキストを渡します。  ページの本文をヘッダーまたはフッターを重複させるように [OnDraw](../Topic/CView::OnDraw.md) を呼び出す前にウィンドウの原点または範囲を調整する必要がある場合があります。  ページに含まれるドキュメントの量を減らすことができるので、`OnDraw` を変更する必要があります。  
  
 ヘッダーまたはフッターに占める領域を補足する 1 とおりの方法が [CPrintInfo](../mfc/reference/cprintinfo-structure.md)の **m\_rectDraw** のメンバーを使用することです。  ページが印刷されるたびに、このメンバーはページの使用可能な領域に初期化されます。  ページの本文を印刷する前にヘッダーまたはフッターを印刷する、ヘッダーやフッターに占める領域を占有するに **m\_rectDraw** に格納された四角形のサイズを単純化するできます。  次 `OnPrint` はどの程度領域がページの本文を印刷するためになるかを確認するに **m\_rectDraw** を示すことができます。  
  
 [CDC](../Topic/CDC%20Class.md) の `StartPage` のメンバー関数を呼び出す前に呼び出されるため、ヘッダー、または別の名前、[OnPrepareDC](../Topic/CView::OnPrepareDC.md)から印刷することはできません。  この時点で、プリンター デバイス コンテキストはページ境界と見なされます。  `OnPrint` のメンバー関数からの印刷だけを実行できます。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [マルチページ ドキュメントの印刷](../mfc/multipage-documents.md)  
  
-   [印刷の GDI のリソースを割り当てます。](../mfc/allocating-gdi-resources.md)  
  
## 参照  
 [印刷](../mfc/printing.md)