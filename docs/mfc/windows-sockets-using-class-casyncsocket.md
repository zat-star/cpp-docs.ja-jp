---
title: "Windows ソケット : CAsyncSocket クラスの使い方 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CAsyncSocket"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAsyncSocket クラス, プログラミング モデル"
  - "SOCKET ハンドル"
  - "ソケット [C++], 非同期操作"
  - "ソケット [C++], 変換 (Unicode と MBCS 文字列間の)"
  - "Windows ソケット [C++], 非同期"
  - "Windows ソケット [C++], 変換 (Unicode と MBCS 文字列を)"
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows ソケット : CAsyncSocket クラスの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、クラス [CAsyncSocket](../Topic/CAsyncSocket%20Class.md)を使用する方法について説明します。  このクラスが非常に低レベルで Windows ソケット API をカプセル化することに注意してください。  `CAsyncSocket` は ネットワーク通信を詳しく知るが、ネットワーク イベント通知のコールバックの利便性が必要な場合、プログラマによって使用されます。  この前提に基づいて、この記事は、基本的な手順を示します。  Windows ソケットの MFC アプリケーションの複数のネットワーク プロトコルを扱う Ease は、`CAsyncSocket` を使用することを検討する必要がある場合はと柔軟性を犠牲にするかどうか。  また、完了独自ことを通信が直接プログラミングすることで、より効率を取得できると考えられる場合があります `CSocket`クラスのより一般的な代替モデルを使用します。  
  
 `CAsyncSocket` は *MFC リファレンス"*を参照してください。  Visual C\+\+ では、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]にある Windows ソケット仕様を指定します。  詳細は、で行われます。  Visual C\+\+ では `CAsyncSocket`のサンプル アプリケーションを提供しません。  
  
 ネットワーク通信についてよく理解がなく、単純な解決策が不要な場合は、`CArchive` オブジェクトを使用して [CSocket](../mfc/reference/csocket-class.md) クラスを使用します。  詳細については、" [Windows ソケット: アーカイブが持つソケットを使用する](../mfc/windows-sockets-using-sockets-with-archives.md) を参照してください。  
  
 ここでは説明しています:  
  
-   `CAsyncSocket` オブジェクトを作成および使用します。  
  
-   [CAsyncSocket の役割](#_core_your_responsibilities_with_casyncsocket)。  
  
##  <a name="_core_creating_and_using_a_casyncsocket_object"></a> Creating and Using CAsyncSocket オブジェクト  
  
#### CAsyncSocket を使用します。  
  
1.  [CAsyncSocket](../Topic/CAsyncSocket%20Class.md) オブジェクトを構築し、**SOCKET** の基になるハンドルを作成するためにオブジェクトを使用します。  
  
     ソケットの作成は、正常な更新構築の MFC パターンに従います。  
  
     たとえば、次のようになります。  
  
     [!CODE [NVC_MFCSimpleSocket#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#3)]  
  
     または  
  
     [!CODE [NVC_MFCSimpleSocket#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#4)]  
  
     上の最初のコンストラクターは、スタックの `CAsyncSocket` オブジェクトを作成します。  2 番目のコンストラクターは、ヒープの `CAsyncSocket` を作成します。  上記の [作成](../Topic/CAsyncSocket::Create.md) の最初の呼び出しはストリーム ソケットの作成に既定のパラメーターを使用します。  **作成** の 2 回目の呼び出しでは、指定したアドレスとポートとデータグラム ソケットを作成します。\(いずれかの構築の **作成** メソッドのどちらのバージョンも使用できます\)。  
  
     **作成** へのパラメーターは次のとおりです。:  
  
    -   「:」ポート 短整数。  
  
         サーバー ソケットに、ポートを指定する必要があります。  クライアントのソケットは、通常、ソケットでポートを選択ウィンドウを有効にする場合は、このパラメーターの既定値を受け入れます。  
  
    -   ソケット タイプ: **SOCK\_STREAM** \(既定\) または **SOCK\_DGRAM**。  
  
    -   「ftp.microsoft.com」または「128.56.22.8」などのソケット「アドレス」。  
  
         これは、ネットワーク上のインターネット プロトコル \(IP\) のアドレスです。  このパラメーターの既定値に対して常に依存します。  
  
     用語「ポート」および「ソケット アドレスは [Windows ソケット: ポート、ソケット アドレス](../mfc/windows-sockets-ports-and-socket-addresses.md)」で説明します。  
  
2.  ソケットでクライアント、[CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md)を使用してサーバー ソケットへのソケット オブジェクトを接続します。  
  
     または  
  
     ソケットでサーバー、開始するようにソケット \([CAsyncSocket::Listen](../Topic/CAsyncSocket::Listen.md)と\) をリッスンし、クライアント接続の試みを設定します。  アタッチ要求を受信したときに、[CAsyncSocket::Accept](../Topic/CAsyncSocket::Accept.md)を受け入れます。  
  
     接続を受け入れると、パスワードを検証するなどのタスクを実行できます。  
  
    > [!NOTE]
    >  **承諾** のメンバー関数では、パラメーターとして `CSocket` の新しい空のオブジェクトへの参照を受け取ります。  **承諾**を呼び出す前にこのオブジェクトを構築する必要があります。  このソケット オブジェクトがスコープ外出かければ、接続が閉じています。  この新しいソケット オブジェクトの **作成** を呼び出さないでください。  例については、[Windows ソケット: 一連の操作](../Topic/Windows%20Sockets:%20Sequence%20of%20Operations.md)記事を参照してください。  
  
3.  Windows ソケット API 関数をカプセル化する `CAsyncSocket` オブジェクトのメンバー関数を呼び出して、ほかのソケットと通信を実行します。  
  
     Windows ソケット仕様と *MFC の参照*[CAsyncSocket](../Topic/CAsyncSocket%20Class.md) クラスを参照してください。  
  
4.  `CAsyncSocket` オブジェクトを破棄します。  
  
     スタックのソケット オブジェクトを作成したら、デストラクターを含む関数がスコープの外に出たときに呼び出されます。  、**new** の演算子を使用して作成した場合、ヒープのソケット オブジェクトを破棄するときに **delete** の演算子を使用する必要があります。  
  
     デストラクターは、オブジェクトを破棄する前にオブジェクトの [閉じる](../Topic/CAsyncSocket::Close.md) メンバー関数を呼び出します。  
  
 コードのこの手順の例では、実際に `CSocket` オブジェクトの場合\)、[Windows ソケット: 一連の操作](../Topic/Windows%20Sockets:%20Sequence%20of%20Operations.md)を参照してください。  
  
##  <a name="_core_your_responsibilities_with_casyncsocket"></a> CAsyncSocket の役割  
 クラス [CAsyncSocket](../Topic/CAsyncSocket%20Class.md)オブジェクトを作成すると、オブジェクトは Windows の **SOCKET** ハンドルをカプセル化し、そのハンドルの操作を提供します。  `CAsyncSocket`を使用するときに発生する可能性のあるすべての問題を処理が API を直接使用している場合。  たとえば、次のようになります。  
  
-   シナリオを「ブロック」。  
  
-   送信と受信のコンピューター間でバイト順の差を計算します。  
  
-   Unicode とマルチバイト文字セット \(MBCS\) 文字列の変換。  
  
 これらの用語と追加情報の定義については、[Windows ソケット: ブロッキング](../Topic/Windows%20Sockets:%20Blocking.md)、[Windows ソケット: バイト順序](../mfc/windows-sockets-byte-ordering.md)、[Windows ソケット: 文字列からの変換](../mfc/windows-sockets-converting-strings.md)を参照してください。  
  
 これらの問題にかかわらず、アプリケーションがすべての柔軟性を、の選択である必要があることができ、取得することもできます。**CAsycnSocket** クラスです。  そうでない場合、クラス `CSocket` を使用する代わりに検討する必要があります。  `CSocket` は ユーザーの詳細を非表示: これはブロッキング呼び出しで Windows メッセージをポンプを、のバイト順の相違点と文字列変換を管理する `CArchive`へのアクセスを提供します。  
  
 詳細については、次のトピックを参照してください。  
  
-   [Windows ソケット: 背景](../mfc/windows-sockets-background.md)  
  
-   [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
## 参照  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)