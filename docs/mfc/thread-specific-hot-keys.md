---
title: "スレッド固有のホット キー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 89c6ae27dacf5b8637c914c92b6805b1cc405353
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="thread-specific-hot-keys"></a>スレッド固有のホット キー
アプリケーションのスレッドに固有のホット キーの設定 ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md))、Windows を使用して**RegisterHotKey**関数。 ユーザーは、スレッド固有のホット キーを押すと、Windows の投稿、 [WM_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279)特定のスレッドのメッセージ キューの先頭へのメッセージ。 **WM_HOTKEY**仮想キー コード、シフト状態と押された特定のホット キーの ID のユーザー定義メッセージが含まれています。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。 このメソッドの詳細については、次を参照してください。 [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309)です。  
  
 呼び出しで使用されるシフト状態フラグ注**RegisterHotKey**によって返されるものと同じではない、 [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey)メンバー関数を呼び出す前にこれらのフラグを変換する必要があります**。RegisterHotKey**です。  
  
## <a name="see-also"></a>参照  
 [CHotKeyCtrl の使い方](../mfc/using-chotkeyctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

