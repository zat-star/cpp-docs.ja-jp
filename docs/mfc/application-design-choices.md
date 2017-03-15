---
title: "アプリケーションのデザイン上の検討事項 | Microsoft Docs"
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
  - "アプリケーションのデザイン [C++], デザイン目標"
  - "アプリケーションのデザイン [C++], インターネット アプリケーション"
  - "アプリケーション [MFC], インターネット"
  - "クライアント アプリケーション [C++], およびサーバー アプリケーション (インターネット上の)"
  - "デザイン"
  - "インターネット [C++], およびイントラネット"
  - "インターネット アプリケーション [C++], デザイン (アプリケーションを)"
  - "サーバー アプリケーション, およびクライアント アプリケーション (インターネット上の)"
ms.assetid: 9b96172c-b4d4-4c69-bfb2-226ce0de6d08
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# アプリケーションのデザイン上の検討事項
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、インターネットのプログラミング時に考慮する必要のあるデザイン上の問題について説明します。  
  
 この記事で説明されているトピックは次のとおりです。:  
  
-   [イントラネット ゾーンとインターネット](#_core_intranet_versus_internet)  
  
-   [クライアントとサーバー アプリケーション](#_core_client_or_server_application)  
  
-   [Web ページ: HTML の Active ドキュメント、ActiveX コントロール](#_core_the_web_page.3a_.html.2c_.activex_documents.2c_.activex_controls)  
  
-   [ブラウザーまたはスタンドアロン アプリケーション](#_core_browser_or_stand.2d.alone_application)  
  
-   [インターネットの COM](#_core_com_on_the_internet)  
  
-   [Client Data のダウンロード サービス](#_core_client_data_download_services)  
  
 プログラムを作成し、開始する準備ができている場合は [MFC アプリケーションの作成](../mfc/writing-mfc-applications.md)を参照してください。  
  
##  <a name="_core_intranet_versus_internet"></a> イントラネット ゾーンとインターネット  
 インターネットで実行する多くのアプリケーションは、ブラウザーとインターネット アクセスを持つユーザー全員がアクセスできるようになります。  ビジネスは、TCP\/IP プロトコルと Web ブラウザーを使用して全社的なネットワークであるイントラネットを実装しています。  イントラネットは全社的な情報の単純にアップグレードする中央のソースを提供します。  これには、ソフトウェアを、アンケートをアップグレードすると、カスタマー サポート提供し、表にし、情報提供のために使用できます。  次の表は、インターネットまたはイントラネットの機能を比較します。  
  
|インターネット|Intranet|  
|-------------|--------------|  
|低帯域|高帯域幅|  
|データとシステムの遅延セキュリティ|データとシステムへのアクセス|  
|コンテンツの最小コントロール|コンテンツの高いコントロール|  
  
##  <a name="_core_client_or_server_application"></a> クライアントとサーバー アプリケーション  
 アプリケーションはクライアント コンピューターまたはサーバー コンピューター上で実行されている可能性があります。  アプリケーションは、サーバーに格納し、クライアント コンピューターのインターネットおよび実行にダウンロードされる可能性があります。  MFC WinInet クラスはファイルをダウンロードするクライアント アプリケーションで使用されます。  MFC と非同期モニカー クラスは、ファイルおよびコントロール プロパティをダウンロードするために使用されます。  ActiveX コントロールと Active ドキュメントのクラスは、クライアント アプリケーションとサーバーからクライアントで実行するためにダウンロードされるアプリケーションで使用されます。  
  
##  <a name="_core_the_web_page.3a_.html.2c_.activex_documents.2c_.activex_controls"></a> Web ページ: HTML の Active ドキュメント、ActiveX コントロール  
 Microsoft は、Web ページのコンテンツを提供する複数の方法を提供します。  Web ページは、ActiveX コントロールなどの動的なコンテンツを提供するために標準 HTML または HTML 拡張機能を、オブジェクト タグなどの同期プリミティブを使用できます。  
  
 通常、Web ブラウザーを表示する HTML ページ。  Active ドキュメントは、COM 対応のブラウザーの簡単なポイントしますインターフェイスのアプリケーションのデータを表示できます。  Active ドキュメント サーバーはドキュメント、独自のメニューおよびツール バーでのクライアント領域の完全なフレームを表示できます。  
  
 作成した ActiveX コントロールはサーバーから非同期にダウンロードされ、Web ページで表示することができます。  サーバーに情報を送信する前にクライアント側の検証を実行するために VBScript などのスクリプト言語を使用できます。  
  
##  <a name="_core_browser_or_stand.2d.alone_application"></a> ブラウザーまたはスタンドアロン アプリケーション  
 ブラウザーで表示される HTML ページと Active ドキュメント サーバーに埋め込まれている ActiveX コントロールを作成することもできます。  Web サーバーの ISAPI アプリケーションを実行する要求を送信するためのボタンを含む HTML ページを作成できます。  ブラウザー アプリケーションを使用してせずにファイルをダウンロードし、ユーザーに対して情報を表示するには、インターネット プロトコルを使用するスタンドアロン アプリケーションを作成できます。  
  
##  <a name="_core_com_on_the_internet"></a> インターネットの COM  
 ActiveX コントロールと Active ドキュメントおよび非同期モニカーはすべて COM \(Component Object Model\) テクノロジを使用します。  
  
 ActiveX コントロールは、インターネット サイトでドキュメントとページに動的コンテンツを提供します。  COM ではアクティブ ドキュメントを使用して ActiveX コントロールと全フレームのドキュメントを作成できます。  
  
 非同期モニカーは、コントロールがデータをダウンロードするインクリメンタルまたは推移的な対策を含むインターネットの環境で、機能するようにするための機能を提供します。  コントロールは、データを非同期に同時に取得する可能性のある他のコントロールに使用する必要があります。  
  
##  <a name="_core_client_data_download_services"></a> Client Data のダウンロード サービス  
 クライアントにデータを渡すことができる 2 組の API は WinInet および非同期モニカーです。  HTML ページに .gif と .avi 大きなファイルと ActiveX コントロールがある場合、ユーザーが非同期にダウンロードして非同期モニカーを非同期的に使用するか、WinInet を使用することにより、応答性を向上させることができます。  
  
 インターネットの一般的なタスクは、データを転送することです。  既に Active テクノロジを ActiveX コントロールがある場合 \(たとえば、使用している場合\)、ダウンロードする漸進的に変換するデータに非同期モニカーを使用できます。  HTTP、FTP、Gopher などの共通のインターネット プロトコルを使用してデータを転送するために WinInet を使用できます。  メソッドはそれぞれ独立プロトコルを提供し、WinSock および TCP\/IP を使用して抽象レイヤーを提供します。  まだ [WinSock](../mfc/windows-sockets-in-mfc.md) を直接使用できます。  
  
 次の表は、インターネット間でデータを転送するために MFC を使用する方法を示します。  
  
|このプロトコルを使用します。|このような状況で|これらのクラスを使用します。|  
|--------------------|--------------|--------------------|  
|[非同期モニカーを使用してインターネットのダウンロード](../mfc/asynchronous-monikers-on-the-internet.md)|COM、ActiveX コントロール、インターネット プロトコルを使用して非同期の転送します。|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)、[CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)|  
|[WinInet](../mfc/win32-internet-extensions-wininet.md)|HTTP、FTP、Gopher のインターネット プロトコルです。  データは同期的または非同期的に転送することによって、キャッシュにシステムに格納されます。|[CInternetSession](../Topic/CInternetSession%20Class.md)、[CFtpFileFind](../Topic/CFtpFileFind%20Class.md)、[CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)など。|  
|[WinSock](../mfc/windows-sockets-in-mfc.md)|最大効率とコントロールです。  ソケットおよび TCP\/IP プロトコルを理解する必要があります。|[CSocket](../mfc/reference/csocket-class.md)、[CAsyncSocket](../Topic/CAsyncSocket%20Class.md)|  
  
## 参照  
 [MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)   
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)   
 [Win32 インターネット拡張機能 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット上の非同期モニカー](../mfc/asynchronous-monikers-on-the-internet.md)