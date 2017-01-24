---
title: "CImageList の使い方 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CImageList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImageList クラス, 使用"
  - "イメージ リスト コントロール"
ms.assetid: 3d2a909e-d641-46b7-aada-81cab1a29b41
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CImageList の使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CImageList](../Topic/CImageList%20Class.md)クラスによって表されるイメージ リストは、それぞれがインデックスによって参照できる同じサイズのイメージのコレクションです。  イメージ リストを効率的にアイコンまたはビットマップの大きいセットを管理するために使用されます。  ウィンドウではないため、イメージ リスト自体がコントロールではありません; ただし、リスト コントロール \([CListCtrl](../Topic/CListCtrl%20Class.md)\)、ツリー コントロール \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\)、およびタブ コントロール \([CTabCtrl](../Topic/CTabCtrl%20Class.md)\) を含むコントロールのさまざまな型として使用されます。  
  
 イメージ リストのイメージは、画面デバイスの形式を使用すると、一つの大きなビットマップに含まれています。  イメージ リストは、イメージを透過的に描画するために使用されるマスクを含むモノクロ ビットマップを含める場合があります \(アイコン\) のスタイル。  `CImageList` は イメージを描画し、そのイメージを作成し、イメージ リストを破棄し、イメージを追加および削除できるメンバー関数が、イメージ、マージのイメージとドラッグ イメージを提供します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [イメージ リストの種類](../Topic/Types%20of%20Image%20Lists.md)  
  
-   [イメージ リストを使用します。](../mfc/using-an-image-list.md)  
  
-   [イメージ リストの処理](../mfc/manipulating-image-lists.md)  
  
-   [イメージ リストのイメージの描画](../mfc/drawing-images-from-an-image-list.md)  
  
-   [イメージ リスト内のイメージのオーバーレイ](../mfc/image-overlays-in-image-lists.md)  
  
-   [イメージ リスト内のイメージにドラッグします。](../Topic/Dragging%20Images%20from%20an%20Image%20List.md)  
  
-   [イメージ リストのイメージ情報](../mfc/image-information-in-image-lists.md)  
  
## 参照  
 [コントロール](../mfc/controls-mfc.md)