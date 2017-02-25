---
title: "OLE サーバー クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "COM コンポーネント, クラス"
  - "コンポーネント クラス"
  - "OLE サーバー アプリケーション, サーバー クラス"
  - "OLE サーバー ドキュメント"
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE サーバー クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのクラスは、サーバー アプリケーションによって使用されます。  サーバー ドキュメントは **CDocument**からではなく、`COleServerDoc` から派生されます。  `COleServerDoc` が `COleLinkingDoc`から派生されるため、サーバー ドキュメントには、そのリンク コンテナーである場合があることに注意してください。  
  
 `COleServerItem` クラスは別のドキュメントに埋め込むか、リンクできるドキュメントのドキュメントまたは部分を表します。  
  
 ドキュメント\/ビュー `COleTemplateServer` サポートが作成され、ほかのアプリケーションからの OLE オブジェクトを組み合わせるオブジェクトがコンテナーに編集できますが、`COleIPFrameWnd` と `COleResizeBar` は埋め込み先での編集をサポートします。  
  
 [COleServerDoc](../Topic/COleServerDoc%20Class.md)  
 サーバー アプリケーションのドキュメント クラスの基本クラスとして使用されます。  `COleServerDoc` オブジェクトは `COleServerItem` オブジェクトを選択して、サーバー サポートの概要を示します。  ビジュアル編集機能は、クラス ライブラリのドキュメント\/ビュー アーキテクチャを使用して指定されます。  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 `COleClientItem` と `COleServerItem`の抽象基本クラスです。  `CDocItem` からの派生クラスのオブジェクトは、文書内の部分を表します。  
  
 [COleServerItem](../mfc/reference/coleserveritem-class.md)  
 `COleServerDoc` 項目に OLE インターフェイスを表すために使用されます。  通常、埋め込まれたなドキュメントの一部を表す `COleServerDoc` の 1 種類のオブジェクトがあります。  ドキュメントの一部であるへのリンクは、それらがドキュメントの部分にリンクを表す、`COleServerItem` の多くのオブジェクトというサーバー。  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 サーバー ドキュメントが編集されているビューにフレーム ウィンドウを指定します。  
  
 [COleResizeBar](../mfc/reference/coleresizebar-class.md)  
 埋め込み先でのサイズ変更に標準のユーザー インターフェイスが用意されています。  このクラスのオブジェクトは `COleIPFrameWnd` オブジェクトとともに使用されます。  
  
 [COleTemplateServer](../mfc/reference/coletemplateserver-class.md)  
 フレームワークが提供するドキュメント\/ビュー アーキテクチャを使用してドキュメントを作成するために使用します。  作業に最も `COleTemplateServer` のオブジェクト委譲 `CDocTemplate` 関連のオブジェクトになります。  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE の例外処理でエラーが発生します。  このクラスは、コンテナーとサーバーの両方で使用されます。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)