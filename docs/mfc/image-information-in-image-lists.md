---
title: "イメージ リストのイメージ情報 | Microsoft Docs"
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
  - "CImageList クラス, イメージ情報"
  - "イメージ リスト [C++], イメージ情報"
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# イメージ リストのイメージ情報
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CImageList](../Topic/CImageList%20Class.md) は イメージ リストから情報を取得するさまざまな機能が含まれています。  [GetImageInfo](../Topic/CImageList::GetImageInfo.md) のメンバー関数は、ピクセルあたりのカラー プレーンとビットのイメージとマスクのビットマップ、数値、およびイメージのビットマップ内のイメージに外接する四角形のハンドルなどの一つについての情報を `IMAGEINFO` の構造、塗りつぶします。  直接イメージのビットマップを作成する場合は、この情報を使用できます。  
  
 [GetImageCount](../Topic/CImageList::GetImageCount.md) のメンバー関数は、イメージ リスト内のイメージの数を取得します。  
  
 イメージ リストに基づいてアイコンを [ExtractIcon](../Topic/CImageList::ExtractIcon.md) メンバー関数を使用してイメージとマスクに作成できます。  関数の戻り値は新しいアイコンのハンドル。  
  
## 参照  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)