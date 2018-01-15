---
title: "グラフィック オブジェクトをデバイス コンテキストに選択する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5909625b816deb1303821aaec4034fa24f29be5f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>グラフィック オブジェクトをデバイス コンテキストに選択する
このトピックは、ウィンドウのデバイス コンテキストでグラフィック オブジェクトの使用に適用されます。 したら[描画オブジェクトを作成する](../mfc/one-stage-and-two-stage-construction-of-objects.md)、保存されている既定のオブジェクトの代わりに、デバイス コンテキストに選択する必要があります。  
  
 [!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]  
  
## <a name="lifetime-of-graphic-objects"></a>グラフィック オブジェクトの有効期間  
 によって返されるグラフィック オブジェクト[SelectObject](../mfc/reference/cdc-class.md#selectobject)は「一時」です。 これによってが削除される、 [OnIdle](../mfc/reference/cwinapp-class.md#onidle)クラスのメンバー関数`CWinApp`時刻の次回のプログラムがアイドル状態を取得します。 によって返されるオブジェクトを使用する限り`SelectObject`メイン メッセージ ループに制御を返すことがなく 1 つの関数、存在しないことが問題です。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [グラフィック オブジェクト](../mfc/graphic-objects.md)  
  
-   [グラフィック オブジェクトの 1 つのステージと 2 段階の構築](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [デバイス コンテキスト](../mfc/device-contexts.md)  
  
-   [ビューの描画](../mfc/drawing-in-a-view.md)  
  
## <a name="see-also"></a>参照  
 [グラフィック オブジェクト](../mfc/graphic-objects.md)

