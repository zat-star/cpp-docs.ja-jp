---
title: "メッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d03eed129fd5a2a7c73f7c7948cb766813f63c34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="messages"></a>メッセージ
メッセージ ループで、**実行**クラスのメンバー関数`CWinApp`取得には、さまざまなイベントによって生成されたメッセージがキューに登録します。 たとえば、ユーザーには、マウスがクリックすると、Windows は送信いくつかのマウスに関連するメッセージなど`WM_LBUTTONDOWN`マウスの左ボタンが押されたときに、`WM_LBUTTONUP`マウスの左ボタンが離されたとき。 アプリケーション メッセージ ループのフレームワークの実装では、目的のウィンドウ メッセージをディスパッチします。  
  
 メッセージの重要なカテゴリの記載[メッセージ カテゴリ](../mfc/message-categories.md)です。  
  
## <a name="see-also"></a>参照  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

