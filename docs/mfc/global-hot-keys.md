---
title: "グローバル ホット キー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 82297507d8725e6292def759272f48d0d63e84b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="global-hot-keys"></a>グローバル ホット キー
グローバル ホット キーは、特定の子ウィンドウ以外のウィンドウに関連付けられます。 ユーザーは、システムの任意の部分からウィンドウをアクティブにできます。 アプリケーションが送信することによって特定のウィンドウでグローバル ホット キーを設定、 [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284)そのウィンドウにメッセージ。 たとえば場合、`m_HotKeyCtrl`は、 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)オブジェクトおよび`pMainWnd`へのポインターは、ホット キーが押されたときにアクティブ化されるウィンドウにあるコントロールに指定されたホット キーを関連付けるには、次のコードを使用する可能性がありますウィンドウを指す`pMainWnd`です。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]  
  
 グローバル ホット キーを押したときに指定されたウィンドウを受け取る、 [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360)を示すメッセージ**SC_HOTKEY**コマンドの種類として。 また、このメッセージを受け取ったウィンドウがアクティブにします。 このメッセージには、押されたキーに関する正しい情報が含まれていないためこのメソッドを使用することはできません、同じウィンドウに接続されている異なるホット キーの違い。 送信元アプリケーションまで、ホット キーは有効**WM_SETHOTKEY**が終了します。  
  
## <a name="see-also"></a>参照  
 [CHotKeyCtrl の使い方](../mfc/using-chotkeyctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

