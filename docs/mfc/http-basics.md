---
title: "HTTP の基礎 | Microsoft Docs"
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
  - "HTTP 要求, 戻り値"
  - "HTTP, 戻り値"
  - "戻り値"
ms.assetid: 5b7421bf-42c8-4f3a-8566-8ff5957f58cc
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# HTTP の基礎
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

インターネット アプリケーションを記述する場合は、通常、HTTP ヘッダーの情報を確認し、追加します。  リターン コードは要求されたイベントの成功または失敗を示します。  複数の共通のリターン コードは、次の表に示します。  
  
|リターン コード|説明|  
|--------------|--------|  
|200|ある URL 送信です。|  
|400|わかりにくい要求|  
|404|要求された URL。|  
|405|サーバーは要求されたメソッドをサポートしません。|  
|500|不明なサーバー エラー|  
|503|サービスを使用できません。|  
  
 HTTP 応答は、次の表に示すようにグループ化されます。  
  
|グループ|説明|  
|----------|--------|  
|200–299|成功|  
|300–399|情報|  
|400–499|要求のエラー|  
|500–599|サーバー エラー|  
  
 ハイパーテキストの転送プロトコル \(HTTP\) は hypermedia の情報システム用のアプリケーション レベルのプロトコルです。  Web ブラウザーとサーバーとの通信を HTTP に関する詳細について、ハイパーテキストの転送プロトコル \(HTTP\) 仕様を参照し:  
  
 [http:\/\/www.w3.org\/pub\/WWW\/Protocols\/](http://www.w3.org/pub/WWW/Protocols/)  
  
## 参照  
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)