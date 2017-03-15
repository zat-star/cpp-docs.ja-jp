---
title: "ファイルを削除する典型的な FTP クライアント アプリケーションの作成手順 | Microsoft Docs"
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
  - "FTP (ファイル転送プロトコル), クライアント アプリケーション"
  - "インターネット アプリケーション, FTP クライアント アプリケーション"
  - "インターネット クライアント アプリケーション, FTP 削除"
  - "WinInet クラス, FTP"
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ファイルを削除する典型的な FTP クライアント アプリケーションの作成手順
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の表は、ファイルを削除する一般的な FTP のクライアント アプリケーションで実行する可能性のある手順を示します。  
  
|対象|、アクション|効果|  
|--------|------------|--------|  
|FTP セッションを開始します。|[CInternetSession](../Topic/CInternetSession%20Class.md) オブジェクトを作成します。|WinInet を初期化し、サーバーに接続します。|  
|FTP サーバーに接続します。|[CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md)を使用します。|["](../mfc/reference/cftpconnection-class.md) オブジェクトを返します。|  
|FTP サーバー上の適切なディレクトリにあることを確認します。|[CFtpConnection::GetCurrentDirectory](../Topic/CFtpConnection::GetCurrentDirectory.md) または [CFtpConnection::GetCurrentDirectoryAsURL](../Topic/CFtpConnection::GetCurrentDirectoryAsURL.md)を使用します。|選択したメンバー関数により、サーバー上で現在接続しているディレクトリの名前または URL を返します。|  
|サーバーの新しい FTP ディレクトリに変更します。|[CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md)を使用します。|サーバーに現在接続しているディレクトリを変更します。|  
|FTP ディレクトリの最初のファイルを検索します。|[CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md)を使用します。|最初のファイルを検索します。  ファイルが存在しない場合は false を返します。|  
|FTP ディレクトリのファイルを検索します。|[CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md)を使用します。|次のファイルを検索します。  ファイルが存在しない場合は false を返します。|  
|**FindFile** または `FindNextFile`で見つかったファイルを削除します。|**FindFile** または `FindNextFile`で返すファイル名を使用して [CFtpConnection::Remove](../Topic/CFtpConnection::Remove.md)を使用します。|読み取りまたは書き込みのサーバーのファイルを削除します。|  
|例外を処理する|[CInternetException](../mfc/reference/cinternetexception-class.md) クラスを使用します。|すべての一般的なインターネットの種類の例外を処理します。|  
|FTP セッションを終了します。|[CInternetSession](../Topic/CInternetSession%20Class.md) オブジェクトを破棄します。|自動的に開くファイル ハンドルと接続をクリーンアップします。|  
  
## 参照  
 [Win32 インターネット拡張機能 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント クラスの必要条件](../Topic/Prerequisites%20for%20Internet%20Client%20Classes.md)   
 [MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)