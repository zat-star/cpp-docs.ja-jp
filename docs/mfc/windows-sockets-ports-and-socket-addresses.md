---
title: "Windows ソケット : ポートとソケット アドレス | Microsoft Docs"
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
  - "アドレス [C++], ソケット"
  - "ポート [C++]"
  - "ポート [C++], 定義"
  - "ソケット [C++], アドレス"
  - "ソケット [C++], ポート"
  - "Windows ソケット [C++], アドレス"
  - "Windows ソケット [C++], ポート"
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows ソケット : ポートとソケット アドレス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、用語を「Ported」示し、「解決します。Windows ソケットに使用される」。  
  
##  <a name="_core_port"></a> ポート  
 ポート、サービスが提供できる一意のプロセスを識別します。  現在のコンテキストでは、ポートの Windows Sockets をサポートするアプリケーションに関連付けられます。  つまり、それぞれの Windows ソケットのアプリケーションを識別することです。したがって、コンピューターの Windows ソケットのアプリケーションの実行を同時に実行できます。  
  
 特定のポートは FTP などの共通サービス用に予約されています。  この種類のサービスを提供するこれらのポートの使用を避ける必要があります。  Windows ソケットの仕様では、予約済みのポートについて詳しく説明します。  ファイル WINSOCK.H はそれらを一覧表示します。  
  
 Windows が DLL が使用可能なポートを選択ソケットはポート値として有効にするには、\- 0 を渡します。  MFC はポート値を超える 1,024 の小数点を選択します。  MFC が [CAsyncSocket::GetSockName](../Topic/CAsyncSocket::GetSockName.md) のメンバー関数を呼び出して、選択したポート値を取得できます。  
  
##  <a name="_core_socket_address"></a> ソケット アドレス  
 各ソケット オブジェクトはネットワークのインターネット プロトコル \(IP\) のアドレスに関連付けられます。  通常、アドレスは「ftp.microsoft.com」などのコンピューター名、または「128.56.22.8」のような点を打たれた数です。  
  
 ソケットを作成して追求に対して独自のアドレスを指定する必要はありません。  
  
> [!NOTE]
>  コンピューターに複数のネットワーク カード \(またはアプリケーションがいつの日またはそのようなコンピューターで実行される場合があります\)、別のネットワークを表す個別に置くことができます。  この場合、どのネットワーク カードをソケットを使用するかを指定するにはアドレスを与える必要がある場合があります。  これは高度なと使用可能な移植性の問題になるのは確実です。  
  
 詳細については、次のトピックを参照してください。  
  
-   [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows ソケット: アーカイブが持つソケットのしくみについて](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
## 参照  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)