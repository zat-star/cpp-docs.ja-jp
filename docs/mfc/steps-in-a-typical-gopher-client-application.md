---
title: "典型的な Gopher クライアント アプリケーションの作成手順 | Microsoft Docs"
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
  - "Gopher クライアント アプリケーション"
  - "インターネット アプリケーション, gopher クライアント アプリケーション"
  - "インターネット クライアント アプリケーション, gopher テーブル"
  - "WinInet クラス, Gopher"
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 典型的な Gopher クライアント アプリケーションの作成手順
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の表は、一般的な Gopher のクライアント アプリケーションで実行する可能性のある手順を示します。  
  
|対象|、アクション|効果|  
|--------|------------|--------|  
|gopher セッションを開始します。|[CInternetSession](../Topic/CInternetSession%20Class.md) オブジェクトを作成します。|WinInet を初期化し、サーバーに接続します。|  
|Gopher サーバーに接続します。|[CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md)を使用します。|[CGopherConnection](../mfc/reference/cgopherconnection-class.md) オブジェクトを返します。|  
|gopher の最初のリソースを探します。|[CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md)を使用します。|最初のファイルを検索します。  ファイルが存在しない場合は false を返します。|  
|gopher の次のリソースを見つけます。|[CGopherFileFind::FindNextFile](../Topic/CGopherFileFind::FindNextFile.md)を使用します。|次のファイルを検索します。  ファイルが存在しない場合は false を返します。|  
|読み取ることの **FindFile** または `FindNextFile` で見つかったファイルを開きます。|[CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md)を使用して gopher ロケーターを取得します。  [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md)を使用します。|Locator 属性で指定されたファイルを開きます。  `OpenFile` は [CGopherFile](../mfc/reference/cgopherfile-class.md) オブジェクトを返します。|  
|指定した gopher ロケーターを使用してファイルを開きます。|[CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md)を使用して gopher ロケーターを作成します。  [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md)を使用します。|Locator 属性で指定されたファイルを開きます。  `OpenFile` は [CGopherFile](../mfc/reference/cgopherfile-class.md) オブジェクトを返します。|  
|ファイルから読み込みます。|[CGopherFile](../mfc/reference/cgopherfile-class.md)を使用します。|指定したバッファーを使用して指定したバイト数を読み取ります。|  
|例外を処理する|[CInternetException](../mfc/reference/cinternetexception-class.md) クラスを使用します。|すべての一般的なインターネットの種類の例外を処理します。|  
|gopher セッションを終了します。|[CInternetSession](../Topic/CInternetSession%20Class.md) オブジェクトを破棄します。|自動的に開くファイル ハンドルと接続をクリーンアップします。|  
  
## 参照  
 [Win32 インターネット拡張機能 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント クラスの必要条件](../Topic/Prerequisites%20for%20Internet%20Client%20Classes.md)   
 [MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)