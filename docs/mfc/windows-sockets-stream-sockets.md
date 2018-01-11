---
title: "Windows ソケット: ストリーム ソケット |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- stream sockets [MFC]
ms.assetid: 31faaa34-a995-493f-a30b-b8115293d619
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc112bd3cfbf1194a2898afecb513edcbc456747
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-stream-sockets"></a>Windows ソケット : ストリーム ソケット
この記事では、ストリーム ソケットの場合、使用可能な 2 つの Windows ソケット型の 1 つについて説明します。 (他の型が、[データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md))。  
  
 ストリーム ソケットは、レコード境界のないデータ フローの: ことができる双方向のバイトのストリーム (アプリケーションが全二重:、両方の送信し、がソケットを介して受信)。 ストリームは、シーケンス処理された、重複していないデータを配信する際に依存できます。 ("Sequenced"パケットが送信された順序で配信されたことを意味します。 「重複していない」ことを意味特定のパケットを 1 回だけ取得します。)ストリーム メッセージの受信は保証し、ストリーム、大量のデータを処理するために適しています。  
  
 ネットワーク トランスポート層は、分割または妥当なサイズのパケットにデータをグループ化可能性があります。 `CSocket`梱包し、アンパックするにはクラスを処理します。  
  
 ストリームは明示的な接続に基づいて: ソケット、ソケット B; への接続を要求します。ソケット B を受け入れるか、接続要求を拒否します。  
  
 電話をかけるは、ストリームに例えるを提供します。 通常の状況では、受信側パーティが、順序どおりに、重複または損失なしでえ聞こえます。 ストリーム ソケットは、必要に応じて、たとえば、実装など、ファイル転送プロトコル (FTP)、転送する ASCII または任意のサイズのバイナリ ファイルを容易にします。  
  
 ストリーム ソケットが到着するデータを保証する必要がある場合と、データのサイズが大きなデータグラム ソケットに適しています。 ストリーム ソケットの詳細については、Windows ソケット仕様を参照してください。 Windows SDK では、仕様です。  
  
 ストリーム ソケットを使用するよりもアプリケーションのために、ネットワーク上のすべての受信ソケットにブロードキャストを行うデータグラム ソケットを使用するよう設計されています  
  
-   ブロードキャストのモデルは、ネットワーク洪水 (または"storm") の問題が適用されます。  
  
-   後で採用されているクライアント/サーバー モデルより効率的です。  
  
-   ストリームのモデルには、信頼性の高いデータの転送、データグラム モデルはありませんが用意されています。  
  
-   最終的なモデルを活用ソケット アプリケーションを Unicode と ANSI の間で通信する機能そのクラスをクラス CSocket CArchive やすくなっています。  
  
    > [!NOTE]
    >  クラスを使用する場合`CSocket`ストリームを使用する必要があります。 ソケット タイプを指定する場合、MFC アサーションは失敗**SOCK_DGRAM**です。  
  
## <a name="see-also"></a>参照  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)   
 [Windows ソケット: 予備知識](../mfc/windows-sockets-background.md)

