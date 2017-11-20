---
title: "メッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1766075663ef924e9a731169a09c3d396d643d2e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="messages"></a>メッセージ
メッセージ ループで、**実行**クラスのメンバー関数`CWinApp`取得には、さまざまなイベントによって生成されたメッセージがキューに登録します。 たとえば、ユーザーには、マウスがクリックすると、Windows は送信いくつかのマウスに関連するメッセージなど`WM_LBUTTONDOWN`マウスの左ボタンが押されたときに、`WM_LBUTTONUP`マウスの左ボタンが離されたとき。 アプリケーション メッセージ ループのフレームワークの実装では、目的のウィンドウ メッセージをディスパッチします。  
  
 メッセージの重要なカテゴリの記載[メッセージ カテゴリ](../mfc/message-categories.md)です。  
  
## <a name="see-also"></a>関連項目  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

