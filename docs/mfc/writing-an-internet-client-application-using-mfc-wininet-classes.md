---
title: "MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法 | Microsoft Docs"
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
  - "インターネット アプリケーション, クライアント アプリケーション"
  - "インターネット アプリケーション, WinInet"
  - "インターネット クライアント アプリケーション"
  - "インターネット クライアント アプリケーション, 書き込み"
  - "MFC, インターネット アプリケーション"
  - "WinInet クラス, プログラミング"
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

すべてのインターネット クライアント アプリケーションは、インターネット セッションです。  MFC クラスは [CInternetSession](../Topic/CInternetSession%20Class.md)オブジェクトとしてインターネット セッションを実装します。  このクラスを使用して、1 回の複数の同時インターネット セッションを作成できます。  
  
 サーバーと通信するには、[CInternetConnection](../Topic/CInternetConnection%20Class.md) オブジェクトを必要とし、`CInternetSession`。  [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md)、[CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md)、または [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md)を使用して `CInternetConnection` を作成できます。  これらの呼び出しでは、プロトコル タイプに固有です。  この呼び出しによって、読み取りまたは書き込みのサーバー上でファイルが開かれます。  データの読み取りや書き込み場合は個々のステップとしてファイルを開く必要があります。  
  
 ほとんどのインターネット セッションの場合、`CInternetSession` のオブジェクトは必要な取得を行います [CInternetFile](../mfc/reference/cinternetfile-class.md) オブジェクトと:  
  
-   インターネット セッションで、[CInternetSession](../Topic/CInternetSession%20Class.md)のインスタンスを作成する必要があります。  
  
-   インターネット セッションでデータの読み取りまたは書き込み、`CInternetFile` のインスタンスが \(またはサブクラス、[CHttpFile](../Topic/CHttpFile%20Class.md) または [CGopherFile](../mfc/reference/cgopherfile-class.md)\) を作成します。  データを読み込む最も簡単な方法は、[CInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md)を呼び出します。  この関数は、提供する汎用 Resource Locator \(URL\) を解析して URL で指定されているサーバーに接続し、`CInternetFile` の読み取り専用オブジェクトを返します。  `CInternetSession::OpenURL` は 1 個のプロトコルの種類— FTP、HTTP、Gopher URL の同じ呼び出し作業に固有ではありません。  `CInternetSession::OpenURL` は ローカル ファイル \(`CInternetFile`の代わりに `CStdioFile` を返します\)。  
  
-   インターネット セッションを読み取るか、記述するデータは、FTP ディレクトリに、ファイルの削除などのタスクを、`CInternetFile`のインスタンスを作成する必要がない場合もありますが、実行します。  
  
 `CInternetFile` オブジェクトを作成するには 2 とおりの方法があります。:  
  
-   サーバー接続を確立するために `CInternetSession::OpenURL` を使用して `OpenURL` の呼び出しは `CStdioFile`を返します。  
  
-   サーバー接続を確立するために使用 **CInternetSession::GetFtpConnection**、`GetGopherConnection`、または `GetHttpConnection` がそれぞれ `CFtpConnection::OpenFile`、`CGopherConnection::OpenFile`、または **CHttpConnection::OpenRequest,** を呼び出す必要がある `CInternetFile`、`CGopherFile`、または `CHttpFile`を返すために、各。  
  
 インターネット クライアント アプリケーションの実装の手順は **OpenURL** に基づいて一般的なインターネット クライアントまたは **GetConnection** 関数の 1 種類を使用するプロトコル固有のクライアントを作成するかどうかによって異なります。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [以前に FTP、HTTP、Gopher を包括的に使用するインターネット クライアント アプリケーションを作成できます。](../Topic/Steps%20in%20a%20Typical%20Internet%20Client%20Application.md)  
  
-   [以前にファイルを開く FTP のクライアント アプリケーションを作成できます。](../mfc/steps-in-a-typical-ftp-client-application.md)  
  
-   [以前にないファイルを開いて、書きましたりファイルの削除などの操作を実行する FTP ディレクトリのクライアント アプリケーションまたは。](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)  
  
-   [以前に Gopher のクライアント アプリケーションを作成できます。](../mfc/steps-in-a-typical-gopher-client-application.md)  
  
-   [以前に HTTP クライアント アプリケーションを作成できます。](../mfc/steps-in-a-typical-http-client-application.md)  
  
## 参照  
 [Win32 インターネット拡張機能 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント アプリケーションの作成用の MFC クラス](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [インターネット クライアント クラスの必要条件](../Topic/Prerequisites%20for%20Internet%20Client%20Classes.md)