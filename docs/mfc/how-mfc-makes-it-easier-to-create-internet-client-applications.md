---
title: "MFC を使ってインターネット クライアント アプリケーションを簡単に作成する方法 | Microsoft Docs"
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
  - "インターネット アプリケーション, MFC"
  - "インターネット クライアント アプリケーション, MFC"
  - "MFC, インターネット アプリケーション"
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# MFC を使ってインターネット クライアント アプリケーションを簡単に作成する方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Foundation Class が Win32 インターネット拡張機能 \(WinInet\) 関数をカプセル化する MFC プログラマに一般的なコンテキストを提供します。  MFC は [CStdioFile](../Topic/CStdioFile%20Class.md) クラスから派生される 3 種類のインターネット ファイル クラス \([CInternetFile](../mfc/reference/cinternetfile-class.md)、[CHttpFile](../Topic/CHttpFile%20Class.md)と [CGopherFile](../mfc/reference/cgopherfile-class.md)\) が用意されています。  だけでなく、これらのクラスは、ローカル ファイルに `CStdioFile` を使用し、これらのクラスには、以下の一貫した方法でローカル ファイルおよびインターネット ファイルを処理するプログラマに取得し、処理のインターネット データ親友を作成します。  
  
 MFC WinInet クラスは、インターネット経由で転送されるデータに `CStdioFile` と同じ機能を提供します。  これらのクラスは、高度なアプリケーション プログラミング インターフェイスに、HTTP、FTP、Gopher などのインターネット プロトコルを抽出し、すばやく簡単にパスをインターネット アプリケーションを認識することについて説明します。  たとえば、FTP サーバーに接続は、低レベルのいくつかの手順が必要になりますが、MFC の開発者としてのみ、その接続を作成するに `CInternetSession::GetFTPConnection` に 1 個の呼び出しを行う必要があります。  
  
 また、MFC WinInet クラスには次の利点があります。:  
  
-   バッファリングされた I\/O  
  
-   データのタイプ セーフ ハンドル  
  
-   多くの関数で既定のパラメーター  
  
-   共通のインターネット エラーの例外処理  
  
-   開いているハンドルと接続の自動クリーンアップ  
  
## 参照  
 [Win32 インターネット拡張機能 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [WinInet を使ってインターネット クライアント アプリケーションを簡単に作成する方法](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)