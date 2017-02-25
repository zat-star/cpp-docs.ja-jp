---
title: "コントロールへの項目の追加 | Microsoft Docs"
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
  - "CListCtrl クラス, 追加 (アイテムを)"
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# コントロールへの項目の追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リスト コントロール \([CListCtrl](../Topic/CListCtrl%20Class.md)\) に項目を追加するには、指定する情報種別に応じた形式の [InsertItem](../Topic/CListCtrl::InsertItem.md) メンバー関数を呼び出します。  [LV\_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 構造体を使用する形式もあります。  `LV_ITEM` 構造体には多くのメンバーがあるため、リスト コントロール項目の属性をより詳細に制御できます。  
  
 詳細ビューに関する場合、`LV_ITEM` 構造体で重要なメンバーは、`iItem` と `iSubItem` の 2 つです。  `iItem` メンバーは、構造体が参照する項目の 0 から始まるインデックスです。`iSubItem` メンバーは、サブ項目を示す 1 から始まるインデックスです。または、構造体が 1 つの項目に関する情報しか含んでいない場合は 0 になります。  この 2 つのメンバーを使用して、リスト コントロールが詳細ビューの場合に表示されるサブ項目情報の型と値を項目ごとに決定します。  詳細については、「[CListCtrl::SetItem](../Topic/CListCtrl::SetItem.md)」を参照してください。  
  
 これ以外のメンバーでは、項目のテキスト、アイコンの状態、項目データを指定します。「項目データ」はリスト ビュー項目に関連付けられたアプリケーション定義の値です。  `LV_ITEM` 構造体の詳細については、「[CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md)」を参照してください。  
  
 他の形式の `InsertItem` は、`LV_ITEM` 構造体のメンバーに対応する個々の値を 1 つ以上受け取ります。これにより、サポートする必要のあるメンバーだけを初期化できます。  一般的に、リスト項目の格納はリスト コントロールが管理しますが、"コールバック項目" を使用してアプリケーションで情報の一部を格納することもできます。詳細については、「[コールバック項目とコールバック マスク](../mfc/callback-items-and-the-callback-mask.md)」、および [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] の「[コールバック項目とコールバック マスク](http://msdn.microsoft.com/library/windows/desktop/bb774736)」を参照してください。  
  
 詳細については、「[Adding List\-View Items and Subitems \(リスト ビュー項目とサブ項目の追加\)](http://msdn.microsoft.com/library/windows/desktop/bb774736)」を参照してください。  
  
## 参照  
 [CListCtrl の使い方](../Topic/Using%20CListCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)