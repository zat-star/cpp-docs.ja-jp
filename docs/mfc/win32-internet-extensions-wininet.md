---
title: "Win32 インターネット拡張機能 (WinInet) | Microsoft Docs"
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
  - "クライアント アプリケーション, Win32 のインターネット"
  - "インターネット アプリケーション, Win32 のインターネット拡張機能"
  - "インターネット クライアント アプリケーション, インターネット クライアント アプリケーションの概要"
  - "WinInet クラス, WinInet クラスの概要"
ms.assetid: f8c80f0b-ce14-4f0d-a3cf-4f7d8c5cca59
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Win32 インターネット拡張機能 (WinInet)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

インターネット クライアント アプリケーションはネットワーク データ ソース \(サーバー\) から gopher、FTP、HTTP などのインターネット プロトコルを使用して情報にアクセスするプログラムです。  インターネット クライアント アプリケーションは、天気図、株価、新聞のヘッダーの語などのデータを取得するには、サーバーにアクセスできない場合があります。  インターネット クライアントは、外部ネットワーク \(インターネット\) または内部ネットワークを通じてサーバーにできます \(検索イントラネット アクセスと呼ばれます\)。  
  
 MFC は、Win32 インターネット拡張、またはインターネット クライアント アプリケーションを作成するための WinInet\) が含まれます。  MFC は、一連の標準使いやすいクラスのインターネット拡張機能をカプセル化します。  Win32 関数を直接呼び出すか、MFC WinInet クラスを使用して WinInet のクライアント アプリケーションを作成できます。  
  
 Microsoft Win32 関数のインターネット \(WinInet\) は、任意のアプリケーションの整数部インターネットにするために役立ちます。  WININET.DLL に含まれる新しい関数は HTTP \(ハイパーテキストの転送プロトコル\)、ファイル転送プロトコル \(FTP\)、および Gopher を使用してインターネットにアクセスすることが簡単になります。  
  
 次のトピックでは、インターネット クライアント アプリケーションを作成するプロセスについて説明します。:  
  
-   [WinInet をインターネット クライアント アプリケーションを作成するように簡単にできます。](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)  
  
-   [MFC がインターネット クライアント アプリケーションを作成するように簡単にできます。](../mfc/how-mfc-makes-it-easier-to-create-internet-client-applications.md)  
  
-   [インターネット クライアント アプリケーションを作成するための MFC クラス](../mfc/mfc-classes-for-creating-internet-client-applications.md)  
  
-   [インターネット クライアント クラスの必須コンポーネント](../Topic/Prerequisites%20for%20Internet%20Client%20Classes.md)  
  
-   [MFC WinInet クラスを使用してインターネット クライアント アプリケーションを作成できます。](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)  
  
 次のトピックでは、WinInet 一般的なタスクを実行するための手順を提供し、T:  
  
-   [一般的なインターネット クライアント アプリケーションの手順](../Topic/Steps%20in%20a%20Typical%20Internet%20Client%20Application.md)  
  
-   [通常、FTP のクライアント アプリケーションの手順](../mfc/steps-in-a-typical-ftp-client-application.md)  
  
-   [ファイルを削除する一般的な FTP のクライアント アプリケーションの手順](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)  
  
-   [一般的な Gopher のクライアント アプリケーションの手順](../mfc/steps-in-a-typical-gopher-client-application.md)  
  
-   [一般的な HTTP のクライアント アプリケーションの手順](../mfc/steps-in-a-typical-http-client-application.md)  
  
## 参照  
 [MFC Internet Programming \(NIB\)](http://msdn.microsoft.com/ja-jp/0f7a1f3a-385b-4d56-a55b-0d766840c58a)   
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)   
 [WinInet の基礎](../mfc/wininet-basics.md)