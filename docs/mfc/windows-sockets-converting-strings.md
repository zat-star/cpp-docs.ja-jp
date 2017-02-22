---
title: "Windows ソケット : 文字列の変換 | Microsoft Docs"
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
  - "ソケット [C++], マルチバイト文字列変換の問題"
  - "文字列変換, マルチバイト文字列"
  - "Windows ソケット [C++], マルチバイト文字列変換"
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Windows ソケット : 文字列の変換
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この記事と 2 桁の関連記事は Windows ソケットのプログラミングの問題について説明します。  ここでは、文字列を変換する方法について説明します。  他の懸案事項が [Windows ソケット: ブロッキング](../Topic/Windows%20Sockets:%20Blocking.md) と [Windows ソケット: バイト順序](../mfc/windows-sockets-byte-ordering.md)で説明します。  
  
 クラス [CAsyncSocket](../Topic/CAsyncSocket%20Class.md)から使用または派生すれば、独自懸案事項を管理する必要があります。  クラス [CSocket](../mfc/reference/csocket-class.md)から使用または派生すれば、MFC は自動的にこれらを管理します。  
  
## 文字列からの変換  
 異なるワイド文字形式では、Unicode またはマルチバイト文字セット \(MBCS\) など、またはこれらの 1 に ANSI 文字列を使用してアプリケーションの間に格納されている文字列を使用するアプリケーションの間で通信する変換を独自 `CAsyncSocket`で管理する必要があります。  `CSocket` オブジェクトで使用される `CArchive` オブジェクトは、クラス [CString](../atl-mfc-shared/reference/cstringt-class.md)の機能によって、の変換を管理します。  詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]にある Windows ソケット仕様を参照します。  
  
 詳細については、次のトピックを参照してください。  
  
-   [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows ソケット: 背景](../mfc/windows-sockets-background.md)  
  
-   [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
## 参照  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)