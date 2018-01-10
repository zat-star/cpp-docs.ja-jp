---
title: "Windows メッセージをクラスにマッピング |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4701b0ae9f71099febb1a239cea6285fb0a7b229
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mapping-windows-messages-to-your-class"></a>ダイアログ クラスと Windows メッセージの対応
Windows メッセージを処理するダイアログ ボックスを必要がある場合は、適切なハンドラー関数をオーバーライドします。 これを行うには、プロパティ ウィンドウを使用して[メッセージのマッピング](../mfc/reference/mapping-messages-to-functions.md)ダイアログ クラスにします。 これにより、各メッセージのメッセージ マップ エントリを書き込み、メッセージ ハンドラー メンバー関数をクラスに追加します。 Visual C ソース コード エディターを使用して、メッセージのハンドラーでコードを記述します。  
  
 メンバー関数を上書きすることもできます。 [CDialog](../mfc/reference/cdialog-class.md)とその基本クラスでは、特に[CWnd](../mfc/reference/cwnd-class.md)です。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)  
  
-   [通常オーバーライドされるメンバー関数](../mfc/commonly-overridden-member-functions.md)  
  
-   [通常追加されるメンバー関数](../mfc/commonly-added-member-functions.md)  
  
## <a name="see-also"></a>参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

