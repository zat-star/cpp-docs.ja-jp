---
title: "Windows ソケット : ストリーム ソケット | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "ソケット [C++], ストリーム ソケット"
  - "ストリーム ソケット [C++]"
  - "Windows ソケット [C++], ストリーム ソケット"
ms.assetid: 31faaa34-a995-493f-a30b-b8115293d619
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows ソケット : ストリーム ソケット
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ストリーム ソケット、使用できる 2 種類の Windows ソケット タイプの 1 について説明します。そのほかの型は [データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)です\)。  
  
 ストリーム ソケットはレコード境界線のないデータ フローを提供し、T: 双方向の場合は、バイトのストリーム \(アプリケーション全二重です: これは、ソケットを通じて送受信できます\)。  連続するストリームは、unduplicated データを提供するために使用できます。パケットの送信順序で渡されること \(「配置する」ことを意味します。「一度だけ特定パケットを Unduplicated」を意味します。メッセージの受信ストリームが保証され、ストリームが大量のデータの処理に適しています。  
  
 ネットワーク トランスポート層は、適切なサイズでパケットにまたはグループ データ分割する場合があります。  `CSocket` クラスによってパッキングと展開を処理します。  
  
 ストリームは、接続に基づいています: ソケット A によってソケット B への接続を要求します; ソケット接続 B は要求を承認または拒否します。  
  
 電話、ストリームに優れた対比を提供します。  通常の状況で、受取側はそれを知らせると順序で複製を失わずに、理解してリッスンします。  ストリーム ソケットは任意のサイズの ASCII またはバイナリ ファイルを転送しやすくするファイル転送プロトコル \(FTP\) などの実装に適したなどです。  
  
 ストリーム ソケットはデータが到着することを保証する必要がある場合、データ サイズが大きい場合にデータグラム ソケットをお勧めします。  ストリーム ソケットに関する詳細については、Windows ソケットの仕様を参照します。  仕様は [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] で入手できます。  
  
 ストリーム ソケットを使用してネットワークのすべての受信によってソケットにブロードキャストにデータグラム ソケットを使用するようにはデザインされているアプリケーションより優れた方法です。  
  
-   ブロードキャスト モデルはネットワーク洪水 \(「嵐」\) の問題があります。  
  
-   後で導入されたクライアントサーバのモデルの方が効率的です。  
  
-   ストリーム モデルはデータグラム モデルが信頼できるデータ転送を提供します。  
  
-   最終的なモデルは Unicode の間で通信する機能を利用して、CSocket を分類するために行を分類する ANSI のソケット アプリケーションはたいへん役立ちます。  
  
    > [!NOTE]
    >  `CSocket`クラスを使用すると、ストリームを使用する必要があります。  MFC アサーションは **SOCK\_DGRAM**としてソケット タイプを指定すると失敗します。  
  
## 参照  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)   
 [Windows ソケット : 予備知識](../mfc/windows-sockets-background.md)