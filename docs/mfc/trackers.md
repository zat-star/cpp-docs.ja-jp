---
title: "トラッカー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- trackers [MFC]
- OLE applications [MFC], trackers
- applications [OLE], trackers
- tracking OLE items [MFC]
- OLE containers [MFC], trackers
- CDC class [MFC], trackers
- CRectTracker class [MFC], implementing trackers
- OLE server applications [MFC], trackers
ms.assetid: dcd09399-6637-4621-80e5-d12670429787
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a36a327bcf2a1beb46119c9b6c2947d95473cbaf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="trackers"></a>トラッカー
[CRectTracker](../mfc/reference/crecttracker-class.md)クラスには、四角形のアイテムをアプリケーションに、さまざまな表示スタイルを提供することにより、ユーザーのユーザー インターフェイスが用意されています。 これらのスタイルが実線、斜線、または破線の罫線; を含めるアイテムをカバーするハッチ パターン外部または枠線内にあることができるハンドルのサイズを変更します。 トラッカーは多くの場合で使用される OLE アイテムと共にから派生したオブジェクトは、`COleClientItem`です。 トラッカーの四角形は、アイテムの現在の状態の視覚的な手掛かりを付与します。  
  
 MFC OLE サンプル[OCLIENT](../visual-cpp-samples.md)トラッカーとコンテナー アプリケーションの観点から見た OLE クライアント アイテムを使用して共通のインターフェイスを示しています。 さまざまなスタイルのデモとトラッカー オブジェクトの権限は、MFC の一般的なサンプルを参照してください。[トラッカー](../visual-cpp-samples.md)です。  
  
 OLE アプリケーションでのトラッカーの実装の詳細については、次を参照してください[トラッカー: OLE アプリケーションでのトラッカーの実装。](../mfc/trackers-implementing-trackers-in-your-ole-application.md)  
  
## <a name="see-also"></a>関連項目  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleClientItem クラス](../mfc/reference/coleclientitem-class.md)
