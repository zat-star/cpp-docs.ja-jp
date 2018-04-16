---
title: "イメージ リストの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- image lists [MFC], manipulating
- lists [MFC], image
- CImageList class [MFC], manipulating
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c2670f3935e2f4c482728000a268cb46cc9dbdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="manipulating-image-lists"></a>イメージ リストの操作
[置換](../mfc/reference/cimagelist-class.md#replace)メンバー関数にはイメージ リスト内のイメージが置き換えられます ([CImageList](../mfc/reference/cimagelist-class.md)) 新しいイメージを含むです。 この関数は、イメージ リスト オブジェクト内のイメージの数を動的に増やす必要がある場合に役立ちます。 もできます。 [呼び出す前](../mfc/reference/cimagelist-class.md#setimagecount)関数がイメージ リストに格納されているイメージの数を動的に変更します。 イメージ リストのサイズを大きくした場合は、呼び出す**置換**イメージをイメージの新しいスロットに追加します。 イメージ リストのサイズを小さくと、新しいサイズを超えたイメージが解放されます。  
  
 [削除](../mfc/reference/cimagelist-class.md#remove)メンバー関数は、イメージ リストのイメージを削除します。 [コピー](../mfc/reference/cimagelist-class.md#copy)メンバー関数をコピーしたりイメージ リスト内のイメージをスワップします。 この関数では、ソース イメージをコピー先のインデックスにコピーする必要がありますか、送信元と送信先のイメージを交換するかを指定することができます。  
  
 2 つのイメージ リストをマージすることによって、新しいイメージ リストを作成するには、適切なオーバー ロードを使用して、[作成](../mfc/reference/cimagelist-class.md#create)メンバー関数。 このオーバー ロード**作成**結合結果のイメージを格納する新しいイメージ リスト オブジェクト内の既存のイメージの最初のイメージが一覧表示します。 最初に透過的に 2 番目のイメージを描画して、新しいイメージが作成されます。 新しいイメージのマスクは、2 つの既存のイメージのマスクのビットの論理 OR 演算を実行した場合の結果を示します。  
  
 すべてのイメージがマージされ、新しいイメージ リスト オブジェクトに追加されるまでは、これが繰り返されます。  
  
 イメージ情報をアーカイブに記述するには呼び出すことによって、[書き込み](../mfc/reference/cimagelist-class.md#write)メンバー関数は、そのファイルを呼び出すことにより読み取る、[読み取り](../mfc/reference/cimagelist-class.md#read)メンバー関数。  
  
 [GetSafeHandle](../mfc/reference/cimagelist-class.md#getsafehandle)、[アタッチ](../mfc/reference/cimagelist-class.md#attach)、および[デタッチ](../mfc/reference/cimagelist-class.md#detach)メンバー関数にアタッチされているイメージ リストのハンドルを操作することができる、`CImageList`オブジェクト、中に、[DeleteImageList](../mfc/reference/cimagelist-class.md#deleteimagelist)メンバー関数を破棄せずのイメージ リストの削除、`CImageList`オブジェクト。  
  
## <a name="see-also"></a>参照  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)

