---
title: "コンボ ボックス コントロールを拡張に通知メッセージの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a78e7b9fd8f9c67f14a4bb51088866785d372cca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>拡張コンボ ボックス コントロールでの通知メッセージの処理
ユーザーが拡張コンボ ボックスを操作すると、コントロール (`CComboBoxEx`) から親ウィンドウ (通常はビュー オブジェクトかダイアログ オブジェクト) に通知メッセージが送信されます。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーがドロップダウン リストをアクティブにしたり、コントロールのエディット ボックスをクリックしたりすると、 **CBEN_BEGINEDIT** 通知が送信されます。  
  
 [プロパティ] ウィンドウを使用して、実装するメッセージの親クラスに通知ハンドラーを追加します。  
  
 拡張コンボ ボックス コントロールで送信される通知を一覧で説明します。  
  
-   **CBEN_BEGINEDIT** ユーザーがドロップダウン リストをアクティブにするか、コントロールのエディット ボックスをクリックすると送信されます。  
  
-   **CBEN_DELETEITEM** 項目が削除されると送信されます。  
  
-   **CBEN_DRAGBEGIN** ユーザーがコントロールの編集部分に表示される項目のイメージをドラッグし始めると送信されます。  
  
-   **CBEN_ENDEDIT** ユーザーがエディット ボックス内の操作を完了するか、コントロールのドロップダウン リストから項目を選ぶと、送信されます。  
  
-   **CBEN_GETDISPINFO** コールバック項目に関する表示情報を取得するために送信されます。  
  
-   **CBEN_INSERTITEM** 新しい項目がコントロールに挿入されると送信されます。  
  
## <a name="see-also"></a>参照  
 [CComboBoxEx の使い方](../mfc/using-ccomboboxex.md)   
 [コントロール](../mfc/controls-mfc.md)

