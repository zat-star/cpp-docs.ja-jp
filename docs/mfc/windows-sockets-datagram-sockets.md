---
title: "Windows ソケット : データグラム ソケット | Microsoft Docs"
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
  - "データグラム ソケット [C++]"
  - "ソケット [C++], 双方向データ フロー"
  - "ソケット [C++], データグラム"
  - "Windows ソケット [C++], 双方向データ フロー"
  - "Windows ソケット [C++], データグラム"
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Windows ソケット : データグラム ソケット
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、データグラム ソケット、使用できる 2 種類の Windows ソケット タイプの 1 について説明します。そのほかの型は [ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)です\)。  
  
 データグラム ソケットは配列または unduplicated とは限らない双方向のデータ フローをサポートします。  データグラムは信頼できるという保証はありません; これらはもに失敗した可能性があります。  データグラムの誤った順序および、複製操作は、データ レコードの境界はレコードは、受信側内部サイズ制限より小さい場合は維持されます。  担当 responsible を管理および信頼性配列。\(信頼性はローカル エリア ネットワーク \(LAN \[\] \[\] WAN なインターネットなどの範囲に領域より小さく、ネットワークの場合のように、傾向があります\)。  
  
 データグラムは「コネクションレス」です。つまり、明示的な接続できません; 指定ソケットにデータグラム メッセージを送信し、指定ソケットからメッセージを受け取ることができます。  
  
 データグラム ソケットの例は、ネットワークのシステム時計を同期させてアプリケーションです。  この場合、少なくとも設定のデータグラム ソケットの追加機能を確認する: 多くのネットワーク アドレスへの放送メッセージ。  
  
 データグラム ソケットはレコード指向のデータのストリーム ソケットより優先されます。  データグラム ソケットに関する詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]で Windows ソケットの仕様を参照します。  
  
## 参照  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)   
 [Windows ソケット : 予備知識](../mfc/windows-sockets-background.md)