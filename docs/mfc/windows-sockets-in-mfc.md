---
title: "MFC における Windows ソケット | Microsoft Docs"
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
  - "MFC [C++], Windows ソケット"
  - "ソケット [C++], MFC"
  - "ソケット [C++], プログラミング モデル"
  - "Windows ソケット [C++], MFC サポート"
  - "Windows ソケット [C++], プログラミング モデル"
  - "WINSOCK.DLL"
  - "WSOCK32.DLL"
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC における Windows ソケット
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  MFC Windows ソケット 1 は、[Windows ソケット 2](http://msdn.microsoft.com/library/windows/desktop/ms740673)をサポートしません。  最初に Windows 98 に付属する Windows ソケット 2 は、Windows 2000 に含まれるバージョンです。  
  
 MFC は、Windows ソケットを 2 個の MFC クラスに埋め込むされるネットワーク通信プログラムを作成するための 2 種類のモデルを指定します。  ここでは、これらのモデルとそのほかの詳細 MFC ソケットのサポートについて説明します。  「ソケット」は通信エンドポイントです: アプリケーションがネットワーク経由で他の Windows ソケットのアプリケーションと通信するオブジェクト。  
  
 ソケットの概念についてなど、Windows ソケットの詳細については、「[Windows ソケット: 背景](../mfc/windows-sockets-background.md)」を参照してください。  
  
##  <a name="_core_sockets_programming_models"></a> モデルをプログラミングするソケット  
 モデルをプログラミングする 2 種類の MFC Windows ソケットの次のクラスによってサポートされています:  
  
-   `CAsyncSocket`  
  
     このクラスは、Windows ソケット API をカプセル化します。  [CAsyncSocket](../Topic/CAsyncSocket%20Class.md) は ネットワーク プログラミングを行う、ソケット API のプログラミングの柔軟性を直接表示するネットワーク イベント通知のコールバック関数の利便性をプログラマのようにします。  C\+\+ のオブジェクト指向フォームのパッケージ化のソケット以外、このクラスが提供する唯一の追加抽象化はコールバックに特定のソケット関連の Windows メッセージを変換します。  詳細については、「[Windows ソケット: ソケットの通知](../Topic/Windows%20Sockets:%20Socket%20Notifications.md)」を参照してください。  
  
-   `CSocket`  
  
     このクラスは、`CAsyncSocket`から派生 [CArchive](../mfc/reference/carchive-class.md)、MFC オブジェクトを通じてソケットを持つ指定操作の高レベルの抽象化です。  アーカイブが持つソケットを使用して MFC ファイルのシリアル化のプロトコルを使用して非常によく似ています。  これを使用すること `CAsyncSocket` モデルよりも簡単になります。  [CSocket](../mfc/reference/csocket-class.md) は Windows ソケット API をカプセル化する `CAsyncSocket` から複数のメンバー関数を継承します; これらの機能の一部を使用し、一般にプログラミングするソケットを理解する必要があります。  ただし、`CSocket`、生の API または `CAsyncSocket`クラスを使用して独自にする必要があることを伝えるの多くの部分を管理します。  最も重要な点は、`CSocket` は `CArchive`の同期操作に必要なブロッキング \(Windows メッセージのバックグラウンド処理\) が用意されています。  
  
 `CSocket` と `CAsyncSocket` オブジェクトを作成および使用方法は [Windows ソケット: アーカイブが持つソケットを使用する](../mfc/windows-sockets-using-sockets-with-archives.md) と [Windows ソケット: CAsyncSocket クラスを使用します。](../mfc/windows-sockets-using-class-casyncsocket.md)で説明します。  
  
##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a> Windows ソケット DLL  
 Microsoft Windows のオペレーティング システムが Windows ソケットのダイナミック リンク ライブラリ \(DLL\) を指定します。  Visual C\+\+ では、適切なヘッダー ファイルとライブラリや Windows ソケットの仕様を指定します。  
  
> [!NOTE]
>  Windows NT と Windows 2000 では、16 ビット アプリケーションの Windows ソケットのサポートは WINSOCK.DLL に基づいています。  32 ビット アプリケーションの場合、サポートは WSOCK32.DLL にあります。  用意されている API は同じですが、32 ビット バージョンと 32 ビットに拡大変換されるパラメーターがあります。  Win32 で、スレッド セーフが用意されています。  
  
 Windows ソケットに関する詳細については、参照します:  
  
-   [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
-   [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows ソケット: 一連の操作](../Topic/Windows%20Sockets:%20Sequence%20of%20Operations.md)  
  
-   [Windows ソケット: アーカイブを使用するソケットの例](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Windows ソケット: アーカイブが持つソケットのしくみについて](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows ソケット: ソケット クラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows ソケット: ソケットの通知](../Topic/Windows%20Sockets:%20Socket%20Notifications.md)  
  
-   [Windows ソケット: ブロッキング](../Topic/Windows%20Sockets:%20Blocking.md)  
  
-   [Windows ソケット: バイト順序](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows ソケット: 文字列からの変換](../mfc/windows-sockets-converting-strings.md)  
  
-   [Windows ソケット: ポート、ソケット アドレス](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
## 参照  
 [Windows ソケット](../mfc/windows-sockets.md)