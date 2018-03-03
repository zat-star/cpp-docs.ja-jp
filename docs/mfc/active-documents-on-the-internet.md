---
title: "インターネット上の active ドキュメント |Microsoft ドキュメント"
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
- active documents [MFC], creating
- application wizards [MFC], active documents
- active documents [MFC], programming steps
- application wizards [MFC]
- active documents [MFC], using application wizards
ms.assetid: a46bd8a0-e27a-4116-b1bf-dacdb7ae78d1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0980f048b9be411308b159dea0ceaa71f8eee563
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="active-documents-on-the-internet"></a>インターネット上の Active ドキュメント
アクティブなドキュメントは、従来の埋め込みオブジェクトの拡張機能を提供します。 アクティブなドキュメントは、マルチページ可能性があり、全体のクライアント領域に表示されます。 従来のメニューのネゴシエーションを実行し、インプレースだけでなく、サーバー アプリケーションで開いているウィンドウで編集できます。 斜線の枠で囲まれた小さな四角形として表示する、代わりに、アクティブなドキュメントは、フル フレームと常に、インプレース アクティブです。  
  
 アクティブなドキュメントは、Microsoft Office バインダー、Excel、Word のようなさまざまなドキュメントの種類から成る複合ドキュメントを作成する方法を提供するようにコンテナーで表示でき、それぞれが、カスタムのドキュメントの種類がフル フレームを編集します。 アクティブなドキュメントは、Active ドキュメント コンテナーである Microsoft Internet Explorer などのブラウザーで表示できます。  
  
 **アクティブなドキュメントの利点があります。**  
  
-   ドキュメントを表示できる、全体のクライアント ウィンドウで、完全なフレーム。  
  
-   ドキュメントは、別のアプリケーション ウィンドウで開くことができます。  
  
     開くには、ドキュメントのヘルパー アプリケーションは、クライアント上に存在する必要があります。 またはアプリケーションを実行する前に個別にダウンロードします。 (Word、PowerPoint、および Excel のドキュメントのビューアーを提供) の限られた機能を提供するビューアーを書き込むことがあります。 アプリケーションの完全バージョンには、編集のサポートを提供できます。  
  
-   ドキュメントは、常に、インプレース アクティブです。  
  
-   コンテナーから呼び出されたメニュー コマンドは、ドキュメントにルーティングできます。  
  
-   ドキュメントは、Web ブラウザーで表示できます。 これは、ドキュメントやその他の Web ページのシームレスな統合を提供します。  
  
     ユーザーは、HTML Web ページで、Excel スプレッドシート、しを参照して、アクティブな文書の MFC を使用して記述したドキュメントをサポートするか、できます。 ユーザーは、メニューおよび HTML ページ、Excel、およびアプリケーションのドキュメントのビューの間でシームレスにブラウザーのスイッチと、使い慣れた Web インターフェイスを使用して移動できます。  
  
-   すべてのアプリケーションは、共通のフレームに表示されます。  
  
## <a name="requirements-for-active-documents"></a>アクティブ ドキュメントの要件  
 次の表にリストされたインターフェイスには、埋め込みサーバーに既に必要なインターフェイスおよびアクティブなドキュメントに固有のいくつかの新しいインターフェイスが含まれます。 MFC でこれらのインターフェイスのほとんどの既定の実装を提供する、 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)クラスです。  
  
|ドキュメントをしています.|これらのインターフェイスを実装します。|  
|-------------------------|---------------------------------|  
|そのストレージ メカニズムとして複合ファイルを使用します。|`IPersistStorage`。|  
|アクティブなドキュメント、ファイルから作成などの基本的な埋め込み機能をサポートしています。|`IPersistFile`、`IOleObject`、および `IDataObject`。|  
|サポートする、インプレース アクティブ化します。|`IOleInPlaceObject`および`IOleInPlaceActiveObject`(コンテナーを使用して`IOleInPlaceSite`と**IOleInPlaceFrame**インターフェイス)。|  
|これらの新しいインターフェイスを伴う作業中の文書の拡張機能をサポートしています。 一部のインターフェイスはオプションです。|`IOleDocument`、`IOleDocumentView`、`IOleCommandTarget`、および `IPrint`。|  
  
 MFC には、アクティブなドキュメントへの既存の埋め込みサーバー サポートを拡張するためのサポートが用意されています。  
  
## <a name="add-active-document-support-to-a-new-application"></a>アクティブ ドキュメントのサポートを新しいアプリケーションに追加します。  
 アクティブなドキュメントをサポートする新しいアプリケーションを作成する: MFC アプリケーション ウィザードでの**複合ドキュメント サポート**ページで、「複合ドキュメント サポート」では次のように選択します**フル サーバー**または。**コンテナー/フル サーバー**、および「その他のオプションを選択」チェック ボックスをオン**Active ドキュメント サーバー**です。  
  
##  <a name="_core_convert_an_existing_mfc_in.2d.process_server_to_an_activex_document_server"></a>Active ドキュメント サーバーへの既存の MFC インプロセス サーバーを変換します。  
 場合は、アプリケーション バージョン 4.2 より前のバージョンの Visual C で作成された、インプロセス サーバーが既に次のクラスに変更することによりアクティブ ドキュメントのサポートを追加できます。  
  
|クラス型|前の派生元|派生する変更|  
|----------------|---------------------------|---------------------------|  
|埋め込み先フレーム|`COleIPFrameWnd`|**COleDocIPFrameWnd**|  
|アイテム|`COleServerItem`|`CDocObjectServerItem`|  
  
 また、レジストリで、情報を入力する方法を変更し、その他のいくつかの変更を加えます。 アプリケーション コンポーネントの COM サポートがあるない場合、は、アプリケーションのウィザードを実行し、既存のアプリケーションと COM コンポーネント固有のコードを統合することで、サーバーのサポートを追加できます。  
  
## <a name="see-also"></a>参照  
 [MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)   
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)

