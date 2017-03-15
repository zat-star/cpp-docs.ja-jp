---
title: "WinInet を使ってインターネット クライアント アプリケーションを簡単に作成する方法 | Microsoft Docs"
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
  - "Windows ソケット [C++], および WinInet"
  - "WinInet クラス, インターネット クライアント アプリケーション"
  - "WinInet クラス, および WinSock"
ms.assetid: dc0f9f47-3184-4e7a-8074-2c63e0359885
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# WinInet を使ってインターネット クライアント アプリケーションを簡単に作成する方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Win32 インターネット拡張機能 \(WinInet は、FTP、HTTP、Gopher など、共通のインターネット プロトコルへのアクセスを提供します。  WinInet を使用すると、プログラミングの上位レベルにある特定のインターネット プロトコルの Winsock、TCP\/IP、または詳細を取扱わないでインターネット クライアント アプリケーションを記述できます。  WinInet を使い慣れた Win32 API インターフェイスを 3 つすべてのプロトコルに一貫した一連の関数を提供します。  この一貫性は基になるプロトコルが変更される変更を行う必要があるコード変更を最小限に抑えることができます \(たとえば、FTP から HTTP など\)。  
  
 Visual C\+\+ では、次の 2 通りの方法が WinInet を使用できます。  直接参照します \(詳細については、" [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] の OLE ドキュメントを\) Win32 インターネット関数を呼び出すことができます。また、[MFC WinInet クラス](../mfc/mfc-classes-for-creating-internet-client-applications.md)で WinInet を使用できます。  
  
 **WinInet を使用する:**  
  
-   ダウンロード HTML ページ。  
  
     HTTP はサーバーからクライアント ブラウザーに HTML ページを転送するために使用されるプロトコルです。  
  
-   アップロードまたはファイルをダウンロードまたはディレクトリの一覧を取得する FTP Web 要求。  
  
     一般的な要求はファイルをダウンロードできる匿名ログオンです。  
  
-   インターネット リソースへのアクセスについて Gopher のメニュー システムを使用します。  
  
     メニュー項目は、検索できるそのほかのメニュー、被 ISAM データベース ニュースグループ、またはファイルを含む複数の型でもかまいません。  
  
 3 つすべてのプロトコルでは、接続を確立し、サーバーに要求を、閉じる接続します。  
  
 **MFC WinInet クラスを簡単に実現:**  
  
-   読み取りがハード ディスクからファイルに、HTTP、FTP、Gopher サーバーから情報を簡単に参照します。  
  
-   Winsock または TCP\/IP にプログラムせずに、HTTP、FTP、Gopher プロトコルを直接使用します。  
  
     Win32 インターネット関数を使用する開発者は、TCP\/IP または Windows ソケットを十分に理解しておく必要はありません。  まだ Winsock および TCP\/IP プロトコルを使用してソケット レベルに直接プログラミングできますが、インターネットを介して HTTP、FTP、Gopher などのプロトコルにアクセスするために MFC WinInet クラスを使用する方が簡単です。  多くの一般的な操作には、開発者が使用する特定のプロトコルの詳細を意識する必要はありません。  
  
 インターネット上の他のコンピューターへのクライアントとしてコンピューターから実行できるさまざまな処理に長時間を要する場合があります。  これらの処理速度は、通常、ネットワーク接続の速度によって制限され、処理の別のネットワーク トラフィックと複雑さによって影響を受けることがあります。  たとえば、リモート FTP サーバーに接続は、アドレスを見つけるために、コンピューターが最初にサーバーの名前を検索する必要があります。  アプリケーションは、そのアドレスでサーバーに接続しようとします。  接続を開くと、ファイルを取得するために、実際に接続を使用するには、リモート コンピューターとサーバーは、ファイル転送プロトコル \(FTP の対話を開始します。  
  
## 参照  
 [Win32 インターネット拡張機能 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [MFC を使ってインターネット クライアント アプリケーションを簡単に作成する方法](../mfc/how-mfc-makes-it-easier-to-create-internet-client-applications.md)