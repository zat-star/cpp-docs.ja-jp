---
title: "トラッカー | Microsoft Docs"
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
  - "アプリケーション [OLE], トラッカー"
  - "CDC クラス, トラッカー"
  - "CRectTracker クラス, 実装 (トラッカーを)"
  - "OLE アプリケーション [C++], トラッカー"
  - "OLE コンテナー, トラッカー"
  - "OLE サーバー アプリケーション, トラッカー"
  - "トラッカー"
  - "追跡 (OLE アイテムを)"
ms.assetid: dcd09399-6637-4621-80e5-d12670429787
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# トラッカー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CRectTracker](../mfc/reference/crecttracker-class.md) クラスは、アプリケーションの四角形項目とさまざまな表示スタイルを提供することによってユーザー間でユーザー インターフェイスを提供します。  これらのスタイルはハッチングされた実線または dotted 砕された境界が含まれています; 項目を覆うハッチ パターン; および境界の外側として配置できるハンドルのサイズを変更します。  TRACKER は OLE アイテム、`COleClientItem`から派生される、つまりオブジェクトとともによく使用されます。  トラッカーの四角形は、項目の現在の状態のビジュアル キューを示します。  
  
 MFC のサンプル [OCLIENT](../top/visual-cpp-samples.md) は OLE コンテナー アプリケーションの観点からトラッカーと OLE クライアント項目を使用して共通インターフェイスを示します。  トラッカーのさまざまなスタイルおよび機能の例については、MFC の一般的なサンプル [トラッカー](../top/visual-cpp-samples.md)に変換し、参照してください。  
  
 OLE アプリケーションのトラッカーの実装の詳細については、[トラッカー: OLE アプリケーションのトラッカーの実装](../mfc/trackers-implementing-trackers-in-your-ole-application.md)を参照します  
  
## 参照  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleClientItem クラス](../mfc/reference/coleclientitem-class.md)