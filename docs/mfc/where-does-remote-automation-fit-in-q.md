---
title: "リモート オートメーションを使用する場合 | Microsoft Docs"
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
  - "リモート オートメーション, DCOM"
ms.assetid: 4c4c8176-cfc0-44f7-bc87-b690f069ad2f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# リモート オートメーションを使用する場合
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DCOM が 1996 年に解放され、32 ビットおよび 64 ビットのプラットフォームでのみ使用できます。  Microsoft の Visual Basic チームが通信できるように、コンポーネントがするオートメーションを使用するように Visual Basic に常に参照しています。  分散バージョンでも、エンタープライズ環境の機能の使用が制限されるため、Visual Basic 4.0 Enterprise Edition を開発しているチームは、OLE オートメーションのパーツと COM のリモート処理コンポーネントの独自のセットの作成を調査することにしました。  当然ながら、主要目的が使用可能になったときに結果が互換性があり、DCOM に置き換えることができるようにすることです。  チームは、16 ビットと 32 ビット プラットフォームのリモート オートメーション \(RA\) を実装するようにします。  
  
 リモート オートメーションは、特定の言語に限定されませんが、Visual C\+\+ 4.2 Enterprise Edition のリリースまで、Visual Basic 4.0 でのみ提供されています。  リモート オートメーションが DCOM で完全に包含されることに注意してください。  アプリケーションでリモート オートメーションの代わりに DCOM を使用できる場合は、行ってください。  いずれにしても、リモート オートメーションが適切なシナリオがあります:  
  
-   16 ビットのクライアントがある場所で。  
  
-   社内で Windows NT または Windows 95 の DCOM 対応のバージョンを、出さなかったら。  
  
-   Visual Basic の一つ以上のコンポーネントの代わりに C\+\+ コンポーネントを使用するためにリモート オートメーションを使用する既存のアプリケーション スイートをアップグレードします。  
  
 DCOM 上でオートメーションを使用するためにリモート オートメーションを使用するために作成されるプログラムで作成されたプログラムの違いがある必要がなく、構成ユーティリティはリモート オートメーションと DCOM の間で切り替え操作を非常に簡単にします。  その結果インフラストラクチャが整っている場合、リモート オートメーションから DCOM にアプリケーションをアップグレードすることは困難です。  
  
## 参照  
 [リモート オートメーションの機能](../mfc/what-does-remote-automation-provide-q.md)   
 [DCOM の歴史](../mfc/history-of-dcom.md)