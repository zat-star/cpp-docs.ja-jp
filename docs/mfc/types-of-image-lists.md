---
title: "イメージ リストの種類 |Microsoft ドキュメント"
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
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84a2118978d5ebd722d4fe56cdeec2aa0f74a94e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="types-of-image-lists"></a>イメージ リストの種類
イメージ リストの 2 種類があります ([CImageList](../mfc/reference/cimagelist-class.md)): マスクとマスク。 「マスクされていないイメージ リスト」は、1 つまたは複数のイメージを含むカラー ビットマップで構成されます。 「マスクされたイメージ リスト」は、等しいサイズの 2 つのビットマップで構成されます。 1 つは、イメージを含むカラー ビットマップ、2 番目の一連のマスクを含むモノクロ ビットマップ-最初のビットマップのイメージごとに 1 つです。  
  
 オーバー ロードのいずれか、**作成**メンバー関数はイメージ リストをマスクするかどうかを示すフラグを受け取ります。 (他のオーバー ロードは、マスクされたイメージのリストを作成します)。  
  
 マスクされていないイメージが描画されると、対象のデバイス コンテキストにコピーされます。つまり、デバイス コンテキストの既存の背景色上に描画されます。 マスクされたイメージが描画されると、イメージのビットは、ターゲット デバイス コンテキストの背景色が透けてビットマップの透明な領域を通常生成した、マスクのビットと結合されます。 マスクされたイメージを描画するときに、いくつかの描画スタイルを指定できます。 たとえば、選択したオブジェクトを示すために、イメージ、ディザリングすることを指定できます。  
  
## <a name="see-also"></a>参照  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)

