---
title: "タブ コントロール通知メッセージの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 840ff6fc5dd47a2059e62608b5a5d6f231f8f17c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="processing-tab-control-notification-messages"></a>タブ コントロールの通知メッセージの処理
ユーザーは、タブまたはボタン、タブ コントロールをクリックして、([CTabCtrl](../mfc/reference/ctabctrl-class.md))、親ウィンドウに通知メッセージを送信します。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーは、タブをクリックすると、可能性がある表示する前に、ページ上のコントロール データを事前設定します。  
  
 プロセス**WM_NOTIFY**ビューまたはダイアログ クラスでのタブ コントロールからのメッセージ。 [プロパティ] ウィンドウを使って作成、 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch ステートメントを持つハンドラー関数が通知メッセージを処理しているに基づいて。 タブ コントロールは自らの親ウィンドウに送信できます通知の一覧は、次を参照してください。、**通知**のセクション[タブ コントロールの参照](http://msdn.microsoft.com/library/windows/desktop/bb760548)Windows SDK に含まれています。  
  
## <a name="see-also"></a>参照  
 [CTabCtrl の使い方](../mfc/using-ctabctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

