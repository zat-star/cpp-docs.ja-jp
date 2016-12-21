---
title: "Windows ソケット : アーカイブ付きソケットの使用 | Microsoft Docs"
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
  - "アーカイブ [C++], および Windows ソケット"
  - "CSocket クラス, プログラミング モデル"
  - "ソケット [C++], アーカイブを使用する"
  - "Windows ソケット [C++], アーカイブ"
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows ソケット : アーカイブ付きソケットの使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは [CSocket のプログラミング モデル](#_core_the_csocket_programming_model)について説明します。  [CAsyncSocket](../Topic/CAsyncSocket%20Class.md)を使用して、クラス [CSocket](../mfc/reference/csocket-class.md) は抽象化のレベルでソケット サポートを提供します。  `CSocket` は MFC [CArchive](../mfc/reference/carchive-class.md) オブジェクトを通じてソケット オブジェクト間でデータを渡すために MFC のシリアル化のプロトコルのバージョンを使用します。  `CSocket`、生の API または `CAsyncSocket`クラスを使用して独自にする必要があります。Windows メッセージのバックグラウンド処理を管理している間\) ブロッキングを提供し、通信の多くの部分を管理する `CArchive`へのアクセスを提供します。  
  
> [!TIP]
>  `CAsyncSocket`のより便利なバージョンとしてクラスを `CSocket`、単独で使用できますが、最も単純なプログラミング モデルは `CArchive` オブジェクト `CSocket` を使用します。  
  
 アーカイブが持つソケットの実装がどのように動作するか詳細については、「[Windows ソケット : アーカイブ付きソケットの動作](../mfc/windows-sockets-how-sockets-with-archives-work.md)」を参照してください。  コード例については、[Windows ソケット : 動作シーケンス](../Topic/Windows%20Sockets:%20Sequence%20of%20Operations.md) と [Windows ソケット : アーカイブを使用するソケットの例](../mfc/windows-sockets-example-of-sockets-using-archives.md)を参照します。  、ソケット クラスから独自のクラスを派生することにより取得できます。機能の一部については、[Windows ソケット : ソケット クラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)を参照してください。  
  
> [!NOTE]
>  確立された \(非 MFC\) サーバーと通信する MFC クライアント プログラムを記述したアーカイブを通じて C\+\+ オブジェクトを送信しません。  サーバーがオブジェクトの種類を把握する MFC アプリケーション送信するとき、であるオブジェクトを受け取り、逆シリアル化できません。  非 MFC アプリケーションとの通信に関する関連の素材の場合、[Windows ソケット : バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)記事を参照してください。  
  
##  <a name="_core_the_csocket_programming_model"></a> CSocket プログラミング モデル  
 `CSocket` オブジェクトを使用して、MFC クラス オブジェクトを作成し、関連付ける必要があります。  次の一般的な手順では、各ステップは、ソケット タイプが異なる処理を必要とする手順 3 を除き、ソケット ソケット サーバーとクライアントの両方で、実行されます。  
  
> [!TIP]
>  実行時のサーバー アプリケーションでは、通常、クライアント アプリケーションが接続を検索するときに最初に起動し準備と、「リッスン」です。  クライアントが接続しようとすると、サーバーの準備ができていない場合は、アプリケーションのユーザーが後で再接続するように要求します。  
  
#### ソケット ソケット クライアントとサーバー間の通信を設定するには  
  
1.  [CSocket](../mfc/reference/csocket-class.md) オブジェクトを構築します。  
  
2.  **SOCKET** の基になるハンドルを作成するためにオブジェクトを使用します。  
  
     `CSocket` クライアント オブジェクトの場合、データグラム ソケットを必要とする [作成](../Topic/CAsyncSocket::Create.md)に、既定のパラメーターを使用する必要があります。  `CSocket` のサーバー オブジェクトの場合、**作成** の呼び出しでポートを指定する必要があります。  
  
    > [!NOTE]
    >  `CArchive` は データグラム ソケットを使用しません。  データグラム ソケットに `CSocket` を使用する場合は、アーカイブなしで `CAsyncSocket` \(つまり、使用時にクラスを使用する必要があります。  データグラムが信頼できない \(くることが保証されていない、または誤った順序で送られて、返され、\) ため、アーカイブを使用してシリアル化と互換性がありません。  確実にと順に完了するとシリアル化操作が必要になります。  データグラムに `CArchive` オブジェクト `CSocket` を使用すると、MFC アサーションは失敗します。  
  
3.  ソケットでクライアントの場合、ソケット サーバーへのソケット オブジェクトを接続する呼び出し [CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md)。  
  
     または  
  
     ソケットでサーバーの場合、待機する呼び出し [CAsyncSocket::Listen](../Topic/CAsyncSocket::Listen.md) はクライアントからの試行をアタッチします。  アタッチ要求を受信したときに、[CAsyncSocket::Accept](../Topic/CAsyncSocket::Accept.md)を呼び出すことによってこれを受け入れます。  
  
    > [!NOTE]
    >  **承諾** のメンバー関数では、パラメーターとして `CSocket` の新しい空のオブジェクトへの参照を受け取ります。  **承諾**を呼び出す前にこのオブジェクトを構築する必要があります。  このソケット オブジェクトがスコープ外出かければ、接続が閉じています。  この新しいソケット オブジェクトの **作成** を呼び出さないでください。  
  
4.  これに `CSocket` オブジェクトを関連付ける [CSocketFile](../Topic/CSocketFile%20Class.md) オブジェクトを作成します。  
  
5.  読み込み \(受信\) または送信 \(\) に [CArchive](../mfc/reference/carchive-class.md) オブジェクトを格納するデータを作成します。  アーカイブが `CSocketFile` オブジェクトに関連付けられます。  
  
     `CArchive` がデータグラム ソケットが使用されないことに注意してください。  
  
6.  クライアントとサーバーの間のソケット パス データへの `CArchive` オブジェクトを使用します。  
  
     `CArchive` の特定のオブジェクトに 1 方向のデータのみを移動することに注意してください。: \(受信\) 読み込むか、\(送信\) に格納できます。  場合によっては、`CArchive` の 2 種類のオブジェクトを使用して T: データを送信するための 1、受信他を受け取るようにします。  
  
     接続を受け入れ、アーカイブを設定した後、パスワードを検証するなどのタスクを実行できます。  
  
7.  アーカイブ、ソケット ファイルおよびソケット オブジェクトを破棄します。  
  
    > [!NOTE]
    >  クラス `CSocket`を持つ `CArchive` の提供を操作するためのメンバー関数 `IsBufferEmpty` の分類します。  複数のメッセージ バッファーがデータなどを含んでいる場合、すべての読み取り、バッファーがクリアされるまでループする必要があります。  それ以外の受信するデータがあり、次の通知は無期限に発生することがあります。  すべてのデータを取得することを保証するために `IsBufferEmpty` を使用します。  
  
 記事 [Windows ソケット : 動作シーケンス](../Topic/Windows%20Sockets:%20Sequence%20of%20Operations.md) コード例は、このプロセスの両側について説明します。  
  
 詳細については、次のトピックを参照してください。  
  
-   [Windows ソケット : ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット : データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
## 参照  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)   
 [CSocket::Create](../Topic/CSocket::Create.md)