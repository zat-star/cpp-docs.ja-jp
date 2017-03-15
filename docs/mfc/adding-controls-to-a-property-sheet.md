---
title: "プロパティ シートへのコントロールの追加 | Microsoft Docs"
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
  - "コントロール [MFC], 追加 (プロパティ シートに)"
  - "プロパティ シート, 追加 (コントロールを)"
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# プロパティ シートへのコントロールの追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

既定では、プロパティ シートのプロパティ ページ、タブ インデックスと OK、キャンセルのウィンドウ領域を割り当て、ボタンを適用します。\(最適なモードレス プロパティ シートに OK を持たず、取り消しするには、ボタンを選択します。\) プロパティ シートに他のコントロールを追加できます。  たとえば、外部オブジェクトに適用されている場合、現在の設定がどのように、プロパティ ページの領域の右側をユーザーに示すためにプレビュー ウィンドウを追加できます。  
  
 `OnCreate` ハンドラーのプロパティ シート ダイアログ ボックスにコントロールを追加できます。  Kind 追加コントロールは通常、プロパティ シート ダイアログのサイズを大きくする必要があります。  基本クラス **CPropertySheet::OnCreate**を、現在割り当てられているプロパティ シート ウィンドウの幅と高さを取得するに [GetWindowRect](../Topic/CWnd::GetWindowRect.md) 呼び出しを呼び出した後に、四角形の次元を展開して、プロパティ シートでウィンドウのサイズを変更するに [MoveWindow](../Topic/CWnd::MoveWindow.md) を呼び出します。  
  
## 参照  
 [プロパティ シート](../mfc/property-sheets-mfc.md)   
 [CPropertyPage クラス](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet クラス](../mfc/reference/cpropertysheet-class.md)