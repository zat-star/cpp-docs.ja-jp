---
title: "インターネット上の Active テクノロジ | Microsoft Docs"
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
  - "インターネット アプリケーション, Active テクノロジ"
ms.assetid: 6f782aa1-5c2f-47a2-9e63-ddd0829d5a08
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# インターネット上の Active テクノロジ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Active テクノロジは、世界的なインターネット用、またはイントラネットと呼ばれる企業内ネットワーク用に、動的コンテンツとアプリケーションを作成するためのオープン アーキテクチャです。  Microsoft がインターネットのプログラミングのために提供する主な技術を以下に紹介します。  
  
## ActiveX コントロール  
 ActiveX コントロールは、Web ページまたは ActiveX コントロールのコンテナー アプリケーション内に挿入できるオブジェクトで、OLE コントロールです。  ボタン、株価ティッカー、グラフ コントロールなどが該当します。  詳細については、「[インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)」を参照してください。  
  
## Active ドキュメント  
 Active ドキュメントは、Web ブラウザーまたはドキュメント ビューアーに表示できます。  従来の埋め込みオブジェクトは、単一のページに限定され、ドキュメント内に埋め込まれて表示されました。  Active テクノロジでは、Active ドキュメントはクライアント領域のウィンドウ全体に全画面表示できます。  詳細については、「[インターネット上の Active ドキュメント](../Topic/Active%20Documents%20on%20the%20Internet.md)」を参照してください。  
  
## インターネットでのデータのダウンロード サービス  
 インターネットでは、HTTP、FTP、Gopher などの一般的なプロトコルを使用してデータをダウンロードできます。  MFC WinInet クラスを使用すると、TCP\/IP および WinSock プロトコルを抽象化し、HTTP、FTP、Gopher の各プロトコルでデータを簡単に転送できます。  また、MFC 非同期モニカー クラスを使用すると、その他の処理を停止することなくファイルをダウンロードできるため、大きなオブジェクトを非同期的に描画できます。  詳細については、「[Win32 インターネット拡張機能 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)」を参照してください。  
  
## アクティブ スクリプト  
 VBScript などのスクリプト言語を使用すると、Web ページにコントロールを接続して、操作機能を追加できます。  スクリプトは、サーバーからクライアントに処理を移動します。  たとえば、クライアントでフォームのエントリの妥当性を検討してから、それをサーバーに転送できます。  
  
## HTML 拡張機能  
 コントロールとスクリプトをサポートするために、オブジェクト タグなどの HTML 拡張機能が追加されました。  
  
## 参照  
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)   
 [インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)   
 [インターネット上の Active ドキュメント](../Topic/Active%20Documents%20on%20the%20Internet.md)   
 [Win32 インターネット拡張機能 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)