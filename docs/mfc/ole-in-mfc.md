---
title: "MFC の OLE | Microsoft Docs"
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
  - "アプリケーション [OLE], 概要 (OLE の)"
  - "MFC [C++], OLE および"
  - "OLE [C++]"
  - "OLE アプリケーション [C++], 概要 (OLE の)"
  - "OLE コンポーネント オブジェクト モデル (COM)"
  - "OLE コンテナー, 概要 (OLE の)"
  - "OLE 項目"
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC の OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのトピックでは、MFC を使用して OLE プログラミングに関する基本事項について説明します。  MFC ライブラリには、OLE を使用するプログラムを作成する最も簡単な方法を提供し、T:  
  
-   OLE のビジュアル編集 \(埋め込み先編集の有効化\) を使用します。  
  
-   OLE コンテナーまたはサーバーとして使用します。  
  
-   ドラッグ アンド ドロップ機能を実装する。  
  
-   日付と時刻のデータを使用します。  
  
-   エクスポートされた DLL 関数のエントリ ポイント、OLE\/COM インターフェイス エントリ ポイントとウィンドウ プロシージャのエントリ ポイントを含む MFC モジュールの状態データの管理します。  
  
 また、プログラムから別のプログラムを操作するには、[オートメーション](../mfc/automation.md) または [リモート オートメーション](../mfc/remote-automation.md) を使用できます。  
  
> [!NOTE]
>  OLE オブジェクトという用語は OLE コンテナー、OLE サーバー、OLE アイテム、埋め込み先編集の有効化 \(またはビジュアル編集\)、トラッカー、ドラッグ アンド ドロップと、メニューのマージなどリンクと埋め込みに関連付けられた文書が表示されます。  用語のアクティブは Component Object Model \(COM\) および ActiveX コントロールなどの COM ベースのオブジェクトに適用されます。  OLE オートメーションは、"と呼ばれます。  
  
## このセクションの内容  
 [OLE の背景](../mfc/ole-background.md)  
 どのように関する OLE について、概要を示します。  
  
 [アクティベーション](../mfc/activation-cpp.md)  
 OLE アイテムの編集をアクティブ化の役割について説明します。  
  
 [コンテナー](../mfc/containers.md)  
 OLE でコンテナーを使用してリンクを提供します。  
  
 [データ オブジェクトとデータ ソース](../mfc/data-objects-and-data-sources-ole.md)  
 トピックへのリンクを `COleDataObject` と `COleDataSource` クラスを使用できます。  
  
 [ドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)  
 コピーと貼り付けを OLE で使用する方法について説明します。  
  
 [OLE メニューとリソース](../mfc/menus-and-resources-ole.md)  
 MFC の OLE ドキュメントのアプリケーションのメニューとリソースの使用例です。  
  
 [登録](../mfc/registration.md)  
 サーバーのインストールと初期化について説明します。  
  
 [&#91;サーバー&#93;](../mfc/servers.md)  
 コンテナー アプリケーションによって使用される OLE アイテム \(コンポーネント\) を作成する方法について説明します。  
  
 [トラッカー](../mfc/trackers.md)  
 Web ページに OLE クライアント項目と対話するためのグラフィカル インターフェイスを提供する `CRectTracker` クラスに関する情報を提供します。  
  
## 関連項目  
 [コネクション ポイント](../mfc/connection-points.md)  
 MFC クラス `CCmdTarget` と `CConnectionPoint`を使用してコネクション ポイントを \(以前の OLE コネクション ポイントと呼ばれる\) を実装する方法について説明します。  
  
 [コンテナーとサーバー COM コンポーネント](../mfc/containers-advanced-features.md)  
 既存のコンテナー アプリケーションに省略可能な高度な機能を組み込むために必要な手順について説明します。  
  
 [コンポーネント オブジェクト モデル](http://msdn.microsoft.com/library/windows/desktop/ms694363)  
 MFC せずによる使用方法について説明します。  
  
## 参照  
 [概念](../mfc/mfc-concepts.md)