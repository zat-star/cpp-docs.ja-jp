---
title: "サーバー : サーバーの実装 | Microsoft Docs"
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
  - "OLE サーバー アプリケーション, 実装 (OLE サーバーを)"
  - "サーバー, 実装"
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# サーバー : サーバーの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、MFC アプリケーション ウィザードでビジュアル編集サーバー アプリケーション用に作成するコードを示しています。  アプリケーション ウィザードを使用して、アプリケーション サーバーを実装するためのコードを記述する必要があります。この記事の区分。  
  
 新しいサーバー アプリケーションを作成するときにアプリケーション ウィザードを使用すると、大量のサーバー固有のコードを提供します。  既存のアプリケーションでビジュアル編集サーバー機能を追加する場合は、アプリケーション ウィザードで必要なサーバー コードの残りの部分を追加する前に提供するコードを複製する必要があります。  
  
 アプリケーション ウィザードで複数のカテゴリに分類されます。を提供するサーバー コード:  
  
-   サーバー リソースの定義:  
  
    -   サーバーが独自のウィンドウの埋め込まれたアイテムの編集中に使用されるメニュー リソース。  
  
    -   サーバーがアクティブな設定されるときに使用されるメニューとツール バー リソース。  
  
     これらのリソース詳細については、「[メニューとリソース: サーバーの追加](../mfc/menus-and-resources-server-additions.md)」を参照してください。  
  
-   `COleServerItem`から派生したクラス項目を定義します。  サーバー項目をさらにの詳細については、「[サーバー: サーバー項目](../mfc/servers-server-items.md)」を参照してください。  
  
-   `COleServerDoc`へのドキュメント クラスの基本クラスを変更する。  そのほかの詳細については、「[サーバー: サーバー ドキュメントの実装](../mfc/servers-implementing-server-documents.md)」を参照してください。  
  
-   `COleIPFrameWnd`から派生されるフレームウィンドウ クラスを定義します。  そのほかの詳細については、「[サーバー: 埋め込み先フレーム ウィンドウの実装](../Topic/Servers:%20Implementing%20In-Place%20Frame%20Windows.md)」を参照してください。  
  
-   サーバー アプリケーションのエントリを OLE システムと Windows 登録情報データベースとサーバーの新しいインスタンスを登録することで作成します。  このトピックの詳細については、「[登録](../mfc/registration.md)」を参照してください。  
  
-   サーバー アプリケーションを初期化し、起動します。  このトピックの詳細については、「[登録](../mfc/registration.md)」を参照してください。  
  
 詳細については、" MFC *リファレンス*"の [COleServerItem](../mfc/reference/coleserveritem-class.md)、[COleServerDoc](../Topic/COleServerDoc%20Class.md)と [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) を参照します。  
  
## 参照  
 [サーバー](../mfc/servers.md)   
 [コンテナー](../mfc/containers.md)   
 [メニューとリソース \(OLE\)](../mfc/menus-and-resources-ole.md)   
 [登録](../mfc/registration.md)