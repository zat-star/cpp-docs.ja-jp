---
title: "イメージ リストの作成 | Microsoft Docs"
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
  - "CListCtrl クラス, 作成 (イメージ リストを)"
  - "イメージ リスト [C++], 作成 (CListCtrl の)"
  - "リスト [C++], イメージ"
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# イメージ リストの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イメージ リストを作成するには [CListView](../mfc/reference/clistview-class.md) または [CListCtrl](../Topic/CListCtrl%20Class.md)を使用しても同じです。  
  
> [!NOTE]
>  リスト コントロールが `LVS_ICON` のスタイルが含まれている場合にだけイメージ リストが必要です。  
  
 一つ以上のイメージ リストを作成するために `CImageList` クラスを使用して、大きいアイコン、小さいアイコン、および状態の場合\)。  [CImageList](../Topic/CImageList%20Class.md)を参照し、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [リスト ビューのイメージ リスト](http://msdn.microsoft.com/library/windows/desktop/bb774736) を参照してください。  
  
 各イメージ リストの呼び出し [CListCtrl::SetImageList](../Topic/CListCtrl::SetImageList.md) ; `CImageList` の適切なオブジェクトへのポインターを渡します。  
  
## 参照  
 [CListCtrl の使い方](../Topic/Using%20CListCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)