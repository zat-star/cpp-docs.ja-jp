---
title: "Rebar コントロールの通知メッセージの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22a8b584c309cd6698ddd73449fcbba866111190
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Rebar コントロールでの通知メッセージの処理
Rebar コントロールの親クラスの作成、 `OnChildNotify` rebar コントロールすべてに、switch ステートメントを持つハンドラー関数 (`CReBarCtrl`) 通知メッセージを処理します。 ユーザーが rebar コントロール、変更したり、rebar コントロールから、削除、rebar バンドのレイアウトがバンド上のオブジェクトをドラッグしたときに、親ウィンドウへ通知が送信されます。  
  
 Rebar コントロール オブジェクトでは、次の通知メッセージを送信できます。  
  
-   **RBN_AUTOSIZE** rebar コントロールから送信されます (で作成された、**した**スタイル) ときに、rebar 自動的にサイズ変更するとき。  
  
-   **RBN_BEGINDRAG**ユーザーがバンドのドラッグを始めたとき rebar コントロールから送信されます。  
  
-   **RBN_CHILDSIZE**バンドの子ウィンドウのサイズが変更されるときに、rebar コントロールから送信します。  
  
-   **RBN_DELETEDBAND**バンドが削除された後に、rebar コントロールから送信します。  
  
-   **RBN_DELETINGBAND**バンドを削除するとき、rebar コントロールから送信されます。  
  
-   **RBN_ENDDRAG**ユーザーがバンドのドラッグを停止するときに、rebar コントロールから送信します。  
  
-   **RBN_GETOBJECT** rebar コントロールから送信されます (で作成された、**とき**スタイル) オブジェクトがコントロールでの帯域外を越えてドラッグされるときにします。  
  
-   **RBN_HEIGHTCHANGE**の高さが変更されたときに、rebar コントロールから送信します。  
  
-   **RBN_LAYOUTCHANGED**ユーザーがコントロールのバンドのレイアウトを変更したときに、rebar コントロールから送信します。  
  
 これらの通知の詳細については、次を参照してください。 [Rebar コントロールの参照](http://msdn.microsoft.com/library/windows/desktop/bb774375)Windows SDK に含まれています。  
  
## <a name="see-also"></a>参照  
 [CReBarCtrl の使い方](../mfc/using-crebarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

