---
title: "イメージ リストの操作 | Microsoft Docs"
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
  - "CImageList クラス, 操作"
  - "イメージ リスト [C++], 操作"
  - "リスト [C++], イメージ"
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# イメージ リストの操作
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[置換](../Topic/CImageList::Replace.md) のメンバー関数では新しいイメージとリスト \([CImageList](../Topic/CImageList%20Class.md)\) イメージを置き換えます。  この関数は、動的にイメージ リスト オブジェクト内のイメージの数を増やす必要がある場合にも役立ちます。  [SetImageCount](../Topic/CImageList::SetImageCount.md) 関数は動的にイメージ リスト内のイメージ数を変更します。  イメージ リストのサイズを大きくすると、新しいイメージ スロットにイメージを追加する **置換** 呼び出し。  イメージ リストのサイズを小さくすると、新しいサイズを超えるイメージは解放されます。  
  
 [削除](../Topic/CImageList::Remove.md) のメンバー関数は、イメージ リストのイメージを削除します。  [コピー](../Topic/CImageList::Copy.md) のメンバー関数では、イメージ リスト内のイメージのコピーまたは交換できます。  この関数は、ソース イメージを先のインデックスにコピーするか、または移動元と移動先のイメージが交換されるかどうかを示すことができます。  
  
 2 種類のイメージ リストのマージによって新しいイメージ リストを作成するには、[作成](../Topic/CImageList::Create.md) のメンバー関数の適切なオーバーロードを使用してください。  **作成** のこのオーバーロードは、新しいイメージ リスト オブジェクトで生成されたイメージを格納する既存のイメージ リストの最初のイメージをマージします。  新しいイメージは第 1 の 2 番目のイメージを透過的に描画することによって生成されます。  新しいイメージのマスクは 2 個の既存のイメージのマスク ビットの a 論理 OR 演算を実行した結果です。  
  
 これにより、すべてのイメージが新しいイメージ リスト オブジェクトにマージされ、追加されるまで繰り返されます。  
  
 アーカイブに [Write](../Topic/CImageList::Write.md) メンバー関数を呼び出してイメージ情報を記述し、[読み取り](../Topic/CImageList::Read.md) のメンバー関数を呼び出すことで読み取ることができます。  
  
 [DeleteImageList](../Topic/CImageList::DeleteImageList.md) のメンバー関数は `CImageList` オブジェクトを破棄せずに、イメージ リストを削除するに [GetSafeHandle](../Topic/CImageList::GetSafeHandle.md)、[アタッチ](../Topic/CImageList::Attach.md)と [デタッチ](../Topic/CImageList::Detach.md) のメンバー関数は `CImageList` オブジェクトは、イメージ リストの添付のハンドルを処理できるようにします。  
  
## 参照  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)