---
title: "典型的な HTTP クライアント アプリケーションの作成手順 | Microsoft Docs"
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
  - "アプリケーション [MFC], HTTP クライアント"
  - "クライアント アプリケーション [C++], HTTP"
  - "HTTP クライアント アプリケーション"
  - "インターネット アプリケーション [C++], HTTP クライアント アプリケーション"
  - "インターネット クライアント アプリケーション [C++], HTTP テーブル"
  - "WinInet クラス, HTTP"
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 典型的な HTTP クライアント アプリケーションの作成手順
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の表は、一般的な HTTP のクライアント アプリケーションで実行する可能性のある手順を示しています。:  
  
|対象|、アクション|効果|  
|--------|------------|--------|  
|HTTP セッションを開始します。|[CInternetSession](../Topic/CInternetSession%20Class.md) オブジェクトを作成します。|WinInet を初期化し、サーバーに接続します。|  
|HTTP サーバーに接続します。|[CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md)を使用します。|[CHttpConnection](../mfc/reference/chttpconnection-class.md) オブジェクトを返します。|  
|HTTP 要求を開きます。|[CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md)を使用します。|[CHttpFile](../Topic/CHttpFile%20Class.md) オブジェクトを返します。|  
|HTTP 要求を送信します。|[CHttpFile::AddRequestHeaders](../Topic/CHttpFile::AddRequestHeaders.md) と [CHttpFile::SendRequest](../Topic/CHttpFile::SendRequest.md)を使用します。|ファイルを検索します。  ファイルが存在しない場合は false を返します。|  
|ファイルから読み込みます。|[CHttpFile](../Topic/CHttpFile%20Class.md)を使用します。|指定したバッファーを使用して指定したバイト数を読み取ります。|  
|例外を処理する|[CInternetException](../mfc/reference/cinternetexception-class.md) クラスを使用します。|すべての一般的なインターネットの種類の例外を処理します。|  
|HTTP セッションを終了します。|[CInternetSession](../Topic/CInternetSession%20Class.md) オブジェクトを破棄します。|自動的に開くファイル ハンドルと接続をクリーンアップします。|  
  
## 参照  
 [Win32 インターネット拡張機能 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント クラスの必要条件](../Topic/Prerequisites%20for%20Internet%20Client%20Classes.md)   
 [MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)