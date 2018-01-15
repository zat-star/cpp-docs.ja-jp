---
title: "サーバー: サーバーの実装 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- servers, implementing
- OLE server applications [MFC], implementing OLE servers
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 148a3da3c904f5c314c75fb71deede3c92163cc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="servers-implementing-a-server"></a>サーバー : サーバーの実装
この記事では、MFC アプリケーション ウィザード ビジュアル編集サーバー アプリケーション用に作成するコードについて説明します。 アプリケーションのウィザードを使用していない場合、この記事には、サーバー アプリケーションを実装するコードを記述する必要があります、領域が一覧表示します。  
  
 新しいサーバー アプリケーションを作成するアプリケーションのウィザードを使用している場合は、大量のサーバーに固有のコードを提供します。 ビジュアル編集サーバーの機能を追加する、既存のアプリケーションには、必要なサーバー コードの残りの部分を追加する前に、アプリケーションのウィザードが提供したコードを複製する必要があります。  
  
 アプリケーション ウィザードで提供されるサーバー コードは、複数のカテゴリに分類されます。  
  
-   サーバーのリソースを定義します。  
  
    -   メニュー リソースをサーバーが、独自のウィンドウで埋め込みアイテムを編集するときに使用します。  
  
    -   メニューとツールバーのリソースを場所に、サーバーがアクティブな場合に使用します。  
  
     これらのリソースの詳細については、次を参照してください。[メニューとリソース: サーバーの変更点](../mfc/menus-and-resources-server-additions.md)です。  
  
-   派生した item クラスを定義する`COleServerItem`です。 サーバーのアイテムの詳細については、次を参照してください。[サーバー: サーバー アイテム](../mfc/servers-server-items.md)です。  
  
-   ドキュメント クラスの基本クラスを変更する`COleServerDoc`です。 詳細については、次を参照してください。[サーバー: サーバー ドキュメントの実装](../mfc/servers-implementing-server-documents.md)です。  
  
-   派生したフレーム ウィンドウ クラスを定義する`COleIPFrameWnd`です。 詳細については、次を参照してください。[サーバー: 埋め込み先フレーム ウィンドウの実装](../mfc/servers-implementing-in-place-frame-windows.md)です。  
  
-   Windows レジストリ データベースに、サーバー アプリケーションのエントリを作成して、OLE システムへのサーバーの新しいインスタンスを登録します。 このトピックの情報については、次を参照してください。[登録](../mfc/registration.md)です。  
  
-   初期化し、サーバー アプリケーションを起動します。 このトピックの情報については、次を参照してください。[登録](../mfc/registration.md)です。  
  
 詳細については、次を参照してください。 [COleServerItem](../mfc/reference/coleserveritem-class.md)、 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)、および[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)で、*クラス ライブラリ リファレンス*です。  
  
## <a name="see-also"></a>参照  
 [サーバー](../mfc/servers.md)   
 [コンテナー](../mfc/containers.md)   
 [メニューとリソース (OLE)](../mfc/menus-and-resources-ole.md)   
 [登録](../mfc/registration.md)

