---
title: "イメージのイメージ リストのオーバーレイ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5e70365040b5f009e634a4867a4a1f974d47bd61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="image-overlays-in-image-lists"></a>イメージ リストのイメージのオーバーレイ
すべてのイメージ リスト ([CImageList](../mfc/reference/cimagelist-class.md)) オーバーレイ マスクとして使用するイメージの一覧が含まれています。 「オーバーレイ マスク」は、別のイメージ上に透過的に描画されるイメージです。 任意の画像は、オーバーレイ マスクとして使用できます。 イメージ リストごとに最大 4 つのオーバーレイ マスクを指定することができます。  
  
 オーバーレイ マスクの一覧を使用して、イメージのインデックスを追加する、 [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage)メンバー関数は、イメージのインデックスおよびオーバーレイ マスクのインデックス。 マスクのオーバーレイ インデックスは 1 ベースではなく 0 から始まることに注意してください。  
  
 1 回の呼び出しを使用してイメージ上にオーバーレイ マスクを描画する**描画**です。 パラメーターには、描画するイメージのインデックスと、オーバーレイ マスクのインデックスが含まれます。 使用する必要があります、[から](http://msdn.microsoft.com/library/windows/desktop/bb761408)マクロ オーバーレイ マスクのインデックスを指定します。 呼び出すときにオーバーレイ イメージを指定することも、[もう 1 つ](../mfc/reference/cimagelist-class.md#drawindirect)メンバー関数。  
  
## <a name="see-also"></a>参照  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)

