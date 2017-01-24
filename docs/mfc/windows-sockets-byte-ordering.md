---
title: "Windows ソケット : バイトの順序付け | Microsoft Docs"
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
  - "バイト順の問題点 (ソケット プログラミングの)"
  - "ソケット [C++], バイト順の問題点"
  - "Windows ソケット [C++], バイト順の問題点"
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows ソケット : バイトの順序付け
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この記事と 2 桁の関連記事は Windows ソケットのプログラミングの問題について説明します。  ここでは、バイト順序について説明します。  他の懸案事項が記事で説明されている: [Windows ソケット: ブロッキング](../Topic/Windows%20Sockets:%20Blocking.md) と [Windows ソケット: 文字列からの変換](../mfc/windows-sockets-converting-strings.md)。  
  
 クラス [CAsyncSocket](../Topic/CAsyncSocket%20Class.md)から使用または派生すれば、独自懸案事項を管理する必要があります。  クラス [CSocket](../mfc/reference/csocket-class.md)から使用または派生すれば、MFC は自動的にこれらを管理します。  
  
## バイト順序  
 別のバイト順を使用する別のコンピューター アーキテクチャ、ストア データ。  たとえば、Macintosh \(Motorola\) コンピューターの逆の順序で Intel ベースのコンピューター ストア データ。  リトル エンディアン「」、ネットワーク標準「ビッグ エンディアン」という順序を反転 Intel のバイト順ですか。  次の表は、これらの用語を示しています。  
  
### 大きいとリトル エンディアンのバイト順  
  
|バイト順序|説明|  
|-----------|--------|  
|ビッグ エンディアン|最上位バイトは Word の左端です。|  
|リトル エンディアン|最上位バイトは Word の右端にあります。|  
  
 通常、ネットワークにありますが、バイト順を変換する必要がある状況を送信し、が受け取るデータのバイト順の変換を実行する必要はありません。  
  
## バイト順を変換する必要があります  
 バイト順は次のような場合に変換する必要があります:  
  
-   別のコンピューターに送信されるデータに対してネットワークに解釈する必要がある情報を渡しています。  たとえば、理解する必要のあるネットワーク アドレス渡すことがあります。およびポートを。  
  
-   、通信しているサーバー アプリケーションは、MFC アプリケーションではありません \(と、そのクラスのソース・コードがありません\)。  これは、バイト順の変換を 2 台のコンピューターが同じバイト順序を共有するします。  
  
## バイト順を変換する必要がなくなったとき  
 バイト順は次のような場合に変換する作業が回避できます:  
  
-   両端のマシンからバイトを交換したことに同意してコンピューターの両方が同じのバイト順を使用します。  
  
-   対象と伝えているサーバーは MFC アプリケーションです。  
  
-   対象と伝達ため、バイト順を変換する必要があるかどうかを明示的に理解することは、サーバーのソース・コードがあります。  
  
-   MFC にサーバーを移植できます。  これは、してが比較的単純です。その結果、小規模で、高速コードです。  
  
 [CAsyncSocket](../Topic/CAsyncSocket%20Class.md)を使用して、ユーザーが必要なバイト順の変換を管理する必要があります。  Windows ソケットの「」ビッグ エンディアンのバイト順モデルを標準化し、この順序やそのほかの変換に関数を提供します。  ただし、これは [CSocket](../mfc/reference/csocket-class.md)で使用する[CArchive](../mfc/reference/carchive-class.md)はカウンター \(「リトル エンディアン」\) 順序、`CArchive` を処理するためのバイト順の変換の詳細が使用されます。  アプリケーションでこの標準命令または Windows ソケットのバイト順の変換関数を使用することによって、コードの移植性を高めることができます。  
  
 MFC ソケットの理想的な使用状況は、通信の両端を自分で作成し、両端で MFC を使用する場合です。  非 MFC アプリケーションを作成する場合は、FTP サーバーなど、通信するアプリケーションは、Windows ソケットの変換ルーチン **ntohs**、**ntohl**、**htons**と **htonl**を使用してアーカイブ オブジェクトにデータを渡す前に、独自のバイト スワップ処理を管理する必要があります。  非 MFC アプリケーションとの通信に使用されるこの記事でこれらの関数には後で表示されます。  
  
> [!NOTE]
>  通信の反対側の端部が MFC アプリケーションの場合は、受信側がそれらを処理できないため、アーカイブに `CObject` から派生される C\+\+ オブジェクトをストリームを避ける必要があります。  [Windows ソケット: アーカイブが持つソケットを使用する](../mfc/windows-sockets-using-sockets-with-archives.md)のメモを参照してください。  
  
 バイト順に関する詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]で Windows ソケットの仕様を参照します。  
  
## バイト順の変換の例  
 次の例は、アーカイブを使用する `CSocket` オブジェクトのシリアル化関数を示します。  また、Windows ソケット API のバイト順の変換関数を使用する方法について説明します。  
  
 この例は、ソース・コードにアクセスできない非 MFC サーバー アプリケーションと通信するクライアントを作成する例を示します。  このシナリオでは、非 MFC サーバーが標準ネットワークのバイト順を使用すると仮定します。  これに対し、MFC クライアント アプリケーションは `CSocket` オブジェクトを使用して `CArchive` オブジェクト、および `CArchive` の「」リトル エンディアンのバイト順、ネットワーク標準のオブジェクトを使用します。  
  
 、通信する非 MFC サーバーとします。次のようなメッセージ パケットの確立されるプロトコルを持つ:  
  
 [!CODE [NVC_MFCSimpleSocket#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#5)]  
  
 MFC の用語では、これは次のように表されます。:  
  
 [!CODE [NVC_MFCSimpleSocket#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#6)]  
  
 C\+\+ では、`struct` はクラスは基本的に同じです。  `Message` 構造体上で宣言された `Serialize` のメンバー関数などのメンバー関数を持つことができます。  `Serialize` メンバー関数は次のようになります。:  
  
 [!CODE [NVC_MFCSimpleSocket#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#7)]  
  
 この例では、データのバイト順の変換を 1 辺の非 MFC サーバー アプリケーションのバイト順序ともう一方の端の MFC クライアント アプリケーションで使用される `CArchive` 間に明確に不一致があるとします。  例では、バイト順の変換関数の例を、Windows ソケットの提供示しています。  次の表は、これらの機能を示します。  
  
### Windows ソケットのバイト順の変換関数  
  
|関数|目的|  
|--------|--------|  
|**ntohs**|ネットワークのバイト順からホスト \(ビッグ エンディアンのバイト順にリトル エンディアン\) に 16 ビット値を変換します。|  
|**ntohl**|ネットワークのバイト順からホスト \(ビッグ エンディアンのバイト順にリトル エンディアン\) に 32 ビット値を変換します。|  
|**Htons**|ホストのバイト順からネットワーク \(リトル エンディアンのバイト順にビッグ エンディアン\) に 16 ビット値を変換します。|  
|**Htonl**|ホストのバイト順からネットワーク \(リトル エンディアンのバイト順にビッグ エンディアン\) に 32 ビット値を変換します。|  
  
 この例のもう一つの点が通信の反対側の端部のソケット アプリケーションで非 MFC アプリケーションの場合、次のようにすることを避ける必要があります:  
  
 `ar << pMsg;`  
  
 `pMsg` が `CObject`クラスから派生される C\+\+. C\+\+ オブジェクトへのポインターです。  これは、オブジェクトに関連付けられた MFC 情報を追加し、それが MFC アプリケーション サーバーは同じように理解されません。  
  
 詳細については、次のトピックを参照してください。  
  
-   [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows ソケット: 背景](../mfc/windows-sockets-background.md)  
  
-   [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
## 参照  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)