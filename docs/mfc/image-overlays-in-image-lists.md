---
title: "イメージ リストのイメージのオーバーレイ | Microsoft Docs"
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
  - "CImageList クラス, イメージのオーバーレイ"
  - "イメージ リスト [C++], イメージのオーバーレイ"
  - "オーバーレイ"
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# イメージ リストのイメージのオーバーレイ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

すべてのイメージ リスト \([CImageList](../Topic/CImageList%20Class.md)\) がオーバーレイ マスクとして使用するイメージの一覧が表示されます。  「Overlay マスク」は別のイメージに透過的に描画されるイメージです。  どのイメージがオーバーレイ マスクとして使用できます。  イメージ リストごとに最大 4 個の上にあられされたマスクを指定できます。  
  
 オーバーレイ マスクの一覧に [SetOverlayImage](../Topic/CImageList::SetOverlayImage.md) のメンバー関数で、イメージのインデックスを使用してイメージのインデックス、オーバーレイ マスクのインデックスを追加します。  オーバーレイ マスクのインデックスがインデックス番号が 0 から始まるではなくインデックス番号が 1 から始まるであることに注意してください。  
  
 **描画**に単一の呼び出しを使用してイメージ上にオーバーレイ マスクを描画します。  パラメーターは、描画するイメージのインデックス、オーバーレイ マスクのインデックスが含まれています。  オーバーレイ マスクのインデックスを指定するために [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) マクロを使用する必要があります。  [DrawIndirect](../Topic/CImageList::DrawIndirect.md) メンバー関数を呼び出す場合は、オーバーレイ イメージを指定できます。  
  
## 参照  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)