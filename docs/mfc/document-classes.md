---
title: "ドキュメント クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.document"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ドキュメント クラス"
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ドキュメント クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ドキュメントテンプレート オブジェクトで作成したドキュメント クラスのオブジェクトは、アプリケーションのデータを管理します。  これらのクラスの 1 つがからドキュメントのクラスを派生します。  
  
 ドキュメント クラスのオブジェクトは、ビュー オブジェクトと対話します。  ビュー オブジェクトは、ウィンドウのクライアント領域を表し、文書内にデータを表示し、ユーザーが操作できるようにします。  ドキュメントとビューはドキュメントテンプレート オブジェクトによって作成されます。  
  
 [CDocument](../Topic/CDocument%20Class.md)  
 アプリケーション固有のドキュメントの基本クラスです。  **CDocument**からドキュメント クラスを派生してください。  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 複合ドキュメントの実装、および基本的なコンテナーのサポートに使用します。  クラスのコンテナーとして機能します [CDocItem](../mfc/reference/cdocitem-class.md)からは派生しました。  このクラスは、コンテナー ドキュメントの基本クラスとして使用され、`COleServerDoc`の基本クラスです。  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 `COleDocument` から派生したクラスのリンクにインフラストラクチャを提供する。  埋め込みオブジェクトにリンクを表示するには `COleDocument` の代わりにこのクラスからコンテナー アプリケーションのドキュメント クラスを派生する必要があります。  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 リッチ エディット コントロールにある OLE クライアント項目のリストを保持します。  [CRichEditView](../mfc/reference/cricheditview-class.md) と [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)で使用します。  
  
 [COleServerDoc](../Topic/COleServerDoc%20Class.md)  
 サーバー アプリケーションのドキュメント クラスの基本クラスとして使用されます。  `COleServerDoc` オブジェクトは [COleServerItem](../mfc/reference/coleserveritem-class.md) オブジェクトを選択して、サーバー サポートの概要を示します。  ビジュアル編集機能は、クラス ライブラリのドキュメント\/ビュー アーキテクチャを使用して指定されます。  
  
 [CHtmlEditDoc](../mfc/reference/chtmleditdoc-class.md)  
 、[CHtmlEditView](../mfc/reference/chtmleditview-class.md)を、MFC のドキュメント\/ビュー アーキテクチャのコンテキストで WebBrowser 編集プラットフォーム HTML 機能が用意されています。  
  
## 関連クラス  
 ドキュメント クラス オブジェクトは永続的です。つまり、ストレージ メディアの状態を記述して読み取ることができます。  MFC は、ストレージ メディアをドキュメント内のデータを転送することを容易にするために `CArchive` クラスが用意されています。  
  
 [CArchive](../mfc/reference/carchive-class.md)  
 シリアル化を通じてオブジェクトの実装の永続ストレージに [CFile](../mfc/reference/cfile-class.md) オブジェクトに協力して \([CObject::Serialize](../Topic/CObject::Serialize.md)を参照してください。  
  
 ドキュメントは、OLE オブジェクトを含めることができます。  `CDocItem` は、サーバーとクライアントの項目の基本クラスです。  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 [COleClientItem](../mfc/reference/coleclientitem-class.md) と [COleServerItem](../mfc/reference/coleserveritem-class.md)の抽象基本クラスです。  `CDocItem` からの派生クラスのオブジェクトは、文書内の部分を表します。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)