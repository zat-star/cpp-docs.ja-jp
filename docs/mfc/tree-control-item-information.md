---
title: "ツリー コントロールの項目の情報 | Microsoft Docs"
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
  - "CTreeCtrl クラス, 項目情報"
  - "ツリー コントロール, 項目情報"
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ツリー コントロールの項目の情報
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ツリー コントロール \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) にコントロール内の項目に関する情報を取得するいくつかのメンバー関数があります。  [GetItem](../Topic/CTreeCtrl::GetItem.md) のメンバー関数は、項目に関連付けられたデータの一部またはすべてを取得します。  このデータは、項目の子項目の状態、イメージ、テキスト、数値、およびアプリケーション定義の 32 ビット データ値を含めることができます。  その項目に関連付けられたデータの一部またはすべてを設定できる [SetItem](../Topic/CTreeCtrl::SetItem.md) の関数があります。  
  
 [GetItemState](../Topic/CTreeCtrl::GetItemState.md)、[GetItemText](../Topic/CTreeCtrl::GetItemText.md)、[GetItemData](../Topic/CTreeCtrl::GetItemData.md)と [GetItemImage](../Topic/CTreeCtrl::GetItemImage.md) のメンバー関数は、項目の属性を取得します。  これらの各関数に項目の属性を設定するための対応する Set 関数があります。  
  
 [GetNextItem](../Topic/CTreeCtrl::GetNextItem.md) のメンバー関数は、現在の項目に指定された関係を持つツリー コントロール項目を取得します。  この関数でその項目の親、次または前の最初に表示されるアイテムの子アイテムを取得できます。  、ツリーを走査するメンバー関数が使用されています: [GetRootItem](../Topic/CTreeCtrl::GetRootItem.md)、[GetFirstVisibleItem](../Topic/CTreeCtrl::GetFirstVisibleItem.md)、[GetNextVisibleItem](../Topic/CTreeCtrl::GetNextVisibleItem.md)、[GetPrevVisibleItem](../Topic/CTreeCtrl::GetPrevVisibleItem.md)、[GetChildItem](../Topic/CTreeCtrl::GetChildItem.md)、[GetNextSiblingItem](../Topic/CTreeCtrl::GetNextSiblingItem.md)、[GetPrevSiblingItem](../Topic/CTreeCtrl::GetPrevSiblingItem.md)、[GetParentItem](../Topic/CTreeCtrl::GetParentItem.md)、[GetSelectedItem](../Topic/CTreeCtrl::GetSelectedItem.md)と [GetDropHilightItem](../Topic/CTreeCtrl::GetDropHilightItem.md)。  
  
 [GetItemRect](../Topic/CTreeCtrl::GetItemRect.md) のメンバー関数は、ツリー コントロール項目の外接する四角形を取得します。  [GetCount](../Topic/CTreeCtrl::GetCount.md) と [GetVisibleCount](../Topic/CTreeCtrl::GetVisibleCount.md) メンバー関数はツリー コントロール項目の数、およびツリー コントロール ウィンドウに現在表示されている項目の数を個別に取得します。  特定の項目が [EnsureVisible](../Topic/CTreeCtrl::EnsureVisible.md) のメンバー関数を呼び出して、表示されることを確認できます。  
  
## 参照  
 [CTreeCtrl の使い方](../Topic/Using%20CTreeCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)