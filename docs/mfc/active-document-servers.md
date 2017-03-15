---
title: "Active ドキュメント サーバー | Microsoft Docs"
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
  - "Active ドキュメント サーバー [C++]"
  - "アクティブ ドキュメント [C++], サーバー"
  - "サーバー [C++], アクティブ ドキュメント"
ms.assetid: 131fec1e-02a0-4305-a7ab-903b911232a7
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Active ドキュメント サーバー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

他のアプリケーションの種類の Word、Excel、PowerPoint のホストのような Active ドキュメント サーバーはドキュメント アクティブ ドキュメントと呼ばれます。   \(別のドキュメント ページ内に表示される\) とは異なり、埋め込みオブジェクト、Active ドキュメントは完全なインターフェイスを提供し、それらを作成するサーバー アプリケーションのネイティブ機能を完了します。  ユーザーはこれらの任意のアプリケーションの完全なパワーを使用して \(有効なアクティブ ドキュメントの場合\) を作成することはできません。また、単一のエンティティとして作成されたプロジェクトを処理できます。  
  
 Active ドキュメントは、複数のページがあり、常にでき、埋め込み先編集です。  コンテナーの **ファイル** と **ヘルプ** メニューとメニューをマージするユーザー インターフェイスのアクティブ ドキュメントのコントロールの部分。  これらはコンテナーの編集領域を占有し、プリンターのページ \(余白、フッターなど\) のビューとレイアウトを制御します。  
  
 MFC はドキュメント\/ビュー インターフェイス、コマンド ディスパッチ マップ、印刷、メニュー コントロールやレジストリ管理を持つアクティブ ドキュメント サーバーを実装します。  固有のプログラミングの要件は [アクティブ ドキュメント](../Topic/Active%20Documents.md)で説明します。  
  
 MFC は [CCmdTarget](../Topic/CCmdTarget%20Class.md)から [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md)、派生クラス、および [CDocObjectServerItem](../mfc/reference/cdocobjectserveritem-class.md)の [COleServerItem](../mfc/reference/coleserveritem-class.md)からの派生にアクティブ ドキュメントをサポートします。  MFC は [COleDocObjectItem](../Topic/COleDocObjectItem%20Class.md) クラス、[COleClientItem](../mfc/reference/coleclientitem-class.md)から派生を持つアクティブ ドキュメント コンテナーをサポートします。  
  
 `CDocObjectServer` は アクティブ ドキュメント インターフェイスをマップし、アクティブ文書を初期化し、アクティブにします。  MFC は、アクティブ ドキュメントのハンドルのコマンド ルーティングにマクロが用意されています。  アプリケーションでアクティブ ドキュメントを使用するには、StdAfx.h ファイルに AfxDocOb.h を含めます。  
  
 標準 MFC サーバーは独自の `COleServerItem`\-派生クラスの先頭にフックします。  MFC アプリケーション ウィザードは、アプリケーション サーバーの複合ドキュメント サポートを提供するために **Mini\-server** または **フル サーバー** のチェック ボックスをオンのこのクラスが生成されます。  また **Active ドキュメント サーバー\(A\)** のチェック ボックスをオンにすると、MFC アプリケーション ウィザードは `CDocObjectServerItem` から派生したクラスを生成します。  
  
 `COleDocObjectItem` クラスは OLE コンテナーがアクティブ ドキュメント コンテナーになるようにします。  MFC アプリケーション ウィザードの複合ドキュメント サポート ページで **Active ドキュメント コンテナー\(D\)** のチェック ボックスをオンにして、Active ドキュメント コンテナーを作成するには、MFC アプリケーション ウィザードを使用できます。  詳細については、「[Active ドキュメント コンテナー アプリケーションの作成](../mfc/creating-an-active-document-container-application.md)」を参照してください。  
  
## 参照  
 [Active ドキュメント コンテインメント](../mfc/active-document-containment.md)