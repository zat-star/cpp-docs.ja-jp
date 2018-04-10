---
title: コマンド ターゲット |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bb8d2bff69e95a089827c85ade6dc4bcd67eb7ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="command-targets"></a>コマンド ターゲット
図[フレームワークにおけるコマンド](../mfc/user-interface-objects-and-command-ids.md)メニュー項目とその結果、コマンド オブジェクトがクリックされたときに実行するためにフレームワークから呼び出されるハンドラー関数などのユーザー インターフェイス オブジェクト間の接続を示しています。  
  
 Windows では、メッセージのハンドラーが呼び出されますウィンドウに直接コマンド メッセージではないメッセージを送信します。 ただし、フレームワークは候補オブジェクトの数にコマンドを送ります —「コマンド ターゲット」と呼ばれる — うちの 1 つ通常コマンドのハンドラーを呼び出します。 ハンドラー関数のコマンドと標準の Windows メッセージの両方で同様の動作で説明したように、呼び出されるメカニズムが異なる場合、[フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)です。  
  
## <a name="see-also"></a>参照  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

