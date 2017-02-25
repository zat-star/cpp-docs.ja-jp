---
title: "Windows ソケット : ソケット クラスからの派生 | Microsoft Docs"
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
  - "派生クラス, ソケット クラスから"
  - "ソケット [C++], 派生 (ソケット クラスから)"
  - "Windows ソケット [C++], 派生 (ソケット クラスから)"
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Windows ソケット : ソケット クラスからの派生
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ソケットの 1 つがクラスから独自のクラスを派生することによって取得できる機能について説明します。  
  
 [CAsyncSocket](../Topic/CAsyncSocket%20Class.md) または [CSocket](../mfc/reference/csocket-class.md) から独自の機能を追加する独自のソケット クラスを派生できます。  たとえば、次のようなクラスには、オーバーライドできる一連の仮想メンバー関数を提供します。  これらの関数は、[OnReceive](../Topic/CAsyncSocket::OnReceive.md)[OnSend](../Topic/CAsyncSocket::OnSend.md)、[OnAccept](../Topic/CAsyncSocket::OnAccept.md)、[OnConnect](../Topic/CAsyncSocket::OnConnect.md)と [OnClose](../Topic/CAsyncSocket::OnClose.md)が含まれます。  ネットワーク イベントが発生すると指定する通知を利用するために派生ソケット クラスの関数をオーバーライドできます。  フレームワークは、読み始めることができるデータの受信などの重要なソケット イベントを通知するために、これらの通知コールバック関数を呼び出します。  通知関数の詳細については、「[Windows ソケット: ソケットの通知](../Topic/Windows%20Sockets:%20Socket%20Notifications.md)」を参照してください。  
  
 また、クラス `CSocket` は [OnMessagePending](../Topic/CSocket::OnMessagePending.md) のメンバー関数 \(高度なオーバーライドできる\) を指定します。  MFC は、Windows ソケット ベースのメッセージ ポンプを行っているときにこの関数を呼び出します。  Windows から特定のメッセージを検索し、それに応答する `OnMessagePending` をオーバーライドできます。  
  
 `OnMessagePending` の既定のバージョンは `CSocket` が完了するブロッキング呼び出しを待機している間 `WM_PAINT` メッセージのメッセージ キューを調べるクラスで指定します。  これは、表示品質を向上させるために描画メッセージをディスパッチします。  有効な操作を行うこと以外に、これは自分で関数をオーバーライドできる 1 種類の方法について説明します。  別の例として、次のタスクの `OnMessagePending` を使用することを検討してください。  完了するためにネットワーク トランザクションを待っている間に、モードレス ダイアログ ボックスを表示するとします。  ダイアログ ボックスが非常に長い時間がかかるブロッキングのトランザクションを取り消すために使用できるキャンセル ボタンが含まれています。  `OnMessagePending` のオーバーライドがこのモードレス ダイアログ ボックスに関連するメッセージをポンプして場合があります。  
  
 `OnMessagePending` のオーバーライドでは、呼び出しから `OnMessagePending`の基本クラス バージョンに **TRUE**。値を返します。  、まだする作業を実行する場合は、基本クラスのバージョンを呼び出します。  
  
 詳細については、次のトピックを参照してください。  
  
-   [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows ソケット: ブロッキング](../Topic/Windows%20Sockets:%20Blocking.md)  
  
-   [Windows ソケット: バイト順序](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows ソケット: 文字列からの変換](../mfc/windows-sockets-converting-strings.md)  
  
## 参照  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)