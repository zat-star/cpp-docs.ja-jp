---
title: "典型的な FTP クライアント アプリケーションの作成手順 | Microsoft Docs"
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
  - "FTP (ファイル転送プロトコル)"
  - "FTP (ファイル転送プロトコル), クライアント アプリケーション"
  - "インターネット アプリケーション, FTP クライアント アプリケーション"
  - "インターネット クライアント アプリケーション, FTP テーブル"
  - "WinInet クラス, FTP"
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 典型的な FTP クライアント アプリケーションの作成手順
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

通常、FTP のクライアント アプリケーションは [CInternetSession](../Topic/CInternetSession%20Class.md) と ["](../mfc/reference/cftpconnection-class.md) オブジェクトを作成します。  これらの MFC WinInet クラスが実際にプロキシ型の設定を制御しないでください; IIS は。  
  
 また、これらのサポート技術情報の文書を参照してください。:  
  
-   " HOWTO: WinInet API \(記事 ID を使用して CERN ベースのプロキシの FTP: Q166961\)  
  
-   サンプル: CERN ベースのパスワード保護されたなプロキシ \(記事 ID の FTP: Q216214\)  
  
-   インターネット サービス マネージャーは、インストールされたプロキシ サービス \(記事 ID を表示できない: Q216802\)  
  
 次の表は、一般的な FTP のクライアント アプリケーションで実行する可能性のある手順を示します。  
  
|対象|、アクション|効果|  
|--------|------------|--------|  
|FTP セッションを開始します。|[CInternetSession](../Topic/CInternetSession%20Class.md) オブジェクトを作成します。|WinInet を初期化し、サーバーに接続します。|  
|FTP サーバーに接続します。|[CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md)を使用します。|["](../mfc/reference/cftpconnection-class.md) オブジェクトを返します。|  
|サーバーの新しい FTP ディレクトリに変更します。|[CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md)を使用します。|サーバーに現在接続しているディレクトリを変更します。|  
|FTP ディレクトリの最初のファイルを検索します。|[CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md)を使用します。|最初のファイルを検索します。  ファイルが存在しない場合は false を返します。|  
|FTP ディレクトリのファイルを検索します。|[CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md)を使用します。|次のファイルを検索します。  ファイルが存在しない場合は false を返します。|  
|読み取りまたは書き込みの **FindFile** または `FindNextFile` で見つかったファイルを開きます。|[FindFile](../Topic/CFtpFileFind::FindFile.md) または [FindNextFile](../Topic/CFtpFileFind::FindNextFile.md)で返すファイル名を使用して [CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md)を使用します。|読み取りまたは書き込み用のサーバー上でファイルを開きます。  [CInternetFile](../mfc/reference/cinternetfile-class.md) オブジェクトを返します。|  
|から読み取ったり、またはファイルに書き込みます。|[CInternetFile::Read](../Topic/CInternetFile::Read.md) または [CInternetFile::Write](../Topic/CInternetFile::Write.md)を使用します。|指定したバッファーを使用して、指定したバイト数を、読み取りまたは書き込みを行います。|  
|例外を処理する|[CInternetException](../mfc/reference/cinternetexception-class.md) クラスを使用します。|すべての一般的なインターネットの種類の例外を処理します。|  
|FTP セッションを終了します。|[CInternetSession](../Topic/CInternetSession%20Class.md) オブジェクトを破棄します。|自動的に開くファイル ハンドルと接続をクリーンアップします。|  
  
## 参照  
 [Win32 インターネット拡張機能 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント クラスの必要条件](../Topic/Prerequisites%20for%20Internet%20Client%20Classes.md)   
 [MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)