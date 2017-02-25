---
title: "MFC インターネット プログラミングの作業 | Microsoft Docs"
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
  - "インターネット アプリケーション, 最初の段階"
  - "インターネット アプリケーション, はじめに"
ms.assetid: 6377e9b8-07c4-4380-b63b-05f5a9061313
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# MFC インターネット プログラミングの作業
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、アプリケーションにインターネットのサポートを追加するための詳しい手順について説明します。  具体的には、MFC クラスを使って既存のアプリケーションをインターネット対応にする方法、および既存の  COM コンポーネントにアクティブ ドキュメントのサポートを追加する方法を紹介します。  たとえば、現時点の株価、J リーグの試合の結果、南極の温度などを示すドキュメントを作成できます。  Microsoft は、これらをインターネット上で実現するためのさまざまな技術を提供しています。  
  
 Active テクノロジには、従来の OLE コントロールに相当する ActiveX コントロールと Active ドキュメント、インターネットを通じてファイルを簡単に取得して保存するための WinInet、データを効率的にダウンロードするための非同期モニカーなどがあります。  Visual C\+\+ には、起動アプリケーションを使用して、すばやくプログラミングを始めるための便利なウィザードが用意されています。  各技術の詳細については、「[MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)」および「[MFC COM](../mfc/mfc-com.md)」を参照してください。  
  
 ファイルの操作を FTP で行いたいが、WinSock やネットワーク プログラミング プロトコルについては詳しくない、という場合があります。  WinInet クラスには、これらのプロトコルがカプセル化されています。WinInet クラスに用意されている簡単な関数を使用すると、HTTP、FTP、および Gopher でファイルをダウンロードするインターネット クライアント アプリケーションを作成できます。  WinInet を使用すると、自分のハード ディスク ドライブのフォルダーだけでなく、世界中のフォルダーを検索できます。  また、データの種類にかかわらずさまざまな種類のデータを集めることができ、そのデータを統合インターフェイスを通じてユーザーに提供できます。  
  
 大量のデータをダウンロードすることもできます。  非同期モニカーには、大きなオブジェクトを少しずつ描画するための COM \(Component Object Model\) ソリューションが用意されています。  WinInet を非同期的に使用することもできます。  
  
 次の表は、各技術を通じて実現できる処理の一部を示しています。  
  
|環境|処理|使用する技術|  
|--------|--------|------------|  
|Web サーバー|ログオンと URL 要求に関する詳細情報を追跡する。|フィルターを作成し、ログオン イベントや URL マップの通知を要求します。|  
|Web ブラウザー|動的コンテンツを提供する。|ActiveX コントロールと Active ドキュメントを作成します。|  
|ドキュメント ベースのアプリケーション|FTP によるファイル操作のサポートを追加する。|WinInet または非同期モニカーを使用します。|  
  
 インターネットのプログラミングを始めるための方法については、以下の項目を参照してください。  
  
-   [アプリケーションのデザイン上の検討事項](../mfc/application-design-choices.md)  
  
-   [MFC アプリケーションの作成](../mfc/writing-mfc-applications.md)  
  
-   [インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)  
  
-   [既存の ActiveX コントロールのアップグレード](../Topic/Upgrading%20an%20Existing%20ActiveX%20Control.md)  
  
-   [インターネット上の Active ドキュメント](../Topic/Active%20Documents%20on%20the%20Internet.md)  
  
-   [インターネット上の非同期モニカー](../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [インターネット アプリケーションのテスト](../mfc/testing-internet-applications.md)  
  
-   [インターネットのセキュリティ](../Topic/Internet%20Security%20\(C++\).md)  
  
## 参照  
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)   
 [操作別のインターネット情報](../mfc/internet-information-by-task.md)