---
title: "イメージ リストの使い方 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4321649bf4e8fe0e34fef8fe37b8c96598bef2c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-image-list"></a>イメージ リストの使い方
通常、イメージ リストの使い方は、次のパターンを次に示します。  
  
-   構築、 [CImageList](../mfc/reference/cimagelist-class.md)オブジェクトし、のオーバー ロードの 1 つを呼び出してその[作成](../mfc/reference/cimagelist-class.md#create)イメージ リストを作成しをアタッチする関数、`CImageList`オブジェクト。  
  
-   イメージ リストを作成したときに、イメージを追加しなかった場合に、イメージを追加、イメージ リストを呼び出して、[追加](../mfc/reference/cimagelist-class.md#add)または[読み取り](../mfc/reference/cimagelist-class.md#read)メンバー関数。  
  
-   イメージ リストをそのコントロールの適切なメンバー関数を呼び出すことによってコントロールに関連付けるまたはイメージ リストを使用して自分でイメージ リストのイメージの描画[描画](../mfc/reference/cimagelist-class.md#draw)メンバー関数。  
  
-   おそらくアクセス許可をドラッグするためのイメージ リストの組み込みサポートを使用して、イメージをドラッグします。  
  
> [!NOTE]
>  イメージ リストの作成時の**新しい**破棄する必要があります、演算子、`CImageList`オブジェクトが完了したことがあるときです。  
  
## <a name="see-also"></a>参照  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)

