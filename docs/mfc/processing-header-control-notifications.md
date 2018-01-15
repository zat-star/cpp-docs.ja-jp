---
title: "ヘッダー コントロール通知の処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a442e6aadf7c91918cd523c29330e79c753b115c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="processing-header-control-notifications"></a>ヘッダー コントロール通知の処理
ビューまたはダイアログ クラスで、ウィンドウを使用してプロパティを作成、 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify)ハンドラー関数のヘッダー コントロールの switch ステートメントを持つ ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) にする通知メッセージ処理 (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。 ユーザーがクリックするか、項目との間の区分線をドラッグが、ヘッダー項目をダブルクリックしたときに、親ウィンドウへ通知が送信されます。  
  
 ヘッダー コントロールに関連付けられている通知メッセージに記載されて[ヘッダー コントロールの参照](http://msdn.microsoft.com/library/windows/desktop/bb775239)Windows SDK に含まれています。  
  
## <a name="see-also"></a>参照  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

