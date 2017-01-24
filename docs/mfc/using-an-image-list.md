---
title: "イメージ リストの使い方 | Microsoft Docs"
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
  - "CImageList クラス, 使用"
  - "イメージ リスト [C++]"
  - "リスト [C++], イメージ"
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# イメージ リストの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イメージ リストの一般的な使用法がパターンに従います。:  
  
-   [CImageList](../Topic/CImageList%20Class.md) オブジェクトを構築し、イメージ リストを作成し、`CImageList` オブジェクトに接続するに [作成](../Topic/CImageList::Create.md) 関数のオーバーロードの 1 を呼び出します。  
  
-   イメージ リストを作成したときにイメージを追加しない場合、[追加](../Topic/CImageList::Add.md) または [読み取り](../Topic/CImageList::Read.md) のメンバー関数を呼び出して、イメージ リストにイメージを追加します。  
  
-   そのコントロールの適切なメンバー関数またはイメージ リストの [描画](../Topic/CImageList::Draw.md) のメンバー関数を使用して、イメージ リストのイメージの描画独自を呼び出して、イメージ リストをコントロールに関連付けます。  
  
-   ユーザーがドラッグのイメージ リストの組み込みサポートを使用してイメージを、ドラッグすることができます。  
  
> [!NOTE]
>  イメージ リストが **new** の演算子を使用して作成された場合、それが終わったとき `CImageList` オブジェクトを破棄する必要があります。  
  
## 参照  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)