---
title: "サーバー : サーバー アイテム | Microsoft Docs"
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
  - "アーキテクチャ [C++], サーバー アイテム"
  - "OLE サーバー アプリケーション, サーバー アイテム"
  - "サーバー アイテム"
  - "サーバー アイテム, 実装"
  - "サーバー [C++], サーバー アイテム"
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# サーバー : サーバー アイテム
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーが埋め込まれたまたはリンクされたな OLE アイテムを編集できるように、コンテナーがサーバーを起動するときに、サーバー アプリケーションが作成する「サーバー項目」`COleServerItem`から派生したクラスのオブジェクトであるサーバー項目はサーバー ドキュメントとコンテナー アプリケーション間のインターフェイスを提供します。  
  
 `COleServerItem` クラスはコンテナーからの要求に対して OLE で呼び出される複数のオーバーライドできるなメンバー関数、通常は定義します。  サーバー項目はサーバー ドキュメントまたはドキュメント全体の一部を表すことができます。  項目が OLE コンテナー ドキュメントに埋め込むと、サーバー項目はサーバー全体ドキュメントを表します。  OLE アイテムをリンクすると、サーバー項目はリンクが一部または全体かどうかサーバー ドキュメントまたはドキュメント全体の一部として表すことができます。  
  
 [HIERSVR](../top/visual-cpp-samples.md) のサンプル \(たとえば、サーバー項目クラス、**CServerItem**で、クラス **CServerNode**オブジェクトへのポインターであるメンバーを持ちます。  **CServerNode** オブジェクトは、ツリーの HIERSVR アプリケーションのドキュメントのノードです。  **CServerNode** オブジェクトがルート ノードの場合、**CServerItem** オブジェクトは、ドキュメント全体を表します。  **CServerNode** オブジェクトに子ノードの場合、**CServerItem** オブジェクトは、文書内の部分を表します。  MFC にこの操作の例については、" OLE [HIERSVR](../top/visual-cpp-samples.md) サンプルを参照してください。  
  
##  <a name="_core_implementing_server_items"></a> サーバー項目の実装  
 アプリケーションの「スタート」コードが生成される場合、アプリケーションのウィザードを使用して初期コードをサーバー項目を含めるために行う必要があるのは OLE オプション ページからサーバー オプションの 1 つがを選択するだけです。  既存のアプリケーションをサーバー項目を追加した場合は、次の手順を実行する:  
  
#### サーバー項目を実装するには  
  
1.  `COleServerItem` の派生クラスを作成します。  
  
2.  派生クラスでは、`OnDraw` のメンバー関数をオーバーライドします。  
  
     フレームワークは、メタファイルに OLE アイテムを行うに `OnDraw` を呼び出します。  コンテナー アプリケーションは項目を表示するには、このメタファイルを使用します。  アプリケーションのビュー クラスにも、サーバー アプリケーションがアクティブな場合に、項目の表示に使用される `OnDraw` のメンバー関数があります。  
  
3.  サーバー ドキュメント クラスの `OnGetEmbeddedItem` のオーバーライドを実装してください。  詳細については、[サーバー: サーバー ドキュメントの実装](../mfc/servers-implementing-server-documents.md) と MFC OLE [HIERSVR](../top/visual-cpp-samples.md)サンプルを参照してください。  
  
4.  サーバー項目 `OnGetExtent` クラスのメンバー関数を実装してください。  フレームワークは、項目のサイズを取得するには、この関数を呼び出します。  既定の実装では、何も行われません。  
  
##  <a name="_core_a_tip_for_server.2d.item_architecture"></a> サーバー項目アーキテクチャのヒント  
 [サーバー項目の実装](#_core_implementing_server_items)に示すように、サーバー アプリケーションでは、サーバーに対する VIEW とコンテナー アプリケーションで使用されるメタファイルの項目の両方にする必要があります。  Microsoft Foundation Class ライブラリ アプリケーション アーキテクチャでは、ビュー クラスの `OnDraw` のメンバー関数は、編集すると、項目は \(*クラス ライブラリ リファレンス*の [CView::OnDraw](../Topic/CView::OnDraw.md) を参照してください。  サーバー項目の `OnDraw` はメタファイルに項目を他の場合は \([COleServerItem::OnDraw](../Topic/COleServerItem::OnDraw.md)を参照してください。  
  
 ヘルパー関数をサーバーに書き込むドキュメント クラスとビューとサーバー項目クラスで `OnDraw` 関数からの呼び出しによってコードの重複を避けることができます。  MFC の OLE サンプル [HIERSVR](../top/visual-cpp-samples.md) はこの戦略を使用します: 関数は **CServerView::OnDrawCServerItem::OnDraw** と項目の両方を行うに **CServerDoc::DrawTree** を呼び出します。  
  
 さまざまな条件で描画するため、ビューと項目の両方 `OnDraw` のメンバー関数があります。  ビューは、スクロール バーのようなズームなどの要因を選択のサイズと範囲、クリッピングとユーザー インターフェイス要素に検討する必要があります。  サーバー項目は、全体の OLE オブジェクトを常に描画します。  
  
 詳細については、" MFC *リファレンス*"の [CView::OnDraw](../Topic/CView::OnDraw.md)、[COleServerItem](../mfc/reference/coleserveritem-class.md)、[COleServerItem::OnDraw](../Topic/COleServerItem::OnDraw.md)と [COleServerDoc::OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md) を参照します。  
  
## 参照  
 [サーバー](../mfc/servers.md)