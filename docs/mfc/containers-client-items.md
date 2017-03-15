---
title: "コンテナー : クライアント アイテム | Microsoft Docs"
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
  - "クライアント アイテムと OLE コンテナー"
  - "OLE コンテナー, クライアント アイテム"
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# コンテナー : クライアント アイテム
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この記事は、説明します。クラスからアプリケーションがクライアント項目を派生するかクライアント項目と、います。  
  
 クライアント項目は別のアプリケーションに属する含まれていたり、OLE コンテナー アプリケーションのドキュメントで参照されるデータ項目です。  データをドキュメントに含まれるクライアント項目が埋め込まれます; データがコンテナー ドキュメントによって参照される別の場所に格納されているアセンブリにリンクされます。  
  
 OLE アプリケーションのドキュメント クラスは **CDocument**からではなく、クラス [COleDocument](../mfc/reference/coledocument-class.md) から派生されます。  `COleDocument` クラスは **CDocument** から MFC アプリケーションに基づくドキュメント\/ビュー アーキテクチャを使用するために必要なすべての機能を継承します。  `COleDocument` は、`CDocItem` オブジェクトのコレクションとしてドキュメントを扱うインターフェイスを定義します。  `COleDocument` のメンバー関数は、コレクションの要素を追加、取得すること、および削除するために使用されます。  
  
 任意のコンテナー アプリケーションは `COleClientItem`から 1 個以上のクラスを派生する必要があります。  このクラスのオブジェクトは OLE ドキュメントで、埋め込まれたまたはリンクされた作業項目を表します。  これらのオブジェクトは、ドキュメントが有効な間はドキュメントから削除する、です。  
  
 `CDocItem` は、`COleClientItem` および `COleServerItem` の基本クラスです。  これら二つのクラスの派生オブジェクトは OLE アイテムとクライアント アプリケーションとサーバー アプリケーションの仲立ちとして、それぞれ機能します。  新しい OLE アイテムが文書に追加されるたびに、MFC フレームワークは、クライアント アプリケーションの `COleClientItem`の新しいオブジェクト \(ドキュメントの `CDocItem` オブジェクトのコレクションに派生クラスを追加します。  
  
## 参照  
 [コンテナー](../mfc/containers.md)   
 [コンテナー : 複合ファイル](../mfc/containers-compound-files.md)   
 [コンテナー : ユーザー インターフェイスの問題](../mfc/containers-user-interface-issues.md)   
 [コンテナー : 高度な機能](../mfc/containers-advanced-features.md)   
 [COleClientItem クラス](../mfc/reference/coleclientitem-class.md)   
 [COleServerItem クラス](../mfc/reference/coleserveritem-class.md)