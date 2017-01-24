---
title: "サーバー : サーバー ドキュメントの実装 | Microsoft Docs"
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
  - "OLE サーバー アプリケーション, 実装 (OLE サーバーを)"
  - "OLE サーバー アプリケーション, 管理 (サーバー ドキュメントの)"
  - "サーバー ドキュメント, 実装"
  - "サーバー, サーバー ドキュメント"
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# サーバー : サーバー ドキュメントの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、アプリケーション ウィザードで OLE サーバー オプションを使用して正常にサーバーのドキュメントを実装するために必要な手順について説明します。  
  
#### サーバー ドキュメント クラスを定義するには  
  
1.  **CDocument**の代わりに `COleServerDoc` ドキュメントからクラスを派生してください。  
  
2.  `COleServerItem`から派生したクラスで、サーバー項目を作成します。  
  
3.  サーバー ドキュメント クラスの `OnGetEmbeddedItem` メンバー関数を実装してください。  
  
     `OnGetEmbeddedItem` は コンテナー アプリケーションのユーザーが埋め込まれたアイテムを作成または編集するときに呼び出されます。  これは、ドキュメント全体を表す項目を返す必要があります。  これは `COleServerItem`オブジェクト\-派生クラスとして作成します。  
  
4.  ドキュメントの内容をシリアル化するに `Serialize` のメンバー関数をオーバーライドします。  ドキュメントのネイティブ データを表すために使用するサーバー項目の一覧をシリアル化する必要はありません。  詳細については、記事 [サーバー: サーバー項目](../mfc/servers-server-items.md)の *サーバー項目の実装を* 参照します。  
  
 サーバー ドキュメントが作成されると、フレームワークは自動的に、OLE システム DLL を使用してドキュメントを登録します。  これは、DLL はサーバーのドキュメントを識別できます。  
  
 詳細については、" MFC *リファレンス*"の [COleServerItem](../mfc/reference/coleserveritem-class.md) と [COleServerDoc](../Topic/COleServerDoc%20Class.md) を参照します。  
  
## 参照  
 [サーバー](../mfc/servers.md)   
 [サーバー : サーバー アイテム](../mfc/servers-server-items.md)   
 [サーバー : サーバーの実装](../mfc/servers-implementing-a-server.md)   
 [サーバー : 埋め込み先フレーム ウィンドウの実装](../Topic/Servers:%20Implementing%20In-Place%20Frame%20Windows.md)