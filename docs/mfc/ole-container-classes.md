---
title: "OLE コンテナー クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX クラス [C++]"
  - "コンテナー クラス [C++]"
  - "コンテナー [C++], OLE コンテナー アプリケーション"
  - "OLE [C++], クラス"
  - "OLE クラス [C++]"
  - "ビジュアル編集 [C++], クラス"
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE コンテナー クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのクラスは、コンテナー アプリケーションによって使用されます。  `COleLinkingDoc` と `COleDocument` は両方 `COleClientItem` オブジェクトのコレクションを管理します。  ドキュメントに埋め込まれたオブジェクトにリンクのサポートが必要かどうかを **CDocument**ドキュメント クラスから派生してではなく、`COleLinkingDoc` または `COleDocument`からは、から派生します。  
  
 別のドキュメントから埋め込まれたまたは別のドキュメントにリンクしているドキュメントの OLE アイテムを表すために `COleClientItem` オブジェクトを使用します。  
  
 [COleDocObjectItem](../Topic/COleDocObjectItem%20Class.md)  
 アクティブ ドキュメントのコンテインメントをサポートします。  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 複合ドキュメントの実装、および基本的なコンテナーのサポートに使用します。  クラスのコンテナーとして機能します `CDocItem`からは派生しました。  このクラスは、コンテナー ドキュメントの基本クラスとして使用され、`COleServerDoc`の基本クラスです。  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 `COleDocument` から派生したクラスのリンクにインフラストラクチャを提供する。  埋め込みオブジェクトにリンクを表示するには `COleDocument` の代わりにこのクラスからコンテナー アプリケーションのドキュメント クラスを派生する必要があります。  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 リッチ エディット コントロールにある OLE クライアント項目のリストを保持します。  [CRichEditView](../mfc/reference/cricheditview-class.md) と [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)で使用します。  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 `COleClientItem` と `COleServerItem`の抽象基本クラスです。  `CDocItem` からの派生クラスのオブジェクトは、文書内の部分を表します。  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md)  
 クライアントの埋め込まれたまたはリンクされたな OLE アイテムへの接続の側を表すクライアント項目クラス。  このクラスからクライアント項目を派生してください。  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 使用すると `CRichEditView` と `CRichEditDoc`をリッチ エディット コントロールに格納された OLE アイテムへのクライアント側アクセスを提供します。  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE の例外処理でエラーが発生します。  このクラスは、コンテナーとサーバーの両方で使用されます。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)