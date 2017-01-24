---
title: "コントロールへの列の追加 (レポート ビュー) | Microsoft Docs"
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
  - "CListCtrl クラス, 追加 (列を)"
  - "CListCtrl クラス, レポート ビュー"
  - "列 [C++], 追加 (CListCtrl に)"
  - "レポート ビュー (CListCtrl クラスの)"
  - "ビュー, レポート"
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コントロールへの列の追加 (レポート ビュー)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次の手順では [CListView](../mfc/reference/clistview-class.md) または [CListCtrl](../Topic/CListCtrl%20Class.md) オブジェクトに適用されます。  
  
 リスト コントロールでレポート ビューの場合、各リスト コントロール項目のさまざまなサブ項目を管理するメソッドを提供する列が表示されます。  この構成は、リスト コントロールの列とリスト コントロール項目に関連付けられたサブ項目間の 1 対 1 の対応に実装されます。  サブ項目の詳細については、「[コントロールに項目を追加します。](../mfc/adding-items-to-the-control.md)」を参照してください。  レポート ビューのリスト コントロールの例としては、Windows 95 と Windows 98 のエクスプローラーの詳細ビューによって提供されます。  最初の列一覧フォルダー、ファイル アイコンとラベル。  他の列のリスト ファイルのサイズ、ファイルの種類、日付の最終更新など。  
  
 列がリスト コントロールにいつでも追加することはできますが、列はコントロールを有効にする `LVS_REPORT` のスタイル ビットを持つ場合だけです。  
  
 各列に列をカテゴリに分類し、ユーザーが列のサイズを変更できる関連ヘッダー項目 \([CHeaderCtrl](../Topic/CHeaderCtrl%20Class.md)を参照してください\) オブジェクトがあります。  
  
 リスト コントロールが詳細ビューをサポートする場合は、リスト コントロール項目の有効なサブ項目の列を追加する必要があります。  [LV\_COLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743) 構造体を作成し、[InsertColumn](../Topic/CListCtrl::InsertColumn.md)を呼び出すことで、列を追加します。  必要な列 \(、ヘッダー項目とも呼ばれます\) を追加したら、埋め込まれたなヘッダー コントロールに属するメンバー関数とスタイルを使用してコントロールの順序を変更できます。  詳細については、「[ヘッダー項目コントロールの順序](../mfc/ordering-items-in-the-header-control.md)」を参照してください。  
  
> [!NOTE]
>  リスト コントロールが **LVS\_NOCOLUMNHEADER** のスタイルで作成されている場合は、列を挿入すると、無視されます。  
  
## 参照  
 [CListCtrl の使い方](../Topic/Using%20CListCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)