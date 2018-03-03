---
title: "コンテナー: クライアント アイテム |Microsoft ドキュメント"
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
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aa80911ff14d329dc483cd6497393c6c5595ef2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="containers-client-items"></a>コンテナー : クライアント アイテム
この記事では、クライアント アイテムについて説明し、アプリケーションでそのクライアント アイテムを派生する必要があります。  
  
 クライアント アイテムに含まれているまたは OLE コンテナー アプリケーションのドキュメントによって参照される他のアプリケーションに属するデータ アイテムです。 ドキュメント内に含まれるデータを含むクライアント アイテムが埋め込まれます。データを含むが、コンテナー ドキュメントによって参照されている別の場所に保存されているものがリンクされています。  
  
 OLE アプリケーションでドキュメント クラスがクラスから派生した[COleDocument](../mfc/reference/coledocument-class.md)からではなく**CDocument**です。 `COleDocument`クラスから継承**CDocument**どの MFC アプリケーションの基にドキュメント/ビュー アーキテクチャを使用するために必要なすべての機能です。 `COleDocument`コレクションとして、ドキュメントを処理するインターフェイスも定義`CDocItem`オブジェクト。 いくつか`COleDocument`の追加、取得、およびそのコレクションの要素を削除するメンバー関数が用意されています。  
  
 すべてのコンテナー アプリケーションから少なくとも 1 つのクラスを派生する必要があります`COleClientItem`です。 このクラスのオブジェクトは、埋め込みまたはリンク、OLE ドキュメント内の項目を表します。 ドキュメントから削除される場合を除き、これらのオブジェクトは、それらを含むドキュメントの有効期間存在します。  
  
 `CDocItem`基本クラスは、`COleClientItem`と`COleServerItem`です。 これらの 2 つから派生したクラスのオブジェクトは、それぞれ OLE アイテムと、クライアントとサーバー アプリケーション間の仲介役として機能します。 MFC フレームワークが、クライアント アプリケーションの新しいオブジェクトを追加するには、ドキュメントに新しい OLE 項目が追加されるたびに`COleClientItem`-クラスを派生クラスのドキュメントのコレクションから`CDocItem`オブジェクト。  
  
## <a name="see-also"></a>参照  
 [コンテナー](../mfc/containers.md)   
 [コンテナー: 複合ファイル](../mfc/containers-compound-files.md)   
 [コンテナー: ユーザー インターフェイスの問題](../mfc/containers-user-interface-issues.md)   
 [コンテナー: 高度な機能](../mfc/containers-advanced-features.md)   
 [COleClientItem クラス](../mfc/reference/coleclientitem-class.md)   
 [COleServerItem クラス](../mfc/reference/coleserveritem-class.md)
