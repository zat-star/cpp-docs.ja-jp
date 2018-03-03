---
title: "リスト コントロールの通知メッセージの処理 |Microsoft ドキュメント"
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
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c4a900b6fe0741de852c15afca37a974fc3e989
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-list-controls"></a>リスト コントロールでの通知メッセージの処理
ユーザーは、列ヘッダーをクリックして、アイコンをドラッグして、ラベルというように、リスト コントロールの編集 ([CListCtrl](../mfc/reference/clistctrl-class.md))、親ウィンドウに通知メッセージを送信します。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーには、列ヘッダーがクリックすると、ことができますを Microsoft Outlook のように、クリックした列の内容に基づいて項目を並べ替えます。  
  
 プロセス**WM_NOTIFY**ビューまたはダイアログ クラスのリスト コントロールからのメッセージ。 [プロパティ] ウィンドウを使って作成、 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch ステートメントを持つハンドラー関数が通知メッセージを処理しているに基づいて。  
  
 リスト コントロールを親ウィンドウに送信できる通知の一覧は、次を参照してください。[リスト ビュー コントロールへの参照](http://msdn.microsoft.com/library/windows/desktop/bb774737)Windows SDK に含まれています。  
  
## <a name="see-also"></a>参照  
 [CListCtrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

