---
title: "CSocket クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSocket"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSocket クラス"
  - "SOCKET ハンドル"
  - "ソケット クラス"
  - "WinSock CSocket クラス"
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSocket クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CAsyncSocket`から派生し、WindowsソケットAPIのカプセル化を継承し、`CAsyncSocket` のオブジェクトよりも高いレベルの抽象化を表します。  
  
## 構文  
  
```  
class CSocket : public CAsyncSocket  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSocket::CSocket](../Topic/CSocket::CSocket.md)|`CSocket` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSocket::Attach](../Topic/CSocket::Attach.md)|`CSocket` のオブジェクトに **\[ソケット\]** ハンドルをアタッチします。|  
|[CSocket::CancelBlockingCall](../Topic/CSocket::CancelBlockingCall.md)|現在進行中のブロッキング呼び出しを取り消します。|  
|[CSocket::Create](../Topic/CSocket::Create.md)|ソケットを作成します。|  
|[CSocket::FromHandle](../Topic/CSocket::FromHandle.md)|**\[ソケット\]** のハンドルがの `CSocket` オブジェクトへのポインターを返します。|  
|[CSocket::IsBlocking](../Topic/CSocket::IsBlocking.md)|ブロッキング呼び出しが実行中であるかどうかを判定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSocket::OnMessagePending](../Topic/CSocket::OnMessagePending.md)|完了するためにブロッキング呼び出しを待機している間、メッセージの処理するために呼び出されます。|  
  
## 解説  
 `CSocket` は、クラス `CSocketFile` と `CArchive` をデータの送信と受信を管理するために使用します。  
  
 `CSocket` のオブジェクトも `CArchive`の同期操作に必要なブロッキングを提供します。  ブロックは、`Receive`など、`Send`、`ReceiveFrom`、`SendTo`機能し、`Accept` \(完全に `CAsyncSocket`から継承されます\)、`CSocket`の `WSAEWOULDBLOCK` のエラーが返されます。  代わりに、これらの関数は、操作が完了するまで待機します。  また、元のの呼び出しはエラーと `WSAEINTR` これらの関数の1種類がブロックされて `CancelBlockingCall` が呼び出されたときに終了します。  
  
 `CSocket` のオブジェクトを使用するには、`SOCKET` の基になる型 \(`SOCKET`\) ハンドルを作成するように、コンストラクター、呼び出し `Create` を呼び出します。  `Create` の既定のパラメーターは、ストリーム ソケットを作成します `CArchive` のオブジェクトを使用して、ソケットを使用する代わりに、データグラム ソケットを作成するには、パラメーターを指定したり、サーバーのソケットを作成する特定のポートにバインドします。  クライアント側の `Connect` とサーバー側の `Accept` を使用してクライアントのソケットに接続します。  次 `CSocketFile` のオブジェクトを作成し、`CSocketFile` のコンストラクターの `CSocket` のオブジェクトに関連付けます。  次に \(必要な場合\)、送信するための `CArchive` のオブジェクトとデータを受け取るため、" 1 "を作成し、`CArchive` のコンストラクターの `CSocketFile` のオブジェクトに関連付けます。  通信が完了すると、`CArchive`、`CSocketFile`と `CSocket` オブジェクトを破棄します。  `SOCKET` のデータ型 [Windowsソケット: 背景](../../mfc/windows-sockets-background.md)は、" "で説明します。  
  
 `CSocketFile` と `CSocket`の `CArchive` を使用すると、`CSocket::Receive` がバイトの要求した量を待機するループ \(など\) を入力 `PumpMessages(FD_READ)`状態に陥る可能性があります。  これは、WindowsソケットでFD\_READ通知ごとに1回だけを割り当てるrecvの呼び出しが、`CSocketFile` と `CSocket` はFD\_READごとに複数のrecvの呼び出しを可能にするためです。  読み込むデータがない場合FD\_READを取得するアプリケーションがハングアップ。  、他のFD\_READを取得、アプリケーションはSocketsへの通信を停止します。  
  
 この問題を次のように解決できます。  は、ソケットのクラスの `OnReceive` のメソッドでは、ソケットから読み取る必要なデータが1台のTCPネットワーク パケット \(Intermediate、通常は少なくとも1096バイトの送出バイト単位\) の最大サイズを超えると、独自のメッセージ クラスの `Serialize` のメソッドを呼び出す前に、呼び出し `CAsyncSocket::IOCtl(FIONREAD, ...)`。  使用可能なデータ サイズが小さい必要な場合は、受信するすべてのデータを待機し、次にのみ読み取り操作を開始します。  
  
 次の例では、`m_dwExpected` が受け取るとuserが受け取るおおよそのバイト数です。  コード内で、他の場所で宣言することを前提としています。  
  
 [!CODE [NVC_MFCSocketThread#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSocketThread#4)]  
  
> [!NOTE]
>  MFCソケットを静的にリンクされるMFCアプリケーションのセカンダリ スレッドで使用すると、ソケット ライブラリを初期化するには、ソケットを使用する各スレッドの `AfxSocketInit` を呼び出す必要があります。  既定では、`AfxSocketInit`、プライマリ スレッドでのみ呼び出されます。  
  
 詳細については、[MFCのWindowsソケット](../../mfc/windows-sockets-in-mfc.md)、[Windowsソケット: アーカイブを持つソケットを使用する](../../mfc/windows-sockets-using-sockets-with-archives.md)、[Windowsソケット: アーカイブを持つソケットのしくみ](../../mfc/windows-sockets-how-sockets-with-archives-work.md)、[Windowsソケット: 処理の流れ](../Topic/Windows%20Sockets:%20Sequence%20of%20Operations.md)、[Windowsソケット: アーカイブを使用してソケットの例](../../mfc/windows-sockets-example-of-sockets-using-archives.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAsyncSocket](../Topic/CAsyncSocket%20Class.md)  
  
 `CSocket`  
  
## 必要条件  
 **ヘッダー:** afxsock.h  
  
## 参照  
 [CAsyncSocket クラス](../Topic/CAsyncSocket%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket クラス](../Topic/CAsyncSocket%20Class.md)   
 [CSocketFile クラス](../Topic/CSocketFile%20Class.md)