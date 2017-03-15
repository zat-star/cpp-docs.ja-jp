---
title: "コマンド ID | Microsoft Docs"
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
  - "コマンド ID"
  - "コマンド ID, MFC"
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# コマンド ID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コマンドは、単独でコマンド ID で適切に記述されます \(**WM\_COMMAND** メッセージでエンコードされて\)。  この ID は、コマンドを生成するユーザー インターフェイス オブジェクトに割り当てられます。  通常、ID が割り当てられているユーザー インターフェイス オブジェクトの機能という名前です。  
  
 たとえば、Clear 編集メニューのすべての項目 **ID\_EDIT\_CLEAR\_ALL**などの ID に割り当てることがあります。  クラス ライブラリはフレームワーク自体が処理する **ID\_EDIT\_CLEAR\_ALL** または `ID_FILE_OPEN`などのコマンドに対して、ID、特にあらかじめ定義されています。  他のコマンド ID を作成します。  
  
 Visual C\+\+ には、メニュー エディターで独自のメニューを作成すると、`ID_FILE_OPEN`で説明されているように、クラス ライブラリの名前付け規則に従うことをお勧めします。  [標準のコマンド](../mfc/standard-commands.md) は クラス ライブラリで定義されている標準コマンドについて説明します。  
  
## 参照  
 [ユーザー インターフェイス オブジェクトとコマンド ID](../mfc/user-interface-objects-and-command-ids.md)