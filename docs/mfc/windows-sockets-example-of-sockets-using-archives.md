---
title: "Windows ソケット : アーカイブを使用するソケットの例 | Microsoft Docs"
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
  - "例 [MFC], Windows ソケット"
  - "ソケット [C++], アーカイブを使用する"
  - "Windows ソケット [C++], アーカイブを使用する"
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Windows ソケット : アーカイブを使用するソケットの例
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、クラス [CSocket](../mfc/reference/csocket-class.md)使用例を示します。  例では、ソケットを通じてシリアル化するデータへの `CArchive` オブジェクトを使用しています。  これがファイルから、またはドキュメントのシリアル化ではないことに注意してください。  
  
 `CSocket` オブジェクトを通じてデータを送受信するためにアーカイブを使用する方法を次の例に示します。  例はアプリケーション \(同じコンピューターまたはネットワーク上の別のコンピューター\) の 2 種類のデータ インスタンス設計されています。  1 個のインスタンスは、他のインスタンスを受け取り、にデータを送信します。  どのアプリケーションが交換を開始する他のアプリケーションにサーバーまたはクライアントとして動作します。  次の関数は、アプリケーションのビュー クラスで定義されています:  
  
 [!CODE [NVC_MFCSimpleSocket#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#1)]  
  
 この例の重要なことは、MFC `Serialize` の相互作用する構造体の並列です。  **PacketSerialize** のメンバー関数は **else** 句との **if** のステートメントで構成されます。  関数では、パラメーターとして [CArchive](../mfc/reference/carchive-class.md) の 2 種類の参照が表示: `arData` と `arAck`。  `arData` のアーカイブ オブジェクト \(送信\) 用に設定されている場合、**if** の分岐が実行される; それ以外の場合は `arData` が読み込み \(受信\) に設定されている場合、関数は **else** の分岐を受け取ります。  MFC のシリアル化の詳細については、「[シリアル化](../mfc/how-to-make-a-type-safe-collection.md)」を参照してください。  
  
> [!NOTE]
>  `arAck` のアーカイブ オブジェクトは `arData`のオブジェクトと見なされます。  `arData` が送信する場合は、`arAck` を受け取り、その逆は true です。  
  
 送信するために、この例の関数は、ランダムなデータをわかりやすくするために生成される指定回数では、各ループします。  アプリケーションは、ファイルなどのソースから実際のデータを取得します。  `arData` アーカイブの出力ストリーム演算子 \(**\<\<**\) がデータの 3 個の連続するチャンクのストリームを送信するために使用されています:  
  
-   データの性質を指定する「ヘッダー」 \(数枚コピーの送信先\) この場合、変数 `bValue` の値および。  
  
     項目は、どちらもこの例にランダムに生成されます。  
  
-   データの指定部数。  
  
     **for** の内側のループが `bValue` に指定された回数を送信します。  
  
-   文字列が受信者がユーザーに表示する `strText` と呼ばれます。  
  
 受信側の場合、関数は同じように動作します。ただし、アーカイブからデータを取得するためにアーカイブのストリーム演算子 \(**\>\>**\) を使用します。  受信側アプリケーションが受け取るデータを検証し、最終「」受信メッセージを表示し、表示する送信元のアプリケーションに「の」通知メッセージを送信しています。  
  
 この通信では、コミュニケーションの反対側に表示するには」、受信「 `strText` 変数に送信されたメッセージをシミュレートするため、特定のデータ パケットの受信を受信のユーザーを指定します。  受信側は「の」と表示元の送信元の画面の表示と同様の文字列に応答します。  両方の文字列を受け取るは通常の通信が発生したことを示します。  
  
> [!CAUTION]
>  確立された \(非 MFC\) サーバーと通信する MFC クライアント プログラムを記述したアーカイブを通じて C\+\+ オブジェクトを送信しません。  サーバーがオブジェクトの種類を把握する MFC アプリケーション送信するとき、であるオブジェクトを受け取り、逆シリアル化できません。  記事 [Windows ソケット: バイト順序](../mfc/windows-sockets-byte-ordering.md) の例は、この型の通信を示しています。  
  
 詳細については、Windows ソケットの仕様を参照します: **htonl**、**htons**、**ntohl**、**ntohs**。  また、詳細については、"参照してください:  
  
-   [Windows ソケット: ソケット クラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows ソケット: アーカイブが持つソケットのしくみについて](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows ソケット: 背景](../mfc/windows-sockets-background.md)  
  
## 参照  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)   
 [CArchive::IsStoring](../Topic/CArchive::IsStoring.md)   
 [CArchive::operator \<\<](../Topic/CArchive::operator%20%3C%3C.md)   
 [CArchive::operator \>\>](../Topic/CArchive::operator%20%3E%3E.md)   
 [CArchive::Flush](../Topic/CArchive::Flush.md)   
 [CObject::Serialize](../Topic/CObject::Serialize.md)