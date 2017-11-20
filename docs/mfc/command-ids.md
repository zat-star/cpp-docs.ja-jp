---
title: "コマンド Id |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 95b531d12afc524e27bf36fc5a44d5f555fc9f91
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="command-ids"></a>コマンド ID
コマンドが、コマンド ID だけで完全に説明されている (でエンコードされた、 **WM_COMMAND**メッセージ)。 この ID は、コマンドを生成するユーザー インターフェイス オブジェクトに割り当てられます。 通常、Id に割り当てられているユーザー インターフェイス オブジェクトの機能の名前です。  
  
 たとえば、編集 メニューの すべてクリア項目割り当てる可能性がある ID など**ID_EDIT_CLEAR_ALL**です。 クラス ライブラリは、framework が処理する自体などのコマンドをいくつかの Id が組み込まれて**ID_EDIT_CLEAR_ALL**または`ID_FILE_OPEN`です。 その他のコマンド Id は、自分で作成したされます。  
  
 メニュー エディター、Visual C で独自のメニューを作成するときに、クラス ライブラリに従うことをお勧めの名前付け規則に示すように`ID_FILE_OPEN`です。 [標準コマンド](../mfc/standard-commands.md)クラス ライブラリで定義されている標準のコマンドについて説明します。  
  
## <a name="see-also"></a>関連項目  
 [ユーザー インターフェイス オブジェクトとコマンド ID](../mfc/user-interface-objects-and-command-ids.md)

